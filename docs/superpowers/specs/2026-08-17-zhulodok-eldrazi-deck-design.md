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

Singleton format: prefer cards impactful on their own or with just the commander. Multi-piece land synergies (Urza Tron, Cloudpost) are unreliable in a 99-card singleton deck and are excluded from the core (at most flex filler). The valuable owned cards are the standalone ones: Eldrazi Temple, Eye of Ugin, Sol Ring, the titans, It That Betrays, Eldrazi Conscription.

## Deck skeleton (99 cards)

| Category | Count | Notes |
|---|---|---|
| Lands | ~37 | Wastes core + standalone utility: Eldrazi Temple, Eye of Ugin, Shrine of the Forsaken Gods, Sanctum of Ugin, War Room, Bonders' Enclave, Reliquary Tower, Rogue's Passage |
| Ramp artifacts | ~14 | Sol Ring, Mind Stone, Thought Vessel, Everflowing Chalice, Worn Powerstone, Hedron Archive, Thran Dynamo, Dreamstone Hedron, Basalt Monolith, Palladium Myr, Kozilek's Channeler, Forsaken Monument, … |
| Payoffs (7+ mana, cascade fuel) | ~22 | Owned: Emrakul the Aeons Torn, Kozilek Butcher of Truth, Ulamog the Infinite Gyre, It That Betrays, Pathrazer of Ulamog, Ulamog's Crusher, Spawnsire. Add: Ulamog the Ceaseless Hunger, Kozilek the Great Distortion, Void Winnower, Oblivion Sower, Artisan of Kozilek, Bane of Bala Ged, Desolation Twin, Sire of Seven Deaths, … |
| Interaction | ~10 | All Is Dust, Ugin's Binding, Titan's Presence, Warping Wail, Not of This World, Scour from Existence, Ugin the Spirit Dragon, Ugin the Ineffable |
| Draw / tutors / glue | ~8 | Conduit of Ruin, Endbringer, Urza's Incubator, Eldrazi Conscription (owned), Lightning Greaves |
| Midgame Eldrazi / flex | ~8 | Standalone 4–6 mana bodies that bridge to the titans: Thought-Knot Seer, Oblivion Sower (if counted here rather than payoffs), Wastescape Battlemage, Abstruse Archaic, Roaming Throne, … |

Counts are targets, not hard constraints; they sum to 99 (37+14+22+10+8+8). Final counts settled during implementation.

Cascade density note: keep the count of 7+ mana spells high enough (~22) that cascades regularly hit another payoff, while cascade hits below 7 (ramp/interaction) are still fine.

## Bracket 3 compliance

- **Game Changers (max 3):** Ancient Tomb and Mana Vault (both as proxies, ~50-60€ each, under the 100€ cap). Third slot intentionally open.
- No mass land denial, no chained extra turns, no early-game 2-card infinite combos, tutors kept light (Eye of Ugin, Sanctum of Ugin, Conduit of Ruin are on-theme and slow).
- Fully legal per the current Commander ban list (the reference deck's Jeweled Lotus is banned and excluded).

## Budget policy

- **Owned:** 0€ (from collection CSV).
- **Buy (~200€ ceiling):** the deck's backbone — cards roughly ≤15€ each. Exact priced buylist is an implementation deliverable; estimated well under budget since colorless staples are mostly cheap.
- **Proxy:** only cards ~15–100€ (e.g. Ancient Tomb, Mana Vault, possibly a pricier titan). These remain realistically buyable later.
- **Excluded entirely:** anything over ~100€.

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
