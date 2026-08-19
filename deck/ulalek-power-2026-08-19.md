# Ulalek power-level assessment — 2026-08-19

20,000-game Monte Carlo goldfish sim of `deck/ulalek-bracket3.txt` (post speed/resilience pass),
extended beyond mana milestones: threats are cast and attack, Ulalek's {C}{C} copy doubles Eldrazi
bodies, Echoes of Eternity copies colorless MV-7+ spells and doubles Kozilek's Unsealing draws,
The Great Henge draws per body, and damage is dealt to three 40-life opponents. The
Ulalek + Echoes + Unsealing infinite counts as a win when assembled with an Eldrazi spell and
{C}{C} spare. (`spellbook_estimate_bracket` not used — known broken.)

Not modeled, and the direction each omission biases the result:
annihilator/Ulamog mill-20/Zhulodok cascade/Ugin walkers (sim **understates** speed),
opponent removal and interaction (sim **overstates** it). These roughly cancel.

## Results

| Metric | Median | 25th/75th | by T8 | by T10 | by T12 |
|---|---|---|---|---|---|
| First opponent dead | T10 | T8 / T11 | 28% | 64% | 85% |
| Table cleared (all 120 damage solo) | T13 | T12 / T15 | 1% | 10% | 36% |

Combo wins (Ulalek + Echoes + Unsealing assembled): **3.2%** of games, median T12 — the combo is a
garnish, not the game plan, consistent with its "allowed late-game line" ruling.

## Verdict: solid, upper-middle **bracket 3**

- Goldfish first-kill T8–11 sits squarely in the upgraded-bracket-3 band (precon-level decks
  goldfish ~T12–14; bracket 4 ~T6–8; cEDH T3–5). First kill by T6 happens in 3% of games —
  comfortably inside the official "games unlikely to end before turn 6-ish" description.
- Game Changers: 3 (Mana Vault, Ancient Tomb, Crop Rotation) — exactly the bracket-3 cap.
- Combos: only the two adjudicated late-game lines; the fast early lines were cut at build time.
- Real-table expectation: between the two rows above, since opponents damage each other — matching
  the observed "average win around turn 10" from actual games.

To push toward bracket 4 the levers would be: unlimited Game Changers (Grim Monolith, The One
Ring), tutors for the Echoes+Unsealing combo (raising that 3.2% assembly rate), and free
interaction — i.e. the same direction as `deck/bracket4-upgrades.md` takes the Zhulodok list.
