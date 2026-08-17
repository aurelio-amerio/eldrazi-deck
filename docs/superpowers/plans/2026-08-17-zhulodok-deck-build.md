# Zhulodok Eldrazi Deck Build Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Produce the validated 100-card Zhulodok, Void Gorger bracket-3 Commander deck with priced buylist (owned/buy/proxy) and bracket-4 upgrade doc, per `docs/superpowers/specs/2026-08-17-zhulodok-eldrazi-deck-design.md`.

**Architecture:** The full decklist is specified in Task 1 of this plan (deck design decisions are already made from EDHREC/price data). Execution validates it with the `claude.ai magic` MCP tools (legality, color identity, bracket, prices), applies rule-driven buy/proxy decisions, and writes the deliverable files.

**Tech Stack:** Plain text/markdown files; `claude.ai magic` MCP tools (`deck_validate`, `spellbook_estimate_bracket`, `scryfall_card_price`, `scryfall_card_details`, `deck_analysis`). MCP tools are deferred — load with ToolSearch `select:<name>` before calling. Card data tools may need the `mcp__claude_ai_magic__` prefix.

## Global Constraints

- Commander: Zhulodok, Void Gorger. All 99 cards must have colorless color identity.
- Bracket 3: ≤3 Game Changers (list contains exactly 1: Mana Vault), no mass land denial, no chained extra turns, no early 2-card infinite combos.
- Legal per current Commander ban list.
- Budget: purchases ≤200€ total (Cardmarket EUR prices). Cards ≤10€ bought freely; 10–25€ cards bought by priority order until ceiling; remainder proxied. No card ≥100€ anywhere in the deck (not even proxied).
- Owned cards (from `archidekt-collection-export-2026-08-17.csv`) cost 0€: Eldrazi Temple, Eye of Ugin (x2), Sol Ring, Emrakul the Aeons Torn, Kozilek Butcher of Truth, Ulamog the Infinite Gyre (x2), It That Betrays, Pathrazer of Ulamog, Ulamog's Crusher, Spawnsire of Ulamog, Eldrazi Conscription, Urza's Mine, Urza's Power Plant, Urza's Tower, Doubling Cube, Lotus Bloom, Cloudpost.
- Decklist file format: Moxfield-importable, `<quantity> <Card Name>` per line.

---

### Task 1: Write the decklist file

**Files:**
- Create: `deck/zhulodok-bracket3.txt`

**Interfaces:**
- Produces: the canonical 100-card list consumed by all later tasks.

- [ ] **Step 1: Write the file with exactly this content**

```text
1 Zhulodok, Void Gorger

// Lands (37)
18 Wastes
1 Eldrazi Temple
1 Eye of Ugin
1 Shrine of the Forsaken Gods
1 Sanctum of Ugin
1 Ugin's Labyrinth
1 War Room
1 Bonders' Enclave
1 Reliquary Tower
1 Rogue's Passage
1 Tomb of the Spirit Dragon
1 Scavenger Grounds
1 Arcane Lighthouse
1 Urza's Cave
1 Blast Zone
1 Ghost Quarter
1 Sea Gate Wreckage
1 Urza's Mine
1 Urza's Power Plant
1 Urza's Tower

// Ramp (13)
1 Sol Ring
1 Mana Vault
1 Mind Stone
1 Thought Vessel
1 Everflowing Chalice
1 Worn Powerstone
1 Hedron Archive
1 Thran Dynamo
1 Fellwar Stone
1 Basalt Monolith
1 Palladium Myr
1 Coldsteel Heart
1 Forsaken Monument

// Payoffs 7+ (21)
1 Emrakul, the Aeons Torn
1 Kozilek, Butcher of Truth
1 Ulamog, the Infinite Gyre
1 It That Betrays
1 Pathrazer of Ulamog
1 Ulamog's Crusher
1 Spawnsire of Ulamog
1 Kozilek, the Great Distortion
1 Kozilek, the Broken Reality
1 Ulamog, the Ceaseless Hunger
1 Ulamog, the Defiler
1 Emrakul, the Promised End
1 Void Winnower
1 Artisan of Kozilek
1 Flayer of Loyalties
1 Desecrate Reality
1 Rise of the Eldrazi
1 Darksteel Monolith
1 Bane of Bala Ged
1 Desolation Twin
1 Sire of Seven Deaths

// Interaction (12)
1 All Is Dust
1 Ugin's Binding
1 Calamity of the Titans
1 Titan's Presence
1 Warping Wail
1 Not of This World
1 Scour from Existence
1 Spatial Contortion
1 Kozilek's Command
1 Ugin, the Spirit Dragon
1 Ugin, the Ineffable
1 Ugin, Eye of the Storms

// Draw / tutors / glue (8)
1 Conduit of Ruin
1 Endbringer
1 Urza's Incubator
1 Eldrazi Conscription
1 Lightning Greaves
1 Mystic Forge
1 Echoes of Eternity
1 Expedition Map

// Midgame / flex (8)
1 Thought-Knot Seer
1 Oblivion Sower
1 Abstruse Archaic
1 Skittering Cicada
1 Solemn Simulacrum
1 It That Heralds the End
1 Roaming Throne
1 Wandering Archaic // Explore the Vastlands
```

Design notes locked in here: the three owned Urza lands replace three Wastes per the spec's flex rule (Urza's Cave and Expedition Map are both in the list to connect them); Cloudpost, Doubling Cube, Lotus Bloom, Ornithopter stay out (multi-piece/low-impact per spec principle); Echoes of Eternity is a fair doubler here (no Fleshraker-style combo partners in the 99). Cross-checked against the Hydrax "Into the Gray" Zhulodok primer (https://moxfield.com/decks/asvw8mXNmEu3VmtzglQGaA, updated 2026-08): adopted its Blast Zone and Ghost Quarter (lands-as-removal, which the draft lacked) over Temple of the False God, and its cheap-rock philosophy (Fellwar Stone, Coldsteel Heart over Dreamstone Hedron, Kozilek's Channeler) to hit the turn-4/5 commander more reliably.

- [ ] **Step 2: Verify the count is exactly 100**

Run: `grep -v '^//' deck/zhulodok-bracket3.txt | grep -v '^$' | awk '{s+=$1} END {print s}'`
Expected: `100`

- [ ] **Step 3: Commit**

```bash
git add deck/zhulodok-bracket3.txt
git commit -m "Add Zhulodok bracket-3 decklist (unvalidated draft)"
```

---

### Task 2: Validate legality, names, and color identity

**Files:**
- Modify: `deck/zhulodok-bracket3.txt` (only if validation finds errors)

**Interfaces:**
- Consumes: `deck/zhulodok-bracket3.txt` from Task 1.
- Produces: a validated list; later tasks may trust every card name is exact and legal.

- [ ] **Step 1: Load and run deck_validate**

ToolSearch `select:mcp__claude_ai_magic__deck_validate`, then call it with format `commander`, commander `Zhulodok, Void Gorger`, and the 99 (pass the list without the commander line; expand `16 Wastes` as quantity 16).
Expected: legal 100-card deck, no color identity violations, no banned cards.

- [ ] **Step 2: Spot-check oracle texts of the three cards whose function the design assumes but whose text was never fetched this project**

Load `select:mcp__claude_ai_magic__scryfall_card_details` and check:
- `Darksteel Monolith` — confirm it is a castable 7+ mana colorless artifact (cascade fuel) and its EDHREC role matches "payoff".
- `Ugin's Binding` — confirm mana value ≥7 (cascade fuel) and it interacts (bounce/exile).
- `Ugin's Labyrinth` — confirm it taps for {C}{C} when a 7+ power colorless card is imprinted, and the deck has ample imprint fodder (it does: 21 payoffs).

If any card does not match its assumed role, replace it with the next-best EDHREC staple of the same category from the spec's skeleton table and re-run Step 1.

- [ ] **Step 3: Commit (only if changes were made)**

```bash
git add deck/zhulodok-bracket3.txt
git commit -m "Fix decklist validation issues"
```

---

### Task 3: Bracket check

**Files:**
- None (verification gate; decklist edits only on failure).

**Interfaces:**
- Consumes: validated list from Task 2.
- Produces: confirmation the list is bracket 3 with exactly 1 Game Changer.

- [ ] **Step 1: Run spellbook_estimate_bracket**

Load `select:mcp__claude_ai_magic__spellbook_estimate_bracket`, call with commanders `["Zhulodok, Void Gorger"]` and the 99 card names.
Expected: bracket ≤3; Game Changers found: exactly `Mana Vault`; no early 2-card infinite combos flagged. (Basalt Monolith alone is fine — the deck runs no Rings of Brighthearth/Forsaken Monument untap loop... note Forsaken Monument IS in the deck: verify the tool does not flag Basalt Monolith + Forsaken Monument as an infinite combo. It is not one — Monument only adds {C} on tap, Basalt's untap costs 3 generic, netting zero. If the tool flags a real combo anyway, cut the flagged non-Monument piece and substitute Sisay's Ring, then re-run.)

- [ ] **Step 2: Record the result**

Append the bracket-estimate output summary (bracket number, GC list) as a comment block at the bottom of `deck/zhulodok-bracket3.txt`:

```text
// Bracket check YYYY-MM-DD: bracket 3, Game Changers: Mana Vault (1/3)
```

- [ ] **Step 3: Commit**

```bash
git add deck/zhulodok-bracket3.txt
git commit -m "Record bracket-3 validation result"
```

---

### Task 4: Price every card and write the buylist

**Files:**
- Create: `deck/buylist.md`

**Interfaces:**
- Consumes: validated list from Task 2; owned-card list from Global Constraints.
- Produces: `deck/buylist.md` with owned/buy/proxy tables and totals; the buy total figure is reused in Task 6's summary.

- [ ] **Step 1: Fetch EUR prices for every non-owned card**

Load `select:mcp__claude_ai_magic__scryfall_card_price`. For each of the ~78 non-owned names (everything in the decklist except the Global Constraints owned list), fetch prices, batching calls in parallel groups of ~10. Record the `eur` value (fall back to `usd` if `eur` is null, noting it).

- [ ] **Step 2: Apply the buy/proxy rules**

Deterministic rules, in order:
1. Owned → **owned** table (0€). Eldrazi Temple, Eye of Ugin, Sol Ring, all owned titans/fatties, Eldrazi Conscription, the 3 Urza lands.
2. Price < 10€ → **buy**. (Includes all Wastes; count 18 as one line, price × 18.)
3. Price ≥ 25€ → **proxy** (expected: Mana Vault ~74€; anything else that drifted ≥25€ since the spec review).
4. Price 10–25€ → buy in this priority order while running buy-total ≤ 200€, then proxy the rest: Ulamog the Ceaseless Hunger, Ugin's Labyrinth, Void Winnower, Urza's Incubator, Ulamog the Defiler, Emrakul the Promised End, Ugin the Spirit Dragon, Ugin Eye of the Storms, Sire of Seven Deaths, Darksteel Monolith, Rise of the Eldrazi, Kozilek the Broken Reality, Roaming Throne (order = impact ranking from the spec review).
5. Sanity: if any card prices ≥100€, STOP — it violates the spec; replace it with the next-best same-category staple (flag in the final report).

- [ ] **Step 3: Write `deck/buylist.md`**

Structure (fill with real data):

```markdown
# Zhulodok Deck Buylist — 2026-08-17 prices (Cardmarket EUR via Scryfall)

## Owned (0€)
| Card | Note |
|---|---|
| Eldrazi Temple | from collection |
...

## Buy (total: XX.XX€ / 200€ budget)
| Card | EUR |
|---|---|
| All Is Dust | 3.78 |
...

## Proxy (would cost XX.XX€ — print these)
| Card | EUR | Reason |
|---|---|---|
| Mana Vault | 74.25 | ≥25€ |
...
```

- [ ] **Step 4: Verify totals**

Recompute the buy-table sum manually (`awk` over the table or by hand) and confirm it is ≤200€ and matches the stated total.
Run: `grep -c '^|' deck/buylist.md` sanity check that owned+buy+proxy rows = 82 unique names (99 cards − 17 duplicate Wastes = 82 lines, plus table header rows).

- [ ] **Step 5: Commit**

```bash
git add deck/buylist.md
git commit -m "Add priced buylist with owned/buy/proxy split"
```

---

### Task 5: Deck health analysis

**Files:**
- Modify: `deck/zhulodok-bracket3.txt` and `deck/buylist.md` (only if analysis forces swaps)

**Interfaces:**
- Consumes: validated, priced list.
- Produces: final tuned list.

- [ ] **Step 1: Run deck_analysis**

Load `select:mcp__claude_ai_magic__deck_analysis`, pass the full decklist with commander.
Expected healthy ranges for this archetype: ~37 lands, 13+ ramp sources, average mana value high (5+ is fine — this deck is intentionally top-heavy), interaction ≥10.

- [ ] **Step 2: Judge flags with archetype context**

deck_analysis will likely warn "curve too high" — that is by design (cascade payoffs must be 7+; ignore). Act only on: fewer than 35 lands flagged, ramp <12, interaction <8, or specific dead-card callouts. If a swap is needed, swap within the same category using the spec's skeleton alternatives, then re-run Task 2 Step 1 (deck_validate) and update `deck/buylist.md` prices for changed cards.

- [ ] **Step 3: Commit (only if changes were made)**

```bash
git add deck/
git commit -m "Tune decklist after health analysis"
```

---

### Task 6: Bracket-4 upgrade module doc

**Files:**
- Create: `deck/bracket4-upgrades.md`

**Interfaces:**
- Consumes: final list from Task 5; buy total from Task 4.
- Produces: standalone upgrade doc; no later task depends on it.

- [ ] **Step 1: Write `deck/bracket4-upgrades.md` with this content, updating prices via scryfall_card_price for the listed additions**

```markdown
# Bracket 4 Upgrade Module

Apply these ~10 swaps to move the deck from bracket 3 to 4. Prices are
Cardmarket EUR at 2026-08-17; ≥25€ items are proxy candidates per the
budget policy. Nothing ≥100€ is listed.

## Combo / explosive package (in)
| Add | Price | Why |
|---|---|---|
| Glaring Fleshraker | ~2€ | With Echoes of Eternity (already in deck): each colorless cast becomes 2 triggers, drains + tokens; near-combo turns |
| Kozilek's Unsealing | ~3€ | Every big cast draws 3; chains with cascade into more casts |
| Rings of Brighthearth | ~15€ | Copies fetch/draw activations; WARNING: with Basalt Monolith = infinite colorless mana (2-card combo — this is exactly what pushes to bracket 4) |
| Grim Monolith | — | EXCLUDED: ~130€ violates price cap. Listed so nobody re-adds it. |
| Metalworker | ~30€ (proxy) | Reveals a grip of artifacts for huge mana bursts |
| Urza's Saga | ~30€ (proxy) | Tutors Expedition Map/Sol Ring, makes construct blockers |
| Sensei's Divining Top | ~25€ (proxy) | Sets up cascade hits — with Mystic Forge, near-draw-engine |

## Corresponding cuts (out)
| Cut | Why |
|---|---|
| Ghost Quarter | Land slot goes to Urza's Saga |
| Sea Gate Wreckage | Slowest draw source |
| Palladium Myr | Fragile ramp, replaced by Metalworker |
| Spatial Contortion | Narrowest interaction |
| Scour from Existence | Overcosted; combo turns end games instead |
| Solemn Simulacrum | Value too slow for bracket 4 |

## Also raises the ceiling
- Second/third Game Changer slots are free: The One Ring and Ancient Tomb
  remain excluded by the ≥100€/never-buy rule; there is no cheap GC worth
  adding — bracket 4 comes from the combo package, not GC count.
- This module is the natural pivot point to the future Ulalek, Fused
  Atrocity build (see TODO.md): Fleshraker/Unsealing/Echoes carry over 1:1.
```

- [ ] **Step 2: Commit**

```bash
git add deck/bracket4-upgrades.md
git commit -m "Add bracket-4 upgrade module"
```

---

### Task 7: Final verification and summary

**Files:**
- Modify: `TODO.md` (tick nothing — Ulalek stays open; add link to deliverables)

**Interfaces:**
- Consumes: all deliverables.

- [ ] **Step 1: Verification pass (superpowers:verification-before-completion)**

Re-run the count command from Task 1 Step 2 (expect 100), confirm all four deliverable files exist (`ls deck/ docs/superpowers/specs/ docs/superpowers/plans/`), confirm buy total ≤200€ as stated in `deck/buylist.md`, confirm git status is clean after commits.

- [ ] **Step 2: Update TODO.md**

Append under the Ulalek item: `- Deliverables from Zhulodok build: deck/zhulodok-bracket3.txt, deck/buylist.md, deck/bracket4-upgrades.md`

- [ ] **Step 3: Commit**

```bash
git add TODO.md
git commit -m "Link Zhulodok deliverables from TODO"
```

- [ ] **Step 4: Report to user**

State: final deck size (100), bracket estimate result, buy total vs 200€, number of proxies, and any substitutions made during validation — with no hedging if all checks passed, or the exact failure if not.
