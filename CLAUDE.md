# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

An MTG Commander (EDH) deck-building workspace for Eldrazi decks — data files and Markdown analysis, no application code, no build or tests. Two decks exist:

- **Zhulodok, Void Gorger** (pure colorless) — `deck/zhulodok-bracket3.txt`
- **Ulalek, Fused Atrocity** (five-color identity, colorless core) — `deck/ulalek-bracket3.txt`

The decklist `.txt` files are **canonical for card names and counts**; buylists and reviews follow them. Decision history and errata live as `//` comments at the bottom of the decklists and in `TODO.md` — read those before re-litigating a card choice. `eldrazi-incursion-*.txt` is the imported source snapshot the Ulalek list was derived from.

Other key files:

- `deck/buylist.md`, `deck/ulalek-buylist.md` — priced buylists (Cardmarket EUR via Scryfall, snapshot-dated in the header; keep that convention when updating prices)
- `deck/bracket4-upgrades.md` — swap module to take the Zhulodok list from bracket 3 to 4
- `deck/review-2026-08-18.md` — structural review of the Zhulodok list
- `archidekt-collection-export-*.csv` — the physical collection export

## House rules (already adjudicated — don't re-flag)

- **Bracket-3 combo policy:** only *early-game* 2-card infinite combos must be cut; late-game combo lines are allowed. Applied rulings: Basalt Monolith + Forsaken Monument was **cut from Zhulodok** (swapped to Sisay's Ring) but **deliberately kept in Ulalek** as a late-game line; Food Chain + Eternal Scourge (+ Glaring Fleshraker) was cut from Ulalek. Bracket 3 also caps official Game Changers at 3 — Ulalek sits at that cap (Mana Vault, Ancient Tomb, Crop Rotation; note Mana Drain is *not* on the Feb-2026 GC list), Zhulodok has 1 (Mana Vault).
- **Ownership accounting:** only the collection CSV counts as owned. Prior buylists are *not* acquisitions. The owner proxies freely — keep expensive cards and mark ≥25€ ones as proxy candidates instead of substituting budget cards; flag anything approaching 100€ for a double-check.
- **Card evaluation:** prefer standalone-impactful cards; Tron/Cloudpost-style synergy lands are low-value in singleton.
- **Color identity trap:** devoid cards are colorless but keep their colored identity (e.g. Kozilek's Unsealing `{2}{U}` is illegal in Zhulodok, fine in Ulalek). This mistake has been made twice — check identity, not color, before recommending a card for Zhulodok.

## The `magic` MCP server: what works, what's broken, and the workaround

Status as of 2026-08-19 (we plan to fork and fix the server later):

- ❌ **All `bulk_*` tools fail** — Scryfall changed its bulk-data API (metadata now exposes `jsonl_download_uri` serving JSONL; the server still reads the removed `download_uri` key). This also makes **`deck_analysis` hang to timeout**, since it resolves cards through the bulk backend first.
- ❌ **`spellbook_estimate_bracket` returns malformed output** — non-numeric `bracket_tag` (e.g. `"R"`) and an empty `game_changer_cards` list even when known Game Changers are in the input. Do not trust it.
- ✅ Working: `scryfall_*` (direct API), `spellbook_find_decklist_combos`, `edhrec_*`, `ping`.

### Deck-analysis procedure (the workaround)

1. **Card data:** fetch straight from the Scryfall API, not the MCP bulk tools:
   ```bash
   curl -s --get "https://api.scryfall.com/cards/named" --data-urlencode "exact=$name"
   ```
   Loop over the decklist with `sleep 0.12` between requests (Scryfall rate limit ~10/s); extract `cmc`, `mana_cost`, `type_line`, `oracle_text` into a JSONL scratch file. For double-faced cards `oracle_text` is on `card_faces`.
2. **Curve / tipping point:** compute the curve from that JSONL and run a Monte Carlo goldfish sim (Python, ~20k iterations): shuffle, simple mulligan (keep 2–5 lands), play a land + cast rocks/cost-reducers greedily each turn, and report medians and by-turn percentages for (a) commander castable, (b) 7 effective mana available, (c) first MV-7+ threat castable (mana **and** card in hand). Model Ancient Tomb/Eldrazi Temple as 2 mana, Eye of Ugin as a −2 reducer. Hypergeometric math (`math.comb`) answers "odds of holding interaction by turn N".
3. **Combos:** `spellbook_find_decklist_combos` with the full list; read the `included` array (ignore `almost_included` unless hunting upgrades).
4. **Bracket:** manual — count Game Changers against the official WotC list and apply the combo policy above. Do not use `spellbook_estimate_bracket`.

Benchmarks from the 2026-08-19 Ulalek analysis for comparison: median commander turn 4, 7 mana by T5 in 53% of games, first haymaker median T6, average table win ~T10.

Use `$CLAUDE_JOB_DIR/tmp` (or another scratch dir) for fetched JSONL and sim scripts — they are throwaway; conclusions go into `deck/*.md`.
