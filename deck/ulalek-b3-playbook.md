# Ulalek, Fused Atrocity — Bracket 3 Playbook

*Written 2026-08-26. Companion to `ulalek-primer.md` (2026-08-24), which covers the combo webs, win-rate simulations, and b3/b4 differences. This document is the **bracket-3 play guide**: the damage packages that actually win games (most of them non-infinite), what to tutor for and in what order, what to deploy first, and how to sequence a real game. All card text verified against Scryfall oracle text on 2026-08-26; combos re-verified against Commander Spellbook the same day (still exactly the two allowed late-game lines).*

Deck: `deck/ulalek-bracket3.txt`

---

## 1. The game plan in one paragraph

This is an Eldrazi battlecruiser deck whose commander turns every threat into two. Ulalek's trigger — *"Whenever you cast an Eldrazi spell, you may pay {C}{C}. If you do, copy all spells you control, then copy all other activated and triggered abilities you control. You may choose new targets for the copies"* — means each haymaker arrives with its cast trigger doubled **and** a token twin on the battlefield. The deck ramps turns 1–3, lands Ulalek turn 4 (48% of games; 87% by T6), and from turn 6 converts 7+ mana into doubled haymakers. First opponent dies around T9 to combat; the table is cleared by T13. The two infinite lines (Echoes + Unsealing, Basalt + Monument) are escape hatches from stalled boards, not the plan — 98% of goldfish wins are combat. Your job as pilot is threefold: **always bank {C}{C}**, pick the right package for the board state (§3), and spend tutors on the mana engine early and the kill piece late (§4).

## 2. The golden rule: {C}{C} discipline

Never cast an Eldrazi spell without asking what the copy buys. The math is almost always "one extra spell for 2 mana" — the best rate in the deck. Concretely:

- **Permanent spells** → the copy resolves as a **token twin** (legendary twins die to the legend rule, *after* their enter-the-battlefield abilities trigger).
- **Cast triggers** → already on the stack when Ulalek's trigger resolves, so they get copied too: one cast, two triggers.
- **Your other triggered/activated abilities on the stack** get copied as well — this is the engine behind every stack trick in §6.
- Copies are **not cast**: they don't retrigger Ulalek, Sanctum of Ugin, Kozilek's Unsealing, or Shadow in the Warp. One cast = one round of copying (two with Echoes of Eternity out).

Corollary: when sequencing a turn, cast the *cheap* Eldrazi first only if you can also afford {C}{C} on the *big* one. If you can only pay the copy tax once, spend it on the spell whose copy is worth the most (see the cheat sheet in §7).

## 3. The winning packages

Ranked roughly by how often they close games. None of these except 3f is infinite — they're "a lot of damage," which is what bracket 3 wants.

### 3a. Board theft alpha strike — *Flayer of Loyalties / Hideous Taskmaster / Emrakul, the World Anew*

The deck's signature kill: win with **their** creatures, on **your** turn, with haste and annihilator.

- **Flayer of Loyalties** ({8}{C}{C}, MV 10) + {C}{C}: the copied cast trigger steals a **second** creature — both untapped, base 10/10, trample, annihilator 2, **haste**. That's 20 hasty trample power plus 4 annihilator sacrifices the turn it resolves, and you keep two 10/10 Flayers (original + nonlegendary token) for next turn. Aim the stolen creatures at their own owners; commanders are the juiciest targets (their commander swings at their face).
- **Hideous Taskmaster** ({6}{R}, 7/2) + {C}{C}: the trigger reads "for each opponent, gain control of up to one target creature that player controls" — copied and retargeted, that's **up to two creatures per opponent**, untapped, with trample/haste/annihilator 1, plus a 7/2 token twin with the same keywords. Against a developed table this is regularly 6 stolen bodies swinging with 6 annihilator triggers. Cheapest of the theft package and the copy tax makes it {C}{C} well spent.
- **Emrakul, the World Anew** (MV 12, madness six {C}) + {C}{C}: steal **two players' entire boards** — permanently, until Emrakul leaves. Protection from spells makes the 12/12 nearly untouchable. The madness cast is real in this deck: with Kozilek, the Great Distortion refilling your hand you'll discard to hand size at cleanup — that's a legal madness window, and six {C} + {C}{C} for a two-board theft is the single most mana-efficient play the deck can make.

**When to fire:** the theft package is your answer to the "everyone else developed while I ramped" board. It converts their board advantage into your lethal turn — don't fire it into an empty table.

### 3b. Conscription turns — *Eldrazi Conscription* is an Eldrazi spell

Eldrazi Conscription is a **Kindred Enchantment — Eldrazi Aura**, so casting it triggers Ulalek. Pay {C}{C} and the spell copy resolves as a **second token Conscription that you may attach to a different creature**: two creatures each get +10/+10, trample, annihilator 2, for {8}+{C}{C}.

- Best hosts: **Ulamog, the Ceaseless Hunger** (30/30 indestructible, annihilator 2, exiles 20 on attack), **Reality Smasher** (haste — the Conscription hits the same turn), or Ulalek itself (12/15, annihilator 2 — commander damage adds up fast at 21).
- It's a colorless MV 8 spell: it triggers **Sanctum of Ugin** (fetch the next threat), exiles **Ugin's Binding** from the graveyard (one-sided mass bounce before your alpha strike), and gets **cascade, cascade** from Zhulodok if he's out.
- With **Echoes of Eternity** on the battlefield the spell is copied again — three Conscriptions off one cast.

### 3c. Mega Flare — *Summon: Bahamut* kills the whole table at once

Bahamut's chapter IV deals **damage equal to the total mana value of your other permanents to each opponent**. Count your board in any normal late game: one Ulamog (10) + a Kozilek (9–10) + Ulalek (5) + rocks and engines (8–12) clears 35+ — lethal or near-lethal to **every opponent simultaneously** from ~30 life. Lands are MV 0, so it's your nonland board that counts — this deck's nonland permanents are the fattest in the format.

- It's not an Eldrazi (no Ulalek trigger), but it **is** a colorless MV 9 spell: **Echoes of Eternity copies it** — the token Saga runs its own chapters one turn behind, including a second Mega Flare — and Echoes **doubles every chapter trigger**: I/II destroy two nonland permanents each, III draws four, IV fires **two Mega Flares**. Echoes + Bahamut alone is usually game over three turns after it lands.
- Chapters I–II are your removal for problem permanents while the bomb ticks.

**When to fire:** the "table at 25–35 life each and I can't profitably attack into three boards" state. Bahamut doesn't care about blockers.

### 3d. Azlask overrun — the go-wide kill

The deck makes a surprising number of Spawn/Scion tokens (Kozilek's Unsealing, Awakening Zone, From Beyond, Path of Annihilation, Kozilek's Command, Chittering Dispatcher, Warping Wail). **Azlask, the Swelling Scourge** converts that chaff into a board wipe on legs:

- Every colorless creature you control that dies gives an experience counter — **including every Spawn you sacrifice for mana**, so by mid-game Azlask sits on 4–8 counters passively.
- **{W}{U}{B}{R}{G}: creatures you control get +X/+X; Spawns and Scions gain indestructible and annihilator 1.** Eight 0/1 Spawns become 6/7 indestructible annihilators: 48 power spread across eight bodies, and every attack forces a sacrifice per token — spread the attackers and three boards disintegrate at once.
- Paying WUBRG in a colorless deck is the trick, and **Path of Annihilation is the enabler**: every Eldrazi you control — **Spawn and Scion tokens are Eldrazi** — taps for any color. Backups: Cascading Cataracts ({5}: five mana in any colors), Path of Ancestry / Command Tower / City of Brass / Mana Confluence / Exotic Orchard (Ulalek's identity is five-color, so "any color in your commander's identity" means *any color*).
- Stack trick: activate Azlask, then respond with an instant-speed Eldrazi cast (§6) and pay {C}{C} — the copied activation makes it **+2X/+2X**.

**When to fire:** board stalls, and any game where the haymakers keep getting answered but the token engines survived — this line wins without a single card over MV 4 on the battlefield.

### 3e. Ulamog attrition — the removal-and-inevitability package

- **Ulamog, the Ceaseless Hunger** + {C}{C}: **exile four permanents** on cast (the best removal spell in the deck), leaving a 10/10 indestructible that eats 20 cards a swing — **40 with Echoes** doubling the attack trigger, which simply kills a mid-game library in two attacks.
- **Ulamog, the Defiler** + {C}{C}: two "exile the top half of their library" triggers — halve two different players, or hit one player twice (¾ of their deck). It then enters with +1/+1 counters equal to the greatest MV in exile (after its own trigger, usually 6–8) and has **annihilator equal to its counters**. Annihilator 7 with Echoes doubling the trigger is "sacrifice fourteen permanents" — one attack ends that player's game even if they survive it.
- **All Is Dust** is the package's sweeper: Kindred Sorcery — Eldrazi, so it triggers Ulalek (the copy mops up anything that dodged the first pass) and your devoid/colorless board ignores it. Remember it pops your own Imprisoned in the Moon — sweep first, moon second.

### 3f. The escape hatches (the two sanctioned infinite lines)

Full write-ups in `ulalek-primer.md` §3 — summarized for completeness:

- **Ulalek + Echoes of Eternity + Kozilek's Unsealing**: cast any MV 4–6 Eldrazi creature with {C}{C} spare → each loop nets +2 Spawns → infinite Spawns/mana, draw the deck via Unsealing. Starters in the 99: Thought-Knot Seer, Sowing Mycospawn, Conduit of Ruin, or a recast Ulalek.
- **Basalt Monolith + Forsaken Monument**: infinite {C}. Outlets: cast your hand, Kozilek the Great Distortion refills, arbitrarily large Kozilek's Command / Eye of Ugin activations, Eldrazi Displacer machine-gun.

Per the house bracket-3 policy these are **late-game lines only** — use them to break a stalemate, not to race.

### 3g. Snowball engines (how the damage packages get paid for)

- **Zhulodok, Void Gorger** in the 99: every 7+ colorless spell cast from hand gets **cascade, cascade**, and Ulalek's {C}{C} copies the cascade triggers — a single Ulamog with both legends out is four free spells deep. Each cascaded Eldrazi *is cast*, so it triggers Ulalek again.
- **Kozilek, the Great Distortion** + {C}{C}: refill to seven cards, keep a counterspell engine on a 12/12 menace body.
- **Nulldrifter** + {C}{C}: draw four, two 4/4 flyers (evoke {2}{U} + {C}{C} = draw four for five mana in a pinch).
- **Kozilek's Command** is a **Kindred Instant — Eldrazi**: it triggers Ulalek *itself*, so X=3 with {C}{C} makes six Spawns, or double scry-and-draw, or exiles two creatures — all at instant speed.
- **Ugin, Eye of the Storms** + Echoes: every colorless spell you cast exiles **two** colored permanents. This is a removal engine, not a combo — and most of your deck is colorless spells.

---

## 4. Tutor primer — what to fetch, and when

### 4a. Land tutors: Crop Rotation (instant), Sylvan Scrying, Sowing Mycospawn

Default pecking order by game phase:

| Phase / situation | Fetch | Why |
|---|---|---|
| T1–3, developing | **Eye of Ugin** | −2 on every colorless Eldrazi spell — it's a ritual that never expires, and a repeatable creature tutor late ({7},{T}) |
| T1–3, Eye already down | **Eldrazi Temple**, then **Ancient Tomb** | 2 mana per turn toward the copy tax |
| Turn before your first 7-drop | **Sanctum of Ugin** | converts the haymaker into the next haymaker (or into Azlask/a combo creature) |
| Blue mage holding mana | **Cavern of Souls**, name Eldrazi | Ulalek and every Eldrazi creature becomes uncounterable — note it does *not* protect noncreature Eldrazi spells (Conscription, Command) |
| Going for the Azlask kill | **Cascading Cataracts** (or a rainbow land) | {5},{T}: WUBRG in one activation; Path of Annihilation is still the better enabler if it's in hand |
| Problem land (Coffers, Cradle, an opposing Cavern) | **Wasteland** | or kick Sowing Mycospawn and skip the tutor |
| Wipe-heavy table, or setting up a flash turn | **Winding Canyons** (repeatable) or **Emergence Zone** (one shot, everything) | deploy creatures at the last opponent's end step — a sorcery-speed wipe catches at most one turn of development |
| Hand has a 7+ card to spare | **Ugin's Labyrinth** | 2 mana per turn; don't fetch it with a hand of small spells |

**Crop Rotation is the deck's only instant-speed land search — spend it like a spell, not like ramp:** end of turn before your big turn, sac a basic for Sanctum (with the haymaker in hand); or fetch Cavern *in response* to sighting counter-mana; or fetch Eye of Ugin mid-combat-math the turn you need the discount. It's also a Game Changer — it should never fetch value casually.

**Sowing Mycospawn is the best tutor in the deck** because Ulalek doubles it: the cast trigger searches a land **onto the battlefield**, so with {C}{C} you get **two lands, untapped** — Eye + Temple is +4 effective mana on the spot; Sanctum + Cavern sets up a protected haymaker chain. Kicked (+{1}{C}) and copied, it **exiles two lands** — Strip Mine twice, attached to a 3/3. It's also MV 4 either way, so Kozilek's Unsealing pays out 2 Spawns (4 with the copy).

### 4b. Creature and Eldrazi-card tutors

- **Conduit of Ruin**: cast trigger searches an MV 7+ colorless creature to the **top of your library** — with {C}{C} the copied trigger searches again, letting you stack your next *two* draws. Default fetches: **Ulamog, the Ceaseless Hunger** (removal + clock) when you need to answer boards, **Kozilek, the Great Distortion** when you need gas, **Emrakul** when a theft turn wins. Its −2 on your first creature spell each turn means the fetched fatty is discounted next turn.
- **Sanctum of Ugin** (any colorless creature, to hand): mid-game, chain haymaker → haymaker. But when a package from §3 is one piece short, fetch the piece instead: **Azlask** (with tokens + rainbow mana up), **Hideous Taskmaster / Flayer** (developed enemy boards), **Elder Deep-Fiend** (you need a Fog or a tap-out turn). *The sacrifice is part of the trigger's resolution, so Ulalek/Echoes copies of the Sanctum trigger fizzle — one Sanctum, one search. Don't count on doubling it.*
- **Eye of Ugin, late game** ({7},{T}: any colorless creature, to hand): this **is** doubled by Ulalek — activate it, respond with an instant-speed Eldrazi (§6) + {C}{C}, and the copied ability searches a second creature for free.
- **From Beyond** searches for **any Eldrazi *card*** — not just creatures. That includes **Echoes of Eternity** (a Kindred Enchantment — Eldrazi: half of the infinite line and the deck's best permanent), **Eldrazi Conscription**, **Kozilek's Command**, **Eldritch Immunity**, and **Not of This World**. The sacrifice is an activation *cost*, so unlike Sanctum the Ulalek copy **works**: activate the search, respond with an instant-speed Eldrazi + {C}{C}, fetch **two** Eldrazi cards. (It cannot fetch Kozilek's Unsealing — devoid, but not an Eldrazi card.)

### 4c. Tutor sequencing rule of thumb

**Turns 1–4 every tutor is a mana tutor** (Eye/Temple/Tomb); **turns 5+ every tutor is a kill-package tutor** — decide which §3 package the board state calls for and fetch its missing piece, favoring pieces that are also engines if the package gets disrupted (Echoes, Unsealing, Path of Annihilation). The one standing exception: fetch **Sanctum** the turn before any planned 7-drop, always — it's a free chain link.

---

## 5. Deployment priorities — what must hit the battlefield fast

In priority order. Mulligan and sequence toward the top of this list.

1. **A 2-mana land or fast rock** (Eye of Ugin > Eldrazi Temple > Ancient Tomb > Ugin's Labyrinth / Sol Ring / Mana Vault). The whole deck's schedule — T4 Ulalek, T6 haymakers — runs on these. This is also why opposing Wasteland effects aimed at you go here, and why you never expose Eye to a kicked Mycospawn carelessly.
2. **Cost reducers, cheapest first**: It That Heralds the End ({1}{C}: −1 on 7+ spells *and* +1/+1 lord), Herald of Kozilek (−1 on everything colorless), Urza's Incubator (name Eldrazi, −2), Conduit of Ruin / Shadow in the Warp (−2 first creature spell). These stack: Eye + Incubator + It That Heralds + Herald makes Ulamog cost {4} — and each reducer effectively discounts the {C}{C} copy tax too, since it frees the mana that pays it.
3. **Ulalek + Lightning Greaves**, ideally the same turn. Ulalek eats every removal spell at the table; Greaves is the only clean protection for a naked commander (Not of This World needs power 7). Recasting Ulalek later is at least tolerable — his cost is all hybrid, so tax is payable — but tempo lost here is haymaker turns lost later.
4. **Kozilek's Unsealing** — the engine that makes the mid-game function: every MV 4–6 creature ramps (2 Spawns), every 7+ draws three. Land it *before* the haymaker turns start, even ahead of a threat.
5. **Echoes of Eternity** — the single most powerful permanent in the list: every colorless spell copied, every trigger doubled (annihilator, Ulamog's attack, Bahamut's chapters, Unsealing, Ulalek himself). It is also the #1 removal magnet in the deck, so deploy it the turn you can *use* it — with a haymaker to cast behind it or the Unsealing loop threatened — not into three untapped boards for value.
6. **Forsaken Monument** — +2/+2 team-wide, {C} doubling (the copy tax becomes free), 2 life per colorless cast, and half of the Basalt escape hatch.
7. **Token engines** (Awakening Zone, From Beyond, Path of Annihilation) — whenever the curve has a gap; they're the Azlask kill and the sacrifice fodder that makes everything else resilient.

**Opening hand:** 2–4 lands with a 2-mana land or fast rock, plus a cost reducer or Unsealing. A hand that casts Ulalek by T4 with one engine behind it is a keep; five haymakers is not — this deck mulligans for its curve, not its top end.

---

## 6. Piloting: sequencing, stack tricks, and threat assessment

### Turn-by-turn shape

- **T1–3:** land, rock, reducer, in that order of importance. The only colored pips that matter are green (Nature's Lore, Three Visits, Beast Within — ~19 sources). Don't run Ulalek out on T3 without protection unless the table is friendly.
- **T4–5:** Ulalek + Greaves. Bank {C}{C} from here to the end of the game. Hold Warping Wail / Stubborn Denial when possible — the deck's loss window is **T5–8 as archenemy**, and one countered sweeper usually buys the winning turn.
- **T6+:** one haymaker per turn, always with the copy tax, each one chaining through Sanctum/Unsealing into the next. Pick the §3 package the board dictates: theft into developed boards, Bahamut into gummed-up ones, Azlask off tokens, Ulamogs for attrition. Close with commander-damage Conscription math or an Ugin ultimate when combat stalls.

### Instant-speed Eldrazi: the trigger keys

Ulalek's copy only fires on an Eldrazi **cast**, so the deck's instant-speed Eldrazi are what turn your activated abilities into doubled ones. The native keys are **Kozilek's Command**, **Eldritch Immunity**, and **Not of This World**; with **Skittering Cicada** out (or a **Winding Canyons** / **Emergence Zone** activation), any Eldrazi becomes a key. The play pattern: activate an ability → while it's on the stack, cast the key + pay {C}{C} → Ulalek's trigger copies the ability. Confirmed-working targets:

- **From Beyond's sacrifice-search** → two Eldrazi cards (sac is a cost; the copy searches free).
- **Eye of Ugin's {7} tutor** → two colorless creatures.
- **Eldrazi Displacer** → two blinks for one activation (double Thought-Knot strip, untap two blockers away).
- **Azlask's WUBRG pump** → +2X/+2X.
- **Does NOT work:** Sanctum of Ugin (the sac is in the resolution — the copy can't pay it), Kozilek's Return / Ugin's Binding graveyard triggers (the "exile this card" clause fails on the second copy). One copy of each per game is all you get — spend them well.

### Echoes of Eternity: re-read your board when it lands

Echoes doubles **every triggered ability of your colorless permanents**, not just combo pieces. The ones players forget: **annihilator** (annihilator 2 becomes four sacrifices), **Ulamog's attack trigger** (exile 40), **Saga chapters** (two Mega Flares), **Ugin Eye of the Storms** (two exiles per colorless spell), **Ulalek himself** (pay {C}{C} twice, two rounds of copying). When Echoes is out, your worst spell is better than your opponents' best one — play like it, because they will kill Echoes the moment they untap.

### Defensive tools, correctly timed

- **Elder Deep-Fiend** is a flash Fog: tap four (eight with {C}{C}) attacking creatures, or tap an opponent's lands on their upkeep for a pseudo–Time Walk on the player most likely to sweep. Emerge off a Spawn is a discount, not a requirement.
- **Kozilek's Return** (from the graveyard, on any 7+ Eldrazi creature cast): a 5-damage one-sided sweep — nearly everything you control survives it. Get it into the yard cheerfully; the {2}{R} mode is mostly a way to bin it.
- **All Is Dust** before, **Imprisoned in the Moon** after — never the reverse (your own sweeper frees the moon'd commander).
- **Eldritch Immunity** overloaded on the alpha-strike turn blanks colored blockers, targeted colored removal, and *damage-based* colored sweepers (Blasphemous Act–style). It does **not** stop "destroy all creatures" wipes — protection prevents damage, targeting, blocking, and attaching, nothing else.
- **Warping Wail** counters sorceries — which at bracket-3 tables means *board wipes*. That's what the {1}{C} is being held for.
- **Heroic Intervention** saves **permanents**, not just creatures — Echoes, Unsealing, and the rocks all survive a Bane of Progress or a destroy-wipe under it, and the hexproof half answers targeted removal on Ulalek. It does not beat exile wipes (Farewell) — against those, deploy from hand at flash speed instead of into them.
- **Winding Canyons / Emergence Zone** are the structural wipe answer: hold the haymaker, cast it on the last opponent's end step, untap, swing. The deck's cast triggers mean even a wiped threat already paid out — and the enchantment engine core (Unsealing, Echoes, Awakening Zone, From Beyond, Path of Annihilation) survives creature wipes entirely.

### Threat assessment and politics

You are visibly the archenemy from turn 6 — plan for it rather than resenting it. Early, stay off the radar: ramp reads as "slow deck" until the first doubled Ulamog. Spend theft triggers and Ulamog exiles on the player who can punish you fastest, not the one with the biggest creature. The exile removal (Ulamog, Ugin's Binding, All Is Dust) ignores indestructible and graveyard decks — aim it accordingly. And because nearly every threat you cast replaces itself (Sanctum, Unsealing, Kozilek refills), you can afford to trade haymakers one-for-one with removal all game; the opponent who runs out of answers first is the one you kill first.

---

## 7. Cheat sheet — what {C}{C} buys on every Eldrazi spell

| Spell | With the copy tax paid |
|---|---|
| Ulamog, the Ceaseless Hunger | Exile **4** permanents; 10/10 indestructible (token twin dies to legend rule after triggers) |
| Ulamog, the Defiler | **Two** half-library exiles; enters annihilator ≈7 |
| Kozilek, the Great Distortion | Double refill-to-7 (second trigger usually whiffs — dump cards to the counter ability first) |
| Kozilek, the Broken Reality | Up to **4** players manifest 2, you draw per manifest |
| Emrakul, the World Anew | Steal **two** players' boards |
| Flayer of Loyalties | Steal **2** creatures as 10/10 haste annihilator 2 + keep 2 Flayers |
| Hideous Taskmaster | Steal up to **2 creatures per opponent** + 7/2 token twin |
| Elder Deep-Fiend | Tap **8** permanents at flash speed |
| World Breaker | Exile **2** artifacts/enchantments/lands |
| Nulldrifter | Draw **4**, two 4/4 flyers |
| Thought-Knot Seer | **Two** hand strips (token's ETB) |
| Sowing Mycospawn | **Two lands onto the battlefield** (kicked: exile 2 lands) |
| Conduit of Ruin | Stack your next **two** draws with 7+ threats |
| Eldrazi Conscription | **Two** auras: +10/+10 trample annihilator 2 each, splittable |
| Kozilek's Command | Both chosen modes **doubled**, at instant speed, triggers itself |
| All Is Dust | Double sweep (your board doesn't care) |
| Eldritch Immunity | Overloaded copy = team protection twice (redundant vs. removal responses) |
| Azlask, the Swelling Scourge | Token twin dies to legend rule → +1 experience counter, at least |
| Ulalek (recast) | MV 5 Eldrazi — a legal starter for the Unsealing loop |

*Benchmarks (20k-game sim, 2026-08-24, `ulalek-primer.md` §8): Ulalek median T4, 7 mana median T6, first haymaker median T8, first kill T9, table cleared T13, 98% of wins by combat.*
