# eldrazi-deck

MTG Commander (EDH) deck-building workspace for Eldrazi decks. See `CLAUDE.md` for
repo conventions and the deck-analysis procedure; decklists and analysis live in `deck/`.

## Power-level tracking

Recorded so upgrades can be checked against a fixed baseline. Numbers come from the
goldfish-sim procedure in `CLAUDE.md` (20k games/list, simple mulligan keeping 2–5 lands,
land + greedy rocks/cost-reducers per turn; Ancient Tomb/Eldrazi Temple modeled as 2 mana,
Eye of Ugin as a −2 reducer; tutors, The One Ring and Urza's Saga are NOT modeled, so real
combo assembly is faster than shown). **Only compare numbers produced by the same script in
the same run** — the sim is rebuilt per analysis session and small modeling choices shift
absolute values; the b3-vs-b4 delta within a row is the meaningful signal.

### 2026-08-21 baseline (same-script run, after the EDHREC swaps in b4)

| Metric | Ulalek bracket 3 | Ulalek bracket 4 |
|---|---|---|
| Commander castable | median T5, 34% by T4 | median T5, 38% by T4 |
| 7 effective mana | median T7, 43% by T6 | median T7, 43% by T6 |
| First MV7+ threat (mana + card in hand) | median T8, 60% by T8 | median T9, 44% by T8 |
| Combo line online (natural draws + 2 spare mana) | 1% by T6, 3% by T8, 4% by T10 | 6% by T6, 12% by T8, 19% by T10 |
| Infinite combo lines (Commander Spellbook, included) | 2 | 13 |
| Game Changers (Feb-2026 list) | 3 (at the bracket-3 cap) | 10 |

Reading: the b4 list trades haymaker velocity (median T9 vs T8, a deliberate design
choice — 4 fewer big threats) for a 4× faster combo clock and denser tutors. The
bracket-3 benchmark of "average table win ~T10" from the 2026-08-19 analysis is the
context: b4 assembles a win line before that in ~1 game in 5 off natural draws alone,
and materially more often once the black tutors, Wishclaw and The One Ring are counted.

### 2026-08-21 EDHREC swap check (b4, pre- vs post-swap)

The four EDHREC-driven swaps (Mystic Forge, Talisman of Dominance, Secluded Courtyard,
Sire of Stagnation — see the decision log in `deck/ulalek-bracket4.txt`) are **sim-neutral**:
they touch no combo piece (still exactly 13 Spellbook lines), no rock speed (Talisman
replaces Fellwar at the same cost/production) and no haymaker count. Their gain is in what
the goldfish sim cannot measure: card-advantage engines (Forge, Sire), guaranteed tutor/
counterspell pips instead of opponent-dependent Fellwar mana, and painless fixing in place
of a painland in the deck's two shallowest colors. Power change: small increase in
consistency and staying power; speed unchanged.
