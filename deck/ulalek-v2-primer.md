# 🌀 Ulalek, Fused Atrocity — Eldrazi Battlecruiser [Primer, Bracket 3, v2]

*The complete guide to the list in `deck/ulalek-bracket3-v2.txt` (the decklist file is canonical for names and counts). Written 2026-08-27, updated **2026-08-31**. Supersedes `ulalek-primer.md` and `ulalek-b3-playbook.md` (v1 documents). All card text verified against Scryfall oracle; combos verified against Commander Spellbook on this exact 99.*

---

## 📖 Table of contents

1. [Lore](#-lore)
2. [Introduction](#-introduction)
3. [Pros, cons & power level](#%EF%B8%8F-pros-cons--power-level)
4. [Ulalek rules school](#-ulalek-rules-school)
5. [The gameplan](#-the-gameplan)
6. [The doubling suite](#-the-doubling-suite--who-copies-what)
7. [The winning packages](#-the-winning-packages)
8. [The mana engine](#%EF%B8%8F-the-mana-engine)
9. [Card advantage & tutors](#-card-advantage-digging-and-tutors)
10. [Interaction & surviving as archenemy](#%EF%B8%8F-interaction-protection-and-surviving-as-archenemy)
11. [Stack tricks](#-stack-tricks--instant-speed-eldrazi-as-trigger-keys)
12. [Cheat sheet: what {C}{C} buys](#-cheat-sheet--what-cc-buys-on-every-eldrazi-spell)
13. [Alternate options](#-alternate-options)
14. [Bracket & house-rules compliance](#-bracket--house-rules-compliance)
15. [Change log](#-change-log)

---

## 📜 Lore

Ulalek, Fused Atrocity is what happens when two Eldrazi titans dip into the same plane at the same place and time: it is an extension of both **Ulamog** and **Kozilek** at once — the only card ever printed that features two titans fused together, melding reality-devouring and matter-distortion into one body. The plane where it happened no longer exists.

Fittingly, the deck is both titans' decks at once: Ulamog's inevitability, Kozilek's card flow, and a commander whose only job is to make every tentacled horror you cast arrive twice.

---

## 👋 Introduction

Ulalek costs `{C/W}{C/U}{C/B}{C/R}{C/G}` — five hybrid pips, each payable with **any** color or true colorless. In practice any five mana casts it, and its five-color identity legalizes devoid cards (Kozilek's Unsealing, World Breaker, Hideous Taskmaster…) that a truly colorless commander could never run. Its text is the whole deck:

> Whenever you cast an **Eldrazi spell**, you may pay `{C}{C}`. If you do, **copy all spells you control**, then **copy all other activated and triggered abilities you control**. You may choose new targets for the copies.

Every Eldrazi spell we cast is double-dipped: two mana turns one Ulamog into two Ulamog cast triggers, one stolen board into two, one Conscription into a pair. We ramp hard for four turns, land Ulalek, and then convert 7+ mana a turn into doubled haymakers until the table is gone. About 98% of goldfish wins are combat kills; the two infinite lines in the deck are sanctioned *late-game* escape hatches under the house bracket-3 policy, not the plan.

**You will like this deck if:**

- You like big, dumb, tentacled monsters — but want casting them to feel *clever*.
- You enjoy stack puzzles: most of this deck's edge is knowing exactly which triggers copy which.
- You want a deck that shrugs off its own board wipes (~88% of the 99 is colorless) and rebuilds faster than anyone.
- Eldrazi are cool to you. (Correct.)

**You will not like this deck if:**

- You want to be left alone: from turn 6 you are visibly the archenemy, every game.
- You dislike math-heavy turns — a good Ulalek turn has 6+ objects on the stack.
- You want turn-3 kills. This is battlecruiser Magic with excellent exchange rates, not a race.

---

## ⚖️ Pros, cons & power level

**✅ Pros**

- **The best mana-to-impact conversion at the table.** `{C}{C}` per copy is the cheapest "extra spell" in Commander.
- **Sweeper-proof engine core.** 88 of 99 cards are colorless: our own All Is Dust and Ugin −X barely touch us, and cast triggers mean even a countered or swept haymaker already paid out.
- **Rebuilds faster than anyone.** Unsealing, Echoes, From Beyond, Garruk's Uprising, Mystic Forge and the rocks all survive creature wipes; Matter Reshaper even pays us when it dies.
- **Exile-based removal.** Ulamogs, Ugins, Ugin's Binding and All Is Dust ignore indestructible and graveyard strategies.
- **Flexible speed.** With Liberator or Skittering Cicada out, the entire deck deploys at flash speed on opponents' end steps.

**❌ Cons**

- **Archenemy from turn 6.** The adjudicated loss window is T5–8: we've telegraphed power but haven't stabilized. Don't get salty when targeted — plan for it (§10).
- **Sorcery-speed board wipes** are the worst enemy; the whole flash plan (§10) exists because of them.
- **Early card flow is thin.** Nearly all card advantage is back-loaded onto resolving fat; Ancient Stirrings, Garruk's Uprising and Matter Reshaper are the patch, not a cure.
- **Colored-pip watch list:** Mana Drain `{U}{U}`, Herald of Kozilek `{1}{U}{R}`, Shadow in the Warp `{R}{G}` are the hardest casts in a green-splash base.
- **Zero basics:** Blood Moon-style effects and opposing Field of Ruin/Ghost Quarter are an accepted edge case (§13).

**☢️ Power level**

- **Bracket 3**, deliberately and verifiably: exactly 3 Game Changers (the cap) — Mana Vault, Ancient Tomb, Crop Rotation — and only the two adjudicated *late-game* infinite lines (§7e). Full compliance detail in §14.
- It starts "doing its thing" ~T4 (commander castable 65% of the time by then) and is in "I will pretty much win" position around T8–9 if unchecked.
- Sim-backed arc (20k-game goldfish, 2026-08-27): 7 effective mana by T6 in 71% of games; first kill ~T9, table cleared ~T13.

---

## 🧑‍🏫 Ulalek rules school

Three rules facts drive every line in this primer — learn these before shuffling up:

1. **Every Eldrazi cast is double-dipped.** Pay `{C}{C}` and the spell is copied (a permanent spell copy becomes a token) *and* every cast trigger already on the stack is duplicated — Ulamog's exile-two becomes exile-four, Elder Deep-Fiend's tap-four becomes tap-eight.
2. **Copies are not cast.** Copies are put onto the stack, not cast (confirmed Ulalek ruling), so they never retrigger "whenever you cast" abilities — not Ulalek's own trigger, not Sanctum of Ugin, not Kozilek's Unsealing, not Skittering Cicada's pump. One cast = one round of copying… *unless:*
3. **Two Ulalek trigger instances = mana-bound recursion.** Ulalek copies "all **other** activated and triggered abilities you control" — and that includes *another instance of Ulalek's own trigger* sitting on the stack. So whenever a doubler (§6) gives you two or more instances off one cast, the first paid instance copies the second, the copy offers its own `{C}{C}` payment, and so on: **every `{C}{C}` you can pay is another full "copy everything" round**, and each round re-copies all the spell copies made by the earlier ones. This is why the deck's mana engine and its doubling suite are the same plan.

**Ordering fine print** (it matters in big turns): when a paid trigger resolves, it puts the **spell copies on the stack first, then the ability copies** — so the copied abilities sit *above* the copied spells and resolve first. You choose the relative order within each group, but you can never resolve a copied spell before the ability copies that came with it.

**Worked example** — you control Ulalek and **Echoes of Eternity**, and cast **Ulamog, the Ceaseless Hunger** with `{C}{C}{C}{C}` spare. What's the maximum carnage?

- The cast puts on the stack: Ulamog + its cast trigger (exile 2), **doubled by Echoes** (Ulamog is a colorless spell) → two exile-2 triggers; Ulalek's trigger, **doubled by Echoes** (Ulalek is a colorless permanent) → two Ulalek instances. Echoes also queues its own copy of the Ulamog spell.
- Resolve the first Ulalek instance, pay `{C}{C}`: copy Ulamog (again) *and* both exile triggers *and* the second Ulalek instance. Running total: four exile-2 triggers, three Ulamog bodies incoming, and a fresh Ulalek instance on top.
- Pay `{C}{C}` once more on that fresh instance and everything doubles again. With just 4 spare mana you resolve **8+ permanents exiled and multiple 10/10s** (all token twins after the first die to the legend rule — *after* their ETBs). That's the deck in one bullet.

**The golden rule — `{C}{C}` discipline.** Never cast an Eldrazi spell without asking what the copy buys; bank `{C}{C}` from the moment Ulalek lands to the end of the game. If you can pay only once this turn, spend it on the spell whose copy is worth the most (§12). Cost reducers effectively discount the tax too: **Eye of Ugin** (−2 colorless Eldrazi) + **Urza's Incubator** (−2 Eldrazi creatures) + **It That Heralds the End** (−1 colorless MV7+) + **Herald of Kozilek** (−1 colorless) makes Ulamog, the Ceaseless Hunger cost `{4}` — with `{C}{C}` spare.

And the judge-call corner: **token copies of legends die to the legend rule after their ETBs resolve** (Matter Reshaper's twin is *not* legendary — it stays); **cast triggers stack with the spell**, so Ulalek's trigger resolves while the causing spell is still there to be copied; **Echoes of Eternity is itself an Eldrazi spell** (casting it triggers Ulalek, and From Beyond can tutor it); **Thief of Existence's second exile** comes from Ulalek copying its cast trigger, not from the token copy.

---

## 🎯 The gameplan

The shape of the 99: **36 lands + 16 ramp/reducers = 52 mana sources**, 10 draw/engines, 12 interaction, 4 threats/protection, 21 creatures. 88 of 99 cards are colorless (the 11 colored: Ancient Stirrings, Beast Within, Crop Rotation, Garruk's Uprising, Heroic Intervention, Imprisoned in the Moon, Mana Drain, Nature's Lore, Shadow in the Warp, Stubborn Denial, Three Visits). Green is the only real splash (~15 sources).

### Early game (T1–3)

**Mulligan for your curve, not your top end.** Keep 2–4 lands including a Tomb/Temple-class land or a 2+ mana rock, plus a cost reducer or an engine piece (Unsealing / Stirrings / Shadow in the Warp). A hand that casts Ulalek by T4 with one engine behind it is a keep; five haymakers is not.

Sequence: **land, fast rock, cost reducer, in that order.** Ancient Stirrings on T1 with spare mana; Matter Reshaper is a fine T2–3 play (it blocks happily and dies into value). Your ramp reads as "slow deck" to the table — enjoy the quiet, it ends at the first doubled haymaker. Don't run Ulalek out on T3 without protection unless the table is friendly.

### Mid game (T4–5) — the danger window opens

Ulalek + **Lightning Greaves the turn it lands** — it eats every removal spell at the table. Bank `{C}{C}` from here to the end of the game. Deploy Unsealing/Uprising before the haymaker turns start, and hold Warping Wail/Stubborn Denial when possible: the adjudicated loss window is **T5–8**, and one countered sweeper usually buys the winning turn.

### Late game (T6+) — archenemy, and fine with it

One haymaker per turn, always with the copy tax, each chaining through Sanctum / Unsealing / Uprising / Forge into the next. Pick the package the board dictates (§7): theft into developed boards, Ulamogs for attrition, Conscription for the commander-damage clock. With Liberator/Cicada out, shift the whole routine to opponents' end steps and keep interaction up on your own turn. Focus the player who can punish you fastest — your removal exiles, so aim it where indestructible and graveyards live.

**Goldfish it.** Seriously — the repo's sim numbers are a map, not the territory. A few solo games teach the `{C}{C}` banking rhythm faster than any primer section.

---

## 🔁 The doubling suite — who copies what

Four permanents multiply Ulalek's output. They do **different, non-overlapping** jobs; knowing which one catches which trigger is most of piloting this deck.

| Piece | Copies/doubles | Does NOT touch | Cost per extra round |
|---|---|---|---|
| **Ulalek** (trigger) | All spells you control + all other activated/triggered abilities on the stack — *including other Ulalek trigger instances* (§4, rule 3) | Anything if you skip the payment | `{C}{C}` per instance |
| **Echoes of Eternity** | Triggered abilities of **colorless spells** (cast triggers!) *and* colorless **permanents**; separately copies every colorless spell you cast | Colored spells/permanents (Garruk's Uprising, Shadow in the Warp) | free, passive |
| **Roaming Throne** (name Eldrazi) | Triggered abilities of Eldrazi **creatures you control** — including **Ulalek's own trigger** (= two `{C}{C}` rounds per cast), annihilator and attack triggers, Matter Reshaper's death trigger, Linebreaker, Dispatcher | **"When you cast" triggers of spells** — those trigger from the stack, and CR 109.2's "creature you control" means a permanent. Also noncreature permanents (Unsealing, From Beyond) | free, passive |
| **Abstruse Archaic** | Any one activated **or triggered** ability from a colorless source, on demand — the only piece that can copy **Eye of Ugin's activation**, a land ability, From Beyond's sac-search, or Ulalek's trigger itself | Mana abilities; sorcery-speed-only if you have no untap | `{1}` + tap (+ the copied trigger's own cost — copying Ulalek's trigger really costs `{1}` + tap + `{C}{C}`, per the official Archaic ruling) |

Stacking: these are additive, and thanks to §4 rule 3 they are *more* than additive — with **Echoes + Throne** out, one Eldrazi cast gives **three** instances of Ulalek's trigger, and each paid instance copies the ones below it. In practice your copy rounds are bounded by your colorless mana, not by your doubler count. This is how non-infinite turns still end games.

---

## 💀 The winning packages

Ranked roughly by how often they close games. None except 7e is infinite — they are "a lot of damage," which is what bracket 3 wants. From T5 on, every tutor should be fetching the missing piece of one of these.

### 7a. Board theft alpha strike — Flayer of Loyalties / Hideous Taskmaster / Emrakul, the World Anew

Win with **their** creatures, on **your** turn, with haste and annihilator.

- **Flayer of Loyalties** (`{8}{C}{C}`, 10/10) + `{C}{C}`: the copied cast trigger steals a **second** creature — both untapped, base 10/10, trample, annihilator 2, haste, until end of turn. That's 20 hasty trample power plus 4 annihilator sacrifices, and Flayer isn't legendary, so you *keep both* the original and the 10/10 token twin. Aim stolen commanders at their own owners.
- **Hideous Taskmaster** (`{6}{R}`, 7/2) + `{C}{C}`: "for each opponent, gain control of up to one target creature that player controls" — copied and retargeted, that's **up to two creatures per opponent**, untapped, with trample/haste/annihilator 1 until end of turn, plus a 7/2 token twin with the same keywords. Regularly 6 stolen bodies against a developed table.
- **Emrakul, the World Anew** (MV 12; **madness — pay six `{C}`**) + `{C}{C}`: gain control of **all creatures two target players control** — not until end of turn; you keep them as long as Emrakul stays. The madness cast is real here: Kozilek, the Great Distortion refills your hand, you discard Emrakul to hand size at cleanup, and six `{C}` + `{C}{C}` steals two armies. **Timing caveat (oracle-verified):** when Emrakul *leaves* the battlefield you sacrifice **all creatures you control** — stolen *and* your own. Fire it as a finisher, not a value play.

**When to fire:** the "everyone else developed while I ramped" board. Theft converts their board advantage into your lethal turn — don't fire it into an empty table.

### 7b. Conscription turns — Eldrazi Conscription is an Eldrazi spell

Eldrazi Conscription (`{8}`, Kindred Enchantment — Eldrazi Aura) triggers Ulalek. Pay `{C}{C}` and the spell copy resolves as a **second token Conscription attachable to a different creature**: two creatures each get +10/+10, trample, annihilator 2, for `{8}`+`{C}{C}` — and with Echoes out, **three** Conscriptions off one cast. Ulalek wearing two is a 22/25 trample annihilator 4: a one-shot commander-damage kill plus a 4-permanent strip.

- Best hosts: **Ulamog, the Ceaseless Hunger** (30/30 indestructible), **Ulalek** (21 commander damage arrives fast), or whatever **Eldrazi Linebreaker** is about to haste up — its begin-combat trigger grants haste and +X/+0 (X = your Eldrazi count).
- It's a colorless MV 8 spell: it triggers **Sanctum of Ugin** (fetch the next threat) and exiles **Ugin's Binding** from the graveyard (one-sided mass bounce before the swing). It is **not** a creature spell, so Kozilek's Unsealing does not pay out on it.

### 7c. Ulamog attrition — removal and inevitability

- **Ulamog, the Ceaseless Hunger** + `{C}{C}`: **exile four permanents** on cast — the best removal spell in the deck — leaving a 10/10 indestructible whose attack trigger mills 20 (**40 with Echoes** doubling it, **40 with Throne** too; with both, 60 — two attacks end a library).
- **Ulamog, the Defiler** + `{C}{C}`: two "target opponent exiles the top half of their library" triggers — halve two different players, or one player twice (¾ of their deck). It enters with +1/+1 counters equal to the greatest MV in exile and has **annihilator X = its counters**, ward—sacrifice two permanents. Throne/Echoes doubling an annihilator-8 attack trigger is "sacrifice sixteen permanents."
- **All Is Dust** is the package's sweeper — a Kindred Sorcery — Eldrazi, so it triggers Ulalek (the copy mops up anything that dodged the first pass) and your ~88%-colorless board ignores it. It destroys *colored* permanents; remember it also pops your own **Imprisoned in the Moon** — sweep first, moon second, never the reverse.
- **Ultima, Origin of Oblivion**'s attack trigger blights a land (loses all types/abilities, taps for `{C}` only) — aim it at Gaea's Cradle, Cabal Coffers, or an opposing utility land; it's removal that never rotates off.

### 7d. Snowball engines (how the packages get paid for)

- **Zhulodok, Void Gorger** in the 99: your 7+ colorless spells **cast from hand** get cascade, cascade — and Ulalek's `{C}{C}` copies the cascade *triggers* too: a single Ulamog with both legends out is four free spells deep, and each cascaded Eldrazi **is cast**, so it triggers Ulalek again. Caveat: Mystic Forge top-of-library casts are *not* from hand — no cascade on those.
- **Mystic Forge**: ~80% of the deck castable off the top, every turn — the deck's grind engine. With **Conduit of Ruin** stacking an MV7+ creature on top, the tutored threat is often castable the same turn at −2 from Conduit's own reduction.
- **Kozilek, the Great Distortion** + `{C}{C}`: double refill-to-seven (stack the triggers so the first resolves while you're empty), then a counterspell engine on a 12/12 menace body — discard a card of MV X to counter a spell of MV X.
- **Kozilek, the Broken Reality** + `{C}{C}`: each trigger has up to two target players manifest two cards from hand, you draw one per manifest — up to draw 8 across both triggers, while shrinking opposing hands into face-down 2/2s.
- **Garruk's Uprising**: 15 of the deck's creatures have power 4+ — including *every* MV7+ haymaker — so each bomb cantrips, and the Ulalek/Echoes token copy of a creature spell **also enters and draws again**. Plus team-wide trample: the annihilator bodies (Flayer, Taskmaster, Ulamog the Defiler) stop being chump-blockable. Green, so Echoes doesn't copy it — its value is all battlefield.
- **The token engines — mana, not an army.** Kozilek's Unsealing (MV 4–6 casts), From Beyond, Path of Annihilation, Kozilek's Command, Chittering Dispatcher and Warping Wail produce a steady stream of Spawn/Scion tokens. Their job is **ramp and chump insurance**: sacrifice them for the `{C}{C}` tax, Echoes' `{C}{C}{C}`, and emergency blocks. Path of Annihilation is also the deck's best colored fixer — every Eldrazi you control (tokens included) taps for any color — and gains you 4 life per MV7+ creature cast.
- **Ugin, Eye of the Storms** + Echoes: every colorless spell you cast exiles **two** colored permanents. A removal engine, not a combo — and most of your deck is colorless spells.
- **Ultima, Origin of Oblivion** + **Forsaken Monument**: each is "tap a permanent/land for `{C}`, add an extra `{C}`" — they stack, so Ancient Tomb/Eldrazi Temple/Urza's Tower start producing absurd mana, and the `{C}{C}` tax becomes free.

### 7e. The escape hatches — the two sanctioned infinite lines

Per the house bracket-3 policy these are **late-game lines only** — break a stalemate with them, don't race. Spellbook-verified on the exact 99 (re-run 2026-08-31): these are the only two.

- **Ulalek + Echoes of Eternity + Kozilek's Unsealing** → infinite Spawn, infinite `{C}`, draw the deck. Cast any **MV 4–6 Eldrazi creature** with `{C}{C}` spare. Echoes doubles both Ulalek's and Unsealing's triggers; resolve one Ulalek trigger paying `{C}{C}` — it copies the spell and all other triggers on the stack (including the second Ulalek instance, §4 rule 3); the doubled Unsealing triggers make four Spawns; sacrifice two to repay `{C}{C}` for the next copied Ulalek trigger. Each cycle nets +2 Spawns and re-copies everything. Convert: infinite `{C}` → cast the whole deck (Unsealing draws 3 per MV7+ creature). **Legal starters in this 99: Thought-Knot Seer (4), Sowing Mycospawn (4), a recast Ulalek (5), Conduit of Ruin (6).** (Matter Reshaper is MV 3 — not a starter. Roaming Throne is MV 4 but not an Eldrazi *spell*, so it triggers Unsealing without triggering Ulalek.)
- **Basalt Monolith + Forsaken Monument** → infinite `{C}` (Monument makes Basalt tap for 4 and untap for 3). Not a win by itself — outlets are casting your hand, Kozilek the Great Distortion refills, and arbitrarily large Kozilek's Command / Eye of Ugin activations. Rule-0 mention it at the table per the standing adjudication.

---

## ⛰️ The mana engine

### The lands that set the schedule

The whole deck's schedule — T4 Ulalek, T6 haymakers — runs on the 2-mana lands. Protect them; opposing Wasteland effects aimed at you go here.

- **Eye of Ugin** — not mana, better: −2 on every colorless Eldrazi spell, a ritual that never expires, plus a late-game repeatable tutor (`{7},{T}`: any colorless creature to hand — and *this* activation, unlike Sanctum, can be copied by Ulalek/Archaic).
- **Eldrazi Temple, Ancient Tomb** — `{C}{C}` every turn (Tomb costs 2 life).
- **Ugin's Labyrinth** — `{C}{C}` if you imprint a 7+ colorless card from hand (20+ hits in the deck). Don't fetch it when the hand is all small spells; you can retrieve the imprinted card later by tapping it for the return mode.
- **The Urza package: Urza's Mine / Power Plant / Tower + Planar Nexus.** Nexus is *every* nonbasic land type, so it counts as all three Urza lands at once: Nexus + Tower = 4 mana from 2 lands; the full set = 8 from 4. Sim-honest expectation: a powered pair by T6 in **~18% of games** — an upside wedge, not the engine. The floor is fine (each is a Wastes). Nexus also taps for any color (`{1},{T}`).
- **Urza's Cave** — `{C}` until you need it, then `{3},{T}`, sac: **any land onto the battlefield tapped, at instant speed**. The deck's third guaranteed specific-land tutor: the missing Urza piece, Eye of Ugin, Sanctum before a haymaker turn, or an end-of-turn Winding Canyons/Emergence Zone. **Type note:** its land type is "Urza's Cave", *not* Mine/Power-Plant/Tower — it fetches Tron pieces but never powers them (that's Nexus's job).
- **Vesuva** — enters tapped as a copy of any land: Temple/Tomb #2, **or Urza's Tower #2** (Tower + Vesuva-Tower + Nexus = 7 mana from 3 lands), or the table's best land. It can't usefully copy Eye (legendary).
- **Three Tree City** (name Eldrazi) — `{2},{T}`: one color × your Eldrazi count, tokens included. Ramp *and* a colored-cost enabler for the splash spells.
- **Bonders' Enclave** — `{3},{T}`: draw a card with a power-4 creature out. Almost always on from T5.
- **Utility:** Boseiju (interaction in a land slot), Wasteland, Cavern of Souls (§10), Sanctum of Ugin (§9), Winding Canyons + Emergence Zone (§10), Yavimaya Cradle of Growth (every land taps for G — it alone fixes Beast Within/Heroic Intervention).

**Zero basics** (accepted 2026-08-27): no basic-only fetcher remains, and mass land denial is forbidden at bracket 3. Residual exposure: Blood Moon–style effects and opposing Field of Ruin/Ghost Quarter — revisit basics only if those appear in the pod.

### Rocks and reducers

Deployment order on T1–3: **fast rock ≥ cost reducer ≥ everything else.** Sol Ring/Mana Vault/Basalt/Thran Dynamo and the 2-drops accelerate the commander; the reducer stack (§4) accelerates everything after him. Note **Fellwar Stone** taps for "any color an opponent's land could produce" — colorless is not a color, so it's the one rock that can never pay the `{C}{C}` tax, Kozilek's Command's `{C}{C}`, or Echoes' `{C}{C}{C}` (it *does* cast Ulalek, whose pips take any mana). Reflecting Pool, by contrast, adds any *type* a land you control could produce — type includes colorless — but only ever one mana (it does not copy Tomb's "2").

---

## 🔎 Card advantage, digging, and tutors

The deck's diagnosed structural weakness is **early/mid-game card flow**: nearly all card advantage is back-loaded onto already casting a fatty. The answers, cheapest first — use them aggressively:

- **Ancient Stirrings** (`{G}`, T1 play): look at top 5, take a colorless card — with 88/99 colorless cards it's effectively "dig 5, take the best card" (odds of a total whiff: ~0.0006%). Land when land-light, rock or threat when flooded. It also finds Urza pieces opportunistically (lands are colorless cards).
- **Matter Reshaper** (`{2}{C}` 3/2 Eldrazi): the cheap body that replaces itself — when it dies, reveal the top card; an MV ≤ 3 permanent (36 lands + the cheap rocks = most of the deck) goes **straight onto the battlefield**, anything else to hand. A chump block or a board wipe now pays *you*. Roaming Throne doubles the death trigger; it's also a cheap early Ulalek trigger, and Urza's Incubator drops it to `{C}`.
- **Garruk's Uprising** (`{2}{G}`): a card per power-4 creature entering — every haymaker cantrips, token copies included.
- **Kozilek's Unsealing** (`{2}{U}`, devoid): the engine that makes the midgame function. **Creature spells only** (verified): MV 4–6 → two Spawns (ramp); MV 7+ → draw three. Echoes doubles it; Throne does not (it's an enchantment).
- **Mystic Forge / Bonders' Enclave / Kozilek refills / Ugin +2**: the T6+ grind layer.

### Tutor matrix — what to fetch, when

**Land tutors — Crop Rotation (instant!), Sowing Mycospawn, and Urza's Cave** (Stirrings is the soft fourth finder):

| Phase / situation | Fetch |
|---|---|
| T1–3, developing | **Eye of Ugin**, then Eldrazi Temple / Ancient Tomb |
| Turn before your first 7-drop | **Sanctum of Ugin** — converts the haymaker into the next one |
| Blue mage holding mana | **Cavern of Souls**, name Eldrazi |
| Urza wedge live (Nexus or 2 pieces already down) | the missing **Urza land** or **Vesuva** |
| Problem land or Blood Moon meta | **Wasteland** / **Boseiju** target list |
| Wipe-heavy table | **Winding Canyons** (repeatable) or **Emergence Zone** (one shot, *everything* — including an end-of-turn All Is Dust) |
| Hand has a spare 7+ card | **Ugin's Labyrinth** |
| Nothing urgent | **Urza's Cave** itself — bank the tutor in a land slot for later |

**Crop Rotation is the deck's premier instant-speed land search — spend it like a spell, not like ramp:** end-of-turn Sanctum with a haymaker in hand; Cavern *in response* to sighting counter-mana; Eye mid-combat-math on the turn the discount matters. It's one of the deck's three Game Changers — never fetch casual value with it. (It sacrifices a land as a cost — with zero basics, sac your worst dual.) **Urza's Cave** is the budget copy of the same play: 4 total mana, land arrives tapped — plan it a turn ahead.

**Sowing Mycospawn is the best tutor in the deck** because Ulalek doubles it: the cast trigger searches a land **onto the battlefield**, so with `{C}{C}` you get **two lands, untapped** — Eye + Temple is +4 effective mana on the spot. Kicked (`{1}{C}`) and copied it also **exiles two lands** (Strip Mine twice, attached to a 3/3), and at MV 4 it triggers Unsealing for 2 Spawns (4 with Echoes) and can start the infinite loop.

**Creature tutors:**

- **Conduit of Ruin**: cast trigger searches an MV 7+ colorless creature **to the top** — copied, you stack your next *two* draws. Defaults: Ulamog the Ceaseless Hunger (removal + clock), Kozilek the Great Distortion (gas), Emrakul (theft finisher). With Mystic Forge out, the topped card is castable immediately; Conduit's own −2 discounts it.
- **Sanctum of Ugin** (sac on your colorless 7+ cast → any colorless creature to hand): midgame, chain haymaker → haymaker; when a §7 package is one piece short, fetch the piece — Taskmaster/Flayer into developed boards, Elder Deep-Fiend when you need a Fog. **The sacrifice is part of the trigger's resolution, so Ulalek/Echoes copies of Sanctum's trigger fizzle — one Sanctum, one search.** Don't count on doubling it.
- **Eye of Ugin, late** (`{7},{T}`): same search, but **this one doubles** — activate, respond with an instant-speed Eldrazi + `{C}{C}` (or Abstruse Archaic), get two creatures.
- **From Beyond** (`{1}{G}` + sac): tutors **any Eldrazi *card*** — including **Echoes of Eternity**, **Eldrazi Conscription**, **Kozilek's Command**, **All Is Dust**, **Eldritch Immunity**, **Not of This World** — not just creatures. The sacrifice is an activation *cost*, so unlike Sanctum the Ulalek/Archaic copy **works**: two Eldrazi cards. (It cannot fetch Kozilek's Unsealing — devoid, but not an Eldrazi card.) Until then it makes a Scion every upkeep.

**Sequencing rule of thumb: turns 1–4 every tutor is a mana tutor; turns 5+ every tutor is a kill-package tutor.** Standing exception: fetch Sanctum the turn before any planned 7-drop, always.

---

## 🛡️ Interaction, protection, and surviving as archenemy

### Your interaction suite, correctly timed

- **Mana Drain** — the `{U}{U}` is the deck's hardest cast; hold it for wipes and game-winning spells, and sink the ramp into next turn's haymaker.
- **Warping Wail** — counters *sorceries*, which at bracket-3 tables means board wipes. That's what the `{1}{C}` is held for. (Also: exile a mana dork / make a Scion at instant speed for an emergency `{C}`.)
- **Stubborn Denial** — ferocious is nearly always on (any power-4 creature); a 1-mana Negate all game.
- **Not of This World** — counters any spell **or ability** targeting your permanent; **free** only if the target is your power-7+ creature. It never protects a naked 2/5 Ulalek — that's Lightning Greaves' job — but it protects every haymaker for `{0}`, and it's an Eldrazi spell: countering their removal triggers Ulalek.
- **Beast Within / Boseiju / World Breaker / Thief of Existence** — the any-permanent answers. Thief's cast trigger (exile a noncreature, nonland permanent MV ≤ 4 an opponent controls) doubled by Ulalek hits two mana rocks/engines; the downside draw only happens when Thief later leaves.
- **All Is Dust → Imprisoned in the Moon, never the reverse** — your own sweeper (and Ugin −X) pops the moon-aura and frees the locked commander.
- **Kozilek's Return** — the `{2}{R}` mode is mostly a way to bin it; from the graveyard it fires on any MV7+ Eldrazi *creature* cast for a 5-damage one-sided sweep (your board is fat enough not to care). The exile clause means the graveyard trigger works **once** — Ulalek copies of it fizzle.
- **Ugin's Binding** — early: a bounce spell. Late: every colorless 7+ spell you cast exiles it from the graveyard for a **one-sided mass bounce** — this triggers off every haymaker for the rest of the game, so bin it happily.
- **Ugin, the Spirit Dragon / Ugin, the Ineffable / Ugin, Eye of the Storms** — sweeper, removal + token draw engine, and the cast-trigger exile engine respectively. Your ~88%-colorless board dodges your own Ugin −X.

### The wipe plan (the deck's structural answer)

Sorcery-speed wipes are the deck's worst enemy; the answer is **flash density** — deploy on the *last opponent's end step* so a wipe catches at most one turn of development:

1. **Liberator, Urza's Battlethopter** — colorless *and* artifact spells have flash: effectively the whole deck, repeatably. It weaponizes held interaction mana (hold Drain/Wail/Denial; if nothing needs countering, flash in a threat) and grows a counter whenever you overspend past its power. It does **not** untap your lands.
2. **Skittering Cicada** — colorless spells have flash, and it grows +X/+X (X = each cast spell's MV, **stacking**, with trample) — cast a 7-drop and a 5-drop precombat and it swings as a 14/14. **Only real casts pump it** — Ulalek/Echoes copies don't.
3. **Winding Canyons** — creatures at flash speed, every turn, in a land slot.
4. **Emergence Zone** — one shot, but flashes **everything**, including noncreature spells: the end-of-turn All Is Dust is a play this deck actually makes.
5. **Heroic Intervention** — saves **permanents**, not just creatures: Echoes, Unsealing, the rocks all survive a destroy-wipe or Bane of Progress under it; the hexproof half answers targeted removal on Ulalek. It does *not* beat exile wipes (Farewell) — against those, stay at flash speed instead.
6. **Eldritch Immunity** — overloaded (`{4}{C}`), the team gains protection from each color: colored blockers, targeted colored removal, and colored *damage-based* sweepers all blank on your swing turn. It does **not** stop "destroy all creatures" — protection prevents Damage, Enchanting/Equipping, Blocking, Targeting, nothing else. It's an Eldrazi instant: casting it triggers Ulalek.
7. **Elder Deep-Fiend** — the flash Fog: tap four (eight with `{C}{C}`) attackers, or tap a sweeper-player's lands on their upkeep. Emerge `{5}{U}{U}` off a Spawn is a discount, not a requirement — the `{8}` cast is normal here, and either way MV 8 triggers Unsealing's draw-three.

And remember the engine core — Unsealing, Echoes, From Beyond, Path of Annihilation, Garruk's Uprising, the rocks — survives creature wipes entirely, and Matter Reshaper turns a sweeper into a free permanent. Cast triggers mean even a swept haymaker already paid out. You rebuild faster than anyone at the table.

### Protecting the key pieces

Priority order — protect these, in order:

1. **Ulalek** — every plan runs through the trigger. **Lightning Greaves the turn it lands.** Recasting is tolerable (hybrid pips make tax payable) but each recast is a haymaker turn lost.
2. **Echoes of Eternity** — the single most powerful permanent in the list; informed opponents kill it on sight. Deploy it the turn you can *use* it — with a haymaker behind it — not into three untapped boards for value. Casting it triggers Ulalek: with `{C}{C}` you get a **token copy of Echoes itself**.
3. **Kozilek's Unsealing** — the engine that keeps the hand full; quietly wins long games alone.
4. **Eye of Ugin / Temple / Tomb** — the difference between T4 and T6 Ulalek.
5. **Mystic Forge / Roaming Throne / Forsaken Monument** — the grind and doubling layer; Throne at least has ward `{2}`.

### Threat assessment and politics

You are visibly the archenemy from T6 — plan for it. Early, ramp reads as "slow deck"; stay off the radar until the first doubled haymaker. Spend theft triggers and Ulamog exiles on the player who can punish you fastest, not the biggest creature. Your exile-based removal ignores indestructible and graveyards — aim it accordingly. Because nearly every threat replaces itself (Sanctum, Unsealing, Uprising, Kozilek refills, Forge), you can trade haymakers one-for-one with removal all game — the opponent who runs out of answers first is the one you kill first.

---

## 🪄 Stack tricks — instant-speed Eldrazi as trigger keys

Ulalek only fires on an Eldrazi **cast**, so instant-speed Eldrazi are what turn your activated abilities into doubled ones. Native keys: **Kozilek's Command**, **Eldritch Immunity**, **Not of This World**. With **Liberator or Skittering Cicada** out (or a Winding Canyons/Emergence Zone activation), *every* Eldrazi is a key. The pattern: activate an ability → while it's on the stack, cast the key + pay `{C}{C}` → Ulalek's trigger copies the ability.

Confirmed-working targets:

- **From Beyond's sacrifice-search** → two Eldrazi cards (sac is a cost; the copy searches free).
- **Eye of Ugin's `{7}` tutor** → two colorless creatures.
- **Basalt Monolith's untap**, **Kozilek's Command itself** (a copied Command keeps its modes and X).
- **Does NOT work:** Sanctum of Ugin (sac is in the resolution — the copy can't pay it); Kozilek's Return / Ugin's Binding graveyard triggers (the "exile this card" clause fails on the second copy — one each per game, spend them well); **mana abilities** — never copyable by anything.

**Kozilek's Command deserves its own note** — `{X}{C}{C}` Kindred Instant, choose two of: X Spawns / scry X + draw / exile a creature MV ≤ X / exile up to X graveyard cards. It triggers Ulalek *itself*, the copy keeps X and modes, and it's the deck's most flexible key: X=3 with `{C}{C}` is six Spawns, or double scry-draw, or two exiled creatures, at instant speed, off `{C}`-heavy mana.

**Abstruse Archaic is the fourth doubling piece** (§6) and the only *repeatable* on-demand one: `{1},{T}` copies any activated or triggered ability from a colorless source — Ulalek's trigger (true cost `{1}`+tap+`{C}{C}`), Eye's tutor, From Beyond's search, a land's ability. It snowballs because Ulalek's trigger sits above the causing spell, which is still on the stack to be re-copied.

---

## 📋 Cheat sheet — what `{C}{C}` buys on every Eldrazi spell

Eldrazi spells (these trigger Ulalek when cast):

| Spell | With the copy tax paid |
|---|---|
| Ulamog, the Ceaseless Hunger | Exile **4** permanents; token twin's ETB resolves before it dies to legend rule |
| Ulamog, the Defiler | **Two** half-library exiles (two players, or one player to ¾); enters annihilator ≈8+ |
| Kozilek, the Great Distortion | Double refill-to-7 (resolve one, dump to the counter ability, resolve the other) |
| Kozilek, the Broken Reality | Two triggers × (up to 2 players manifest 2) — up to **draw 8** |
| Emrakul, the World Anew | Steal **all creatures of two players** (kept while Emrakul lives; its exit sacrifices *your* creatures too) |
| Flayer of Loyalties | Steal **2** creatures as 10/10 haste annihilator-2 + keep both Flayers |
| Hideous Taskmaster | Steal up to **2 creatures per opponent** + a 7/2 token twin, all with haste/trample/annihilator 1 |
| Elder Deep-Fiend | Tap **8** permanents at flash speed |
| World Breaker | Exile **2** artifacts/enchantments/lands; recurs from the yard for `{2}{C}`+sac-a-land |
| Thief of Existence | Exile **2** opposing noncreature, nonland permanents MV ≤ 4 |
| Thought-Knot Seer | **Two** hand strips (the exile is an ETB, so the token twin strips again) |
| Sowing Mycospawn | **Two lands onto the battlefield**; kicked: exile 2 lands |
| Conduit of Ruin | Stack your next **two** draws with MV7+ threats |
| Eldrazi Conscription | **Two** auras: +10/+10 trample annihilator 2 each, splittable |
| Kozilek's Command | Both modes **doubled** at instant speed; triggers Ulalek itself |
| All Is Dust | Double sweep (your board doesn't care); triggers Ulalek itself |
| Eldritch Immunity | Overloaded copy = team protection twice (redundancy vs. responses) |
| Not of This World | Copy counters a **second** spell/ability (retargetable) |
| Matter Reshaper | 3/2 token twin — **not legendary, it stays**; each one dies into a free MV≤3 permanent or a card |
| Eldrazi Linebreaker | 3/3 trample token twin; two begin-combat haste/pump triggers each turn after |
| Chittering Dispatcher | Token twin; every myriad copy that dies makes a Spawn |
| Zhulodok, Void Gorger | Token twin dies to legend rule, but the cast still cascaded if 7+ from hand |
| Ulalek (recast) | MV 5 Eldrazi — a legal starter for the Unsealing loop |

Colorless but **not** Eldrazi spells — they never trigger Ulalek, but Echoes copies them, and Ulalek's trigger copies them if they're on the stack under it: Ultima, Skittering Cicada, Roaming Throne, Liberator, Abstruse Archaic, Mystic Forge, all rocks, all three Ugins, Kozilek's Return, Ugin's Binding, Warping Wail, Kozilek's Unsealing, Forsaken Monument. (Ugin, Eye of the Storms + Echoes: an Eldrazi cast while both are out exiles **two** colored permanents *on top of* everything above.)

---

## 🔀 Alternate options

**⬆️ Powering up (toward bracket 4)**

Evaluated in past passes and recorded as the go-to upgrades if the pod escalates: **The One Ring** (colorless, 100% castable, protection + escalating draw — was weighed against Crop Rotation's GC slot and deferred), **Fierce Guardianship**, **Deflecting Swat**, **Grim Monolith**. Adding a fourth Game Changer or an early-game infinite (e.g. Kinnan + Basalt) moves the deck out of bracket 3 — that's the line you'd be crossing, so cross it on purpose. There is also a true cEDH Ulalek archetype (Glaring Fleshraker storm with Tron lands) — a different deck, not an upgrade path for this one; its Fleshraker/Food Chain lines were deliberately cut here by house policy.

**⬇️ Powering down**

Remove one half of each infinite (Echoes of Eternity or Kozilek's Unsealing; Basalt Monolith or Forsaken Monument) and the deck loses its escape hatches but keeps ~98% of its wins. If a pod is wipe-light you can also trim the flash package for more threats.

**💶 Budget**

House policy: the owner proxies freely and price never decides a card choice; the priced buylist lives in `deck/ulalek-buylist.md` (≥25€ cards are marked as proxy candidates). As of the 2026-08-27 follow-ups nothing in the mana base is ≥25€ — the reserved-list duals were swapped for check lands rather than proxied.

**Known weaknesses / tuning levers** (so testing knows where to look first):

1. **Haymaker-in-hand dip** (48%→40% by T6 in the sim, upper bound): if the top-end feels thin in real games, the fix is a threat re-add — Sire of Seven Deaths or Void Winnower were the flagged candidates — *not* reverting the mana base.
2. **Zero basics**: if Blood Moon effects or Field of Ruin show up in the pod, re-add a basic or two over the weakest duals.
3. **Urza package is a wedge, not an engine** (~18% powered by T6). Urza's Cave (added 2026-08-31) is the consistency patch; the standing house rule (Tron-style synergy lands are low-value in singleton) says don't invest further.
4. **Specific-land tutoring** is back to three guaranteed outs (Crop Rotation, Sowing Mycospawn, Urza's Cave) plus Stirrings as the soft finder — the flagged cost of the Sylvan Scrying cut is considered paid off.
5. **Exile wipes** (Farewell-class) beat Heroic Intervention and indestructible alike — the only answer is flash-speed deployment and counterspells.

---

## 📏 Bracket & house-rules compliance

- **Game Changers: exactly 3** (the bracket-3 cap) — Mana Vault, Ancient Tomb, Crop Rotation. Verified against the Aug-2026 list; Mana Drain and Boseiju are **not** on it, and none of the v2 additions (Urza's Cave and Matter Reshaper included) is.
- **Combos: exactly the two adjudicated late-game lines** (Spellbook re-run on the exact 99, 2026-08-31): Basalt Monolith + Forsaken Monument, and Ulalek + Echoes + Kozilek's Unsealing. Both kept deliberately under the house policy (only *early-game* 2-card infinites must go); rule-0 the Basalt line at the table. No early-game infinite exists in the 99 — Kinnan and Food Chain lines were cut at earlier passes and stay out.
- **No mass land denial.** Wasteland/kicked Mycospawn are single-target land removal, legal at bracket 3.

---

## 🗓️ Change log

**2026-08-31**

- **Tomb of the Spirit Dragon → Urza's Cave.** The deck wanted a third guaranteed land tutor (the Sylvan Scrying cut had left exactly two), and Cave delivers it from a land slot: any land, onto the battlefield, at instant speed. Tomb's lifegain valve was the weakest utility land left. Expedition Map was considered for the same job and rejected — it eats a spell slot and dies to the artifact hate already aimed at our rocks.
- **Azlask, the Swelling Scourge → Matter Reshaper.** Azlask's activation costs `{W}{U}{B}{R}{G}` — five different colored pips at once, which this mana base essentially never assembles. He was a 3-mana 2/2 collecting experience counters with no payoff, and the "Azlask overrun" go-wide package built around him is retired: the token engines were always mana, not an army. Reshaper attacks the deck's real weakness (early card flow, post-wipe refuel) in the same slot.

**2026-08-27 — the v2 pass** (full card-by-card rationale in `deck/ulalek-v2-proposal.md` and the decklist's decision log)

- Lands to 36 with the Urza's Mine/Power-Plant/Tower + Planar Nexus package, Vesuva, Boseiju, Reflecting Pool — and eventually zero basics (the reserved-list duals came and went the same week: too expensive to actually play, swapped for Hinterland Harbor and Sulfur Falls).
- Thran Dynamo over Worn Powerstone; Mystic Forge over Nulldrifter (same card-advantage job, every turn); Roaming Throne over Eldrazi Displacer (it doubles Ulalek's own trigger); Liberator over one flash land.
- Garruk's Uprising and Ancient Stirrings in for The Great Henge and Sylvan Scrying — both swaps aimed at the diagnosed early-game card-flow weakness.
- Eldrazi Conscription restored after initially being cut for a land (owner was right — it's an Eldrazi *spell*, so it triggers Ulalek and one cast makes two +10/+10 annihilator auras); Reality Smasher paid for it (its "protection" rider is a one-card discard tax that stops nothing that matters).
- Combos and Game Changers re-verified after every swap; the deck has sat at exactly 3 GCs and 2 sanctioned lines throughout.

*Sources: Scryfall oracle text (2026-08-27, swap cards re-verified 2026-08-31); Commander Spellbook on the exact 99 (re-run 2026-08-31); 20k-game Monte Carlo sims per the repo methodology in `CLAUDE.md` (absolute numbers only comparable within a run). Owner rulings recorded in the decklist decision log are settled — don't re-litigate them here.*
