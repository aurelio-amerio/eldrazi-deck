# Ulalek, Fused Atrocity — Deck Primer (Bracket 3 & Bracket 4)

*Written 2026-08-24. Covers `deck/ulalek-bracket3.txt` and `deck/ulalek-bracket4.txt`. Combos verified against Commander Spellbook on both exact lists on this date; win-turn numbers come from a fresh 20,000-game Monte Carlo simulation of each list (methodology at the bottom).*

*See also `ulalek-b3-playbook.md` (2026-08-26) — the bracket-3 play guide: non-infinite damage packages, tutor targets, deployment priorities, and stack tricks.*

---

## 1. What this deck is

Ulalek costs `{C/W}{C/U}{C/B}{C/R}{C/G}` — five hybrid pips, each payable with **any** color or true colorless. In practice: any five mana casts it (even Fellwar Stone helps), and its five-color identity legalizes devoid cards that Zhulodok can never play. Its text is the whole deck:

> Whenever you cast an **Eldrazi spell**, you may pay `{C}{C}`. If you do, **copy all spells you control**, then **copy all other activated and triggered abilities you control**.

Two consequences drive every line in the primer:

1. **Every Eldrazi spell is double-dipped.** Pay `{C}{C}` and the spell is copied (a permanent spell copy becomes a token) *and* every cast trigger on the stack is duplicated — Ulamog's exile, Kozilek's draw, World Breaker's Naturalize, Elder Deep-Fiend's tap-four becomes tap-eight.
2. **Copies are not cast.** Token copies don't retrigger "when you cast" abilities. That is why the infinite lines all need a *trigger doubler/copier* (Echoes of Eternity, Strionic Resonator) plus a *Spawn-token payoff* that converts each loop iteration into more `{C}` than the `{C}{C}` it costs.

**Version identity, in one line each:**

- **Bracket 3** — Eldrazi battlecruiser. Wins by combat with doubled haymakers; its two combo lines are late-game garnish (combo decides <2% of goldfish games).
- **Bracket 4** — same battlecruiser chassis, but the win condition moves to a dense 13-line combo web plus black tutors, fast mana, and free interaction. Combat becomes the fallback plan.

---

## 2. How the decks win (simulation-backed)

20,000 goldfish games per list, same engine for both (details §8). "Combo online" is strict: all pieces deployed, Ulalek on the battlefield where required, a castable Eldrazi spell in hand where required, and the full activation mana spare — not just "pieces in play".

| Metric | Bracket 3 | Bracket 4 |
|---|---|---|
| Ulalek cast | median **T4** (87% by T6) | median **T4** (88% by T6) |
| 7 effective mana | median **T6** | median **T6** |
| First MV7+ haymaker cast | median **T8** (50% by T8) | median T11 (34% by T8) |
| First opponent dead (combat) | median **T9** (80% by T10) | median **T10** (65% by T10) |
| Table cleared solo (120 dmg) | median **T13** | median T14 |
| Win-combo fully online | 0.7% by T10 | **12% by T10, 18% by T12** |
| Infinite-mana line online | 2.3% by T10 | 4.5% by T10 |
| Win mode split (by T20) | **98% combat** / 2% combo | **76% combat / 22% combo** |

Read the b4 combo share as a **floor**: the sim draws no extra cards (Kozilek's Unsealing draw-3, The One Ring, Kozilek refill and Mystic Forge top-casts are all unmodeled) and plays tutors greedily rather than sequencing them. The earlier, looser-metric pass (pieces + 2 mana, 2026-08-21) put combo assembly at 17% by T6 / 28% by T8. At a real table:

- **B3 plan:** ramp T1–4 → Ulalek T4 → convert 7+ mana into doubled haymakers T6–8 → first kill ~T9, table dead T12–14. You are the archenemy from T6; the combo lines exist only so a stalled late game has an exit.
- **B4 plan:** identical opening, but from T5 on the tutors assemble a two-card copier+payoff pair around Ulalek; a protected combo turn typically lands **T6–9**, with combat pressure covering the games where the web is disrupted. This is the deck's real primary win mode — treat combat as plan B.

---

## 3. Notable combos

### Shared by both versions

**Ulalek + Echoes of Eternity + Kozilek's Unsealing** → infinite Spawn tokens, infinite `{C}`, infinite ETB/death triggers, and (via Unsealing's second mode) drawing the deck.
Cast any Eldrazi creature with **MV 4–6** with `{C}{C}` spare. Echoes doubles both Ulalek's and Unsealing's triggers. Resolve one Ulalek trigger paying `{C}{C}`: it copies the spell *and* all other triggers on the stack. The doubled Unsealing triggers make **four** Spawns; sacrifice two to repay `{C}{C}` for the copied Ulalek trigger; each cycle nets +2 Spawns and re-copies everything. Convert: infinite Spawn mana → cast your whole deck (Unsealing draws 3 per 7+ creature), or just present an arbitrarily large board. *MV 4–6 Eldrazi in the 99 to start it: Thought-Knot Seer, Sowing Mycospawn, Conduit of Ruin, a recast Ulalek (MV5) — plus Azlask in b3, Spawn-Gang Commander and Writhing Chrysalis in b4. (Elder Deep-Fiend is MV8 even via emerge, and Ultima/Skittering Cicada aren't Eldrazi.)*

**Basalt Monolith + Forsaken Monument** → infinite `{C}`.
Monument's "tap for `{C}` adds an extra `{C}`" makes Basalt tap for 4 and untap for 3. Outlets: cast everything in hand, Kozilek the Great Distortion (refill to 7 and keep casting), huge Kozilek's Command / Blast Zone / Eye of Ugin activations, Eldrazi Displacer machine-gun blinks. **Not an instant win** — you still need a payoff, which is why the sim tracks it separately.

### Bracket 4 only — the combo web

The web is a grid: **Ulalek + one copier + one payoff** = infinite. Almost any pairing works (13 Spellbook-verified lines), which is the design: redundancy instead of cEDH tutor density.

| | **Echoes of Eternity** (passive) | **Strionic Resonator** (needs `{2}` + tap) |
|---|---|---|
| **Kozilek's Unsealing** | ✅ infinite Spawns + draw the deck | ✅ same |
| **Spawn-Gang Commander** | ✅ **infinite damage** (self-contained: it *is* the Eldrazi spell) | ✅ infinite damage — *the reference cEDH list's main line* |
| **Glaring Fleshraker** | ✅ **infinite damage** (1 to each opponent per Spawn) | ✅ |
| **Writhing Chrysalis** | ✅ infinite Spawns + counters | ✅ |

- **The cleanest kill: Ulalek + Resonator + Spawn-Gang Commander** (`{5}{C}{C}{R}{R}` all-in from hand): cast Spawn-Gang, Resonator copies Ulalek's trigger, the copy makes a token Spawn-Gang + 3 Spawns per loop; sacrifice Spawns to Spawn-Gang's ability for **infinite damage** with the loop's leftover mana.
- **Fleshraker turns *any* line lethal**: every Spawn that enters pings all three opponents, so "infinite tokens" lines become infinite damage with Fleshraker merely on the battlefield.
- Fringe redundancy: **Ulalek + Writhing Chrysalis + Eldritch Immunity** and **Ulalek + Writhing Chrysalis + Abstruse Archaic** (Archaic's `{1},{T}` copies Ulalek's trigger like a one-shot Resonator; Rings of Brighthearth can double the Archaic/Resonator activation).
- **Food Chain + Eternal Scourge** → infinite creature-only mana of any color: exile Scourge for 4 mana, recast it from exile for 3, repeat. **+ Glaring Fleshraker = immediate infinite damage** — this is the deck's fastest line (~T4 is realistic with a tutor). Note Scourge exiles itself if an opponent targets it — that's upside here.
- **Infinite mana back-ups:** Basalt + Rings of Brighthearth (copy the untap), Grim Monolith + Rings + Forsaken Monument. Same outlets as above; with infinite `{C}`, Ulalek copies every spell you cast for the rest of the turn.

### Combo-turn protection (b4)

Lead with **Cavern of Souls naming Eldrazi** (the trigger spell can't be countered), keep **Fierce Guardianship / Deflecting Swat / Stubborn Denial** up (Denial's ferocious mode is nearly always on), and remember **Skittering Cicada gives all your colorless spells flash** — you can combo on an opponent's end step. Deflecting Swat also retargets the removal spell aimed at Ulalek or Echoes.

---

## 4. Notable interactions (non-infinite)

**The `{C}{C}` copy menu** — what doubling is actually worth on each spell (both lists unless noted):

- **Ulamog, the Ceaseless Hunger:** exile **four** permanents (both cast triggers resolve even though the token copy dies to the legend rule).
- **Ulamog, the Defiler:** two "exile top half of library" triggers — aim at two different opponents, or halve one player twice (¾ of their deck).
- **Kozilek, the Great Distortion / Broken Reality:** double refill/draw triggers.
- **Elder Deep-Fiend:** flash, tap **eight** permanents on cast — fizzle an attack or tap three lands each on two opponents' upkeeps. Emerge off a Spawn token is a discount, not a requirement.
- **World Breaker:** exile two artifacts/enchantments/lands; recurs itself from the graveyard for `{2}{C}` + a land.
- **Emrakul, the World Anew:** steal **two** players' boards for the turn (madness for six `{C}` is the normal casting mode).
- **Kozilek's Command:** X instant — the copy keeps X, so all four modes scale double.
- **Ugin's Binding:** bounce two nonland permanents; later, *any* colorless 7+ spell exiles it from the graveyard for a **one-sided mass bounce** — this triggers off every haymaker you cast for the rest of the game.
- **Desecrate Reality:** exile up to two even-MV permanents per opponent + double Adamant reanimation.
- **Zhulodok, Void Gorger** in the 99: your 7+ colorless spells from hand get **cascade, cascade** — and Ulalek's trigger copies the cascade *triggers* too. A single Ulamog with both legends out is four cascades deep.

**Engine & utility interactions:**

- **Sanctum of Ugin** sacrifices on any colorless 7+ spell to fetch **any colorless creature** to hand — in b3 it chains haymaker → haymaker; in b4 it fetches *combo creatures* (Glaring Fleshraker, Spawn-Gang Commander, Eternal Scourge are all colorless).
- **Eye of Ugin** is −2 on every colorless Eldrazi spell (Temple/Tomb-class acceleration) and its late-game `{7},{T}` activation is a repeatable colorless-creature tutor.
- **Conduit of Ruin** stacks its top-of-library tutor with **Mystic Forge** (b4): fetch the 7+ creature, cast it off the top — often the same turn, at −2−2 with its own discount plus Incubator/Herald.
- **Kozilek's Unsealing** is the deck's best engine even off-combo: MV 4–6 creatures make 2 Spawns (ramp), 7+ creatures draw 3. With Echoes (b3+b4) every trigger is doubled — 4 Spawns or draw 6.
- **Eldrazi Displacer + Thought-Knot Seer:** repeatable ETB hand-strip (TKS's exile is an ETB, not a cast trigger, so blinking works). Displacer also resets **Ulamog, the Defiler's** +1/+1 counters to the current biggest exile MV, untaps your team out of Elder Deep-Fiend mode, or blanks attackers. Note: most Eldrazi haymakers have *cast* triggers — Displacer does **not** rebuy those.
- **All Is Dust** sacrifices *colored* permanents — nearly your whole board is devoid/colorless and survives. Caveat (adjudicated): it also pops your own **Imprisoned in the Moon** and (b3) colored auras — time the sweeper before, not after, the moon-lock.
- **Warping Wail** counters *sorceries* — most board wipes at these tables — and Ugin, the Spirit Dragon's −X kills a moon'd commander permanently… but see the Imprisoned caveat above.
- **b3 only — Path of Annihilation + Azlask:** Path gives every Eldrazi "{T}: add any color", which is what makes Azlask's `{W}{U}{B}{R}{G}` mass-pump/annihilator activation actually reachable in a colorless deck.
- **b3 only — From Beyond:** upkeep Spawn ramp that late-game sacrifices into a tutor for **any Eldrazi card** — including **Echoes of Eternity** (a Kindred Eldrazi enchantment), i.e. half the combo; it cannot fetch Kozilek's Unsealing (devoid, but not an Eldrazi card).
- **Ugin's Labyrinth** needs a 7+ colorless card imprinted from hand — with 20+ hits in both lists it's usually a Temple, but a fast hand with no big card makes it a Wastes; don't fetch it when your hand is all small.
- **Eldritch Immunity** overloaded (`{4}{C}`) gives the whole team protection from each color: your Eldrazi ignore colored blockers, targeted removal, and colored sweepers on the swing turn.

---

## 5. Top-priority cards

**Cards the deck cannot function without (protect these, in order):**

1. **Ulalek** — every plan runs through the copy trigger. Give it **Lightning Greaves** the turn it lands; it eats every removal spell at the table. (Not of This World in b3 can't protect a naked Ulalek — its free mode needs power 7.)
2. **Echoes of Eternity** — the single most powerful permanent in either list: doubles every trigger and copies every colorless spell, combo or not. In b4 it is the #1 tutor target; opponents who know the deck kill it on sight.
3. **Kozilek's Unsealing** — the draw engine that keeps the hand full; quietly wins long games on its own.
4. **Eye of Ugin / Ancient Tomb / Eldrazi Temple** — the 2-mana lands are the difference between T4 and T6 Ulalek; Wasteland/strip effects aimed at you go here.
5. **b4: Mystic Forge + The One Ring** — the grind engines that refuel a disrupted combo turn.
6. **Forsaken Monument** (both) — +2/+2 team-wide, mana doubling on `{C}`, and half of an infinite-mana line.

**What opponents will (correctly) target:** Echoes, Ulalek, Forsaken Monument, and in b4 Food Chain and Resonator. Sequence so that you deploy the *second* combo piece the turn you go off, not turns earlier.

**Opening hand priorities (both lists):** 2–4 lands including a Tomb/Temple-class land or a 2+ mana rock, plus either a cost reducer or an engine piece (Unsealing / Shadow in the Warp / b4 tutor). A hand that casts Ulalek by T4 with one engine behind it is a keep; a hand of five haymakers is not — this deck mulligans for its curve, not its top end.

---

## 6. What to retrieve first (tutor & fetch priorities)

**Land tutors — Crop Rotation (instant!), Sylvan Scrying, Sowing Mycospawn:**

| Situation | Get |
|---|---|
| T1–3, developing | **Eye of Ugin** (best), else Eldrazi Temple / Ancient Tomb |
| The turn before a 7-drop | **Sanctum of Ugin** (converts the haymaker into the next one — or a combo creature in b4) |
| Blue player holding mana | **Cavern of Souls** (name Eldrazi) |
| Problem permanent / recurring lands | Blast Zone / **Wasteland** |
| b4, artifact plan online | **Urza's Saga** (→ Sol Ring, Mana Vault, Lotus Petal, Mox Diamond) |

Crop Rotation at instant speed means: end-of-turn Sanctum with a haymaker in hand, or an on-the-spot Cavern in response to a counter-heavy board state. Sowing Mycospawn kicked also Strip-Mines a problem land (Cabal Coffers, Gaea's Cradle, an opposing Eye).

**b4 black tutors — Demonic / Vampiric / Wishclaw.** Fetch in this order:

1. **Ulalek out + any payoff already in play** → **Echoes of Eternity** (wins with any Eldrazi spell in hand).
2. **Ulalek out + Echoes out** → cheapest payoff: **Kozilek's Unsealing** (also an engine if the combo is broken up) or **Spawn-Gang Commander** (spell + payoff in one card, immediate kill with `{C}{C}` spare).
3. **No board yet, T2–3** → fast mana (Sol Ring / Mana Vault) or **Food Chain** (then Eternal Scourge assembles a mana engine that Sanctum/Eye converts into Fleshraker for the kill).
4. **Combo repeatedly disrupted** → **The One Ring** and grind; the web is redundant enough to reassemble.

Vampiric Tutor is best end-of-turn before your combo turn; Wishclaw wants to be activated *on the turn you win* so the opponents' borrow never happens.

**Creature tutors (both lists):** Conduit of Ruin only fetches **MV 7+ colorless creatures** — default to **Ulamog, the Ceaseless Hunger** (removal + clock) or **Kozilek, the Great Distortion** (refill); in b4 with Mystic Forge out, the topped card is castable immediately. Sanctum of Ugin and Eye of Ugin fetch *any* colorless creature: b3 chains into the next haymaker; b4 fetches **Glaring Fleshraker → Spawn-Gang Commander → Eternal Scourge** ahead of vanilla threats when a combo is within reach.

---

## 7. Piloting notes by phase

**T1–3 (both):** land, rock, reducer. Every mana source is colorless-friendly; the only colored pips that matter are green (Nature's Lore/Beast Within, ~19 sources) and b4 black (tutors — Talisman of Dominance and the rainbow lands were added exactly for this). Play Mox Diamond only with a spare land in hand.

**T4–5:** Ulalek + Greaves. Hold Warping Wail/Stubborn Denial when you can — the adjudicated danger window for this deck is **T5–8, as archenemy**, not the early game. In b4, spend spare mana on tutors per §6 but *bank* the second combo piece in hand.

**T6+ (b3):** every Eldrazi cast comes with `{C}{C}` held for the copy. Sequence: threat with cast trigger → copy → Sanctum fetch → next threat. Eldritch Immunity/uncounterable Cavern casts break through interaction; All Is Dust resets go-wide boards and mostly misses you. Close with doubled Ulamogs and Ugin ultimates; the Echoes+Unsealing combo is your escape hatch from stalemates, not the plan.

**T6+ (b4):** count to a protected combo turn: copier + payoff + Eldrazi spell + activation mana + one piece of protection (or Cavern/Cicada flash). If the table forces you to act early, the battlecruiser mode still kills on the b3 schedule — the sim says combat alone clears tables by T14 even when the web never assembles.

**Threat assessment note:** both lists lose most often to their own T5–8 archenemy window. Imprisoned in the Moon on the scariest commander buys those turns; remember your own All Is Dust / Ugin −X frees a moon'd commander, so sweep *first*, moon *second*.

---

## 8. Simulation methodology (2026-08-24 run)

20,000 games per list, same engine (extends the standard repo goldfish script): shuffle, mulligan keeping 2–5 lands, land + greedy rocks/reducers each turn; Ancient Tomb / Eldrazi Temple / Ugin's Labyrinth = 2 mana, Eye of Ugin = −2; commander at 5 + tax; threats attack three 40-life opponents; Ulalek's `{C}{C}` copy doubles Eldrazi bodies when mana allows. New in this run: the Spellbook-verified combo lines are checked each turn under strict firing requirements, and b4 models Demonic/Vampiric/Wishclaw (fetch the missing piece of the most complete line) and Urza's Saga (chapter-3 rock fetch). Not modeled: opponent interaction (overstates speed), annihilator / Ulamog mill / cascade / all draw engines and card advantage (understates speed, and materially understates b4 combo assembly). Script: session scratchpad `winsim.py`; conclusions preserved here per repo convention.
