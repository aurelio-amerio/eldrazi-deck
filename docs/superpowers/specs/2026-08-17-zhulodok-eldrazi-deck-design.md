# Zhulodok, Void Gorger — "Double Cascade Titans" Commander Deck

**Date:** 2026-08-17
**Status:** Approved design, pending implementation
**Commander:** Zhulodok, Void Gorger ({5}{C}, colorless)
**Target:** Commander bracket 3, legal per current ban list, with a documented bracket-4 upgrade path

## Goal

Build a colorless Eldrazi Commander deck around Zhulodok, Void Gorger for ~200€ of purchases, using the owned collection (`archidekt-collection-export-2026-08-17.csv`) and printed proxies for expensive staples. Nothing priced over ~100€ is included at all (even as proxy — the user would never buy it).

## Game plan

Ramp with colorless mana rocks and lands to 7+ mana. Zhulodok gives every 7+ mana colorless spell cast from hand **cascade, cascade** — each titan chains into two free spells (ramp, removal, or more threats). Win through annihilator attacks and accumulated 2-for-1 card advantage. No infinite combos; interaction is targeted exile and one board wipe class (All Is Dust).

## Card evaluation principle

Singleton format: prefer cards impactful on their own or with just the commander. Multi-piece land synergies (Urza Tron, Cloudpost) are unreliable in a 99-card singleton deck and are excluded from the core (at most flex filler). (Data point for honesty: ~93% of EDHREC Zhulodok lists do run the Urza lands, accepting the taps-for-1 floor; the exclusion here is a deliberate preference for standalone impact, not an oversight.) The valuable owned cards are the standalone ones: Eldrazi Temple, Eye of Ugin, Sol Ring, the titans, It That Betrays, Eldrazi Conscription.

## Deck skeleton (99 cards)

| Category | Count | Notes |
|---|---|---|
| Lands | ~37 | Wastes core + standalone utility: Eldrazi Temple, Eye of Ugin, Shrine of the Forsaken Gods, Sanctum of Ugin, War Room, Bonders' Enclave, Reliquary Tower, Rogue's Passage |
| Ramp artifacts | ~14 | Sol Ring, Mind Stone, Thought Vessel, Everflowing Chalice, Worn Powerstone, Hedron Archive, Thran Dynamo, Dreamstone Hedron, Basalt Monolith, Palladium Myr, Kozilek's Channeler, Forsaken Monument, … |
| Payoffs (7+ mana, cascade fuel) | ~22 | Owned: Emrakul the Aeons Torn, Kozilek Butcher of Truth, Ulamog the Infinite Gyre, It That Betrays, Pathrazer of Ulamog, Ulamog's Crusher, Spawnsire. Add (EDHREC inclusion in parens): Kozilek the Great Distortion (92%), Ulamog the Ceaseless Hunger (78%), Flayer of Loyalties (77%), Artisan of Kozilek (76%), Void Winnower (67%), Desecrate Reality (74%), Rise of the Eldrazi (80%), Darksteel Monolith (88%), Bane of Bala Ged (60%), Oblivion Sower (58%), Desolation Twin, Sire of Seven Deaths (49%), … |
| Interaction | ~10 | All Is Dust, Ugin's Binding, Titan's Presence, Warping Wail, Not of This World (85% inclusion), Scour from Existence, Calamity of the Titans (64%), Ugin the Spirit Dragon, Ugin the Ineffable |
| Draw / tutors / glue | ~8 | Conduit of Ruin, Endbringer, Urza's Incubator, Eldrazi Conscription (owned), Lightning Greaves, Mystic Forge (81%), Echoes of Eternity (78%, 0.75€ — fair value doubler here since the deck runs no combo partners for it) |
| Midgame Eldrazi / flex | ~8 | Standalone 4–6 mana bodies that bridge to the titans: Thought-Knot Seer, Oblivion Sower (if counted here rather than payoffs), Abstruse Archaic (47%), Skittering Cicada (73%), Solemn Simulacrum, Roaming Throne, … |

Counts are targets, not hard constraints; they sum to 99 (37+14+22+10+8+8). Final counts settled during implementation.

Cascade density note: keep the count of 7+ mana spells high enough (~22) that cascades regularly hit another payoff, while cascade hits below 7 (ramp/interaction) are still fine.

## Bracket 3 compliance

- **Game Changers (max 3):** Mana Vault only (proxy, ~74€). Ancient Tomb was cut on review: at 96€ EUR / $135 USD it sits at the 100€ exclusion line and fails the "would realistically buy later" test. Other GCs seen in Zhulodok lists (The One Ring, Grim Monolith, Mishra's Workshop) all fail the price cap; Field of the Dead is cheap but only 8% inclusion and anti-synergizes with a Wastes-heavy mana base. Two GC slots intentionally unused.
- No mass land denial, no chained extra turns, no early-game 2-card infinite combos, tutors kept light (Eye of Ugin, Sanctum of Ugin, Conduit of Ruin are on-theme and slow).
- Fully legal per the current Commander ban list (the reference deck's Jeweled Lotus is banned and excluded).

## Budget policy

- **Owned:** 0€ (from collection CSV).
- **Buy (~200€ ceiling):** cards ≤10€ are bought freely (the bulk of the deck: All Is Dust 3.78€, Forsaken Monument 3.39€, Thran Dynamo 1.77€, Kozilek the Great Distortion 4.63€, etc.).
- **Mid-tier 10–25€ (decided case by case at buylist time):** price review found ~10 desirable cards in this band (Ulamog the Ceaseless Hunger 18€, Sire of Seven Deaths 21€, Emrakul the Promised End 20€, Darksteel Monolith 20€, Rise of the Eldrazi 19.5€, Urza's Incubator 15€, Ulamog the Defiler 15€, Void Winnower 14€, Ugin's Labyrinth 15.6€, Ugin the Spirit Dragon 11€) — buying all would eat ~170€ alone. The buylist buys the highest-impact ones up to the 200€ ceiling and proxies the rest.
- **Proxy:** cards ~15–100€ that don't make the buy cut (e.g. Mana Vault 74€). These remain realistically buyable later.
- **Excluded entirely:** anything at/over ~100€ (Ancient Tomb 96€ EUR falls here in practice).

## Bracket 4 upgrade module (documented only, not built)

~10–15 swaps, written as a separate doc:
- Combo lines: Echoes of Eternity, Glaring Fleshraker-style packages (win-the-turn potential).
- More fast mana and harder tutors.
- This is also the natural pick-up point for the **future Ulalek, Fused Atrocity exploration** (tracked in TODO.md): same colorless core, 5-color-identity commander, spell/trigger copying.

## Deliverables

1. This design doc.
2. `deck/zhulodok-bracket3.txt` — the 99+1 list in Moxfield-importable format (`1 Card Name` per line).
3. `deck/buylist.md` — priced list split into **owned / buy / proxy**, with total cost vs 200€ budget.
4. `deck/bracket4-upgrades.md` — the upgrade module.
5. `TODO.md` — future work: Ulalek deck exploration.

## Validation

- Deck validates as legal 100-card Commander deck (deck_validate MCP tool).
- Game Changer count ≤ 3, bracket estimate confirms 3 (spellbook_estimate_bracket).
- Buylist total ≤ 200€ using current EUR prices (Scryfall/Cardmarket).
- Mana curve / land count sanity-checked with deck_analysis.
