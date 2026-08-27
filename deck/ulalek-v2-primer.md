# Ulalek, Fused Atrocity — Complete Primer (Bracket 3, v2)

*Written 2026-08-27 for `deck/ulalek-bracket3-v2.txt` (the decklist file is canonical for names and counts). This is the single, self-contained guide to the v2 deck: what it is, how it wins, every important rules interaction, tutor and deployment priorities, and turn-by-turn piloting. It supersedes `ulalek-primer.md` (2026-08-24) and `ulalek-b3-playbook.md` (2026-08-26), which describe the v1 list. All card text in this document was re-verified against Scryfall oracle text on 2026-08-27; combos were re-verified against Commander Spellbook on the exact v2 99 the same day.*

---

## 1. What this deck is

Ulalek, Fused Atrocity costs `{C/W}{C/U}{C/B}{C/R}{C/G}` — five hybrid pips, each payable with **any** color or true colorless. In practice any five mana casts it, and its five-color identity legalizes devoid cards (Kozilek's Unsealing, World Breaker, Hideous Taskmaster…) that a truly colorless commander could never run. Its text is the whole deck:

> Whenever you cast an **Eldrazi spell**, you may pay `{C}{C}`. If you do, **copy all spells you control**, then **copy all other activated and triggered abilities you control**. You may choose new targets for the copies.

Two consequences drive every line in this primer:

1. **Every Eldrazi spell is double-dipped.** Pay `{C}{C}` and the spell is copied (a permanent spell copy becomes a token) *and* every cast trigger already on the stack is duplicated — Ulamog's exile-two becomes exile-four, Elder Deep-Fiend's tap-four becomes tap-eight.
2. **Copies are not cast.** Copies are put onto the stack, not cast (confirmed Ulalek ruling), so they never retrigger "whenever you cast" abilities — not Ulalek's own trigger, not Sanctum of Ugin, not Kozilek's Unsealing, not Skittering Cicada's pump. One cast = one round of copying; more rounds come from the doubling suite (§4).

**Deck identity in one line:** Eldrazi battlecruiser that ramps T1–4, lands Ulalek ~T4, and from T6 converts 7+ mana into doubled haymakers; it wins by combat, board theft, and annihilator. Its two infinite lines are sanctioned *late-game* escape hatches (house bracket-3 policy), not the plan.

**What changed in v2** (2026-08-27, full history in the decklist's decision log): 36 lands including the Urza's Mine/Power-Plant/Tower + Planar Nexus package, Vesuva, Boseiju, Reflecting Pool and zero basics; denser rocks (Thran Dynamo); Mystic Forge and Roaming Throne and Liberator, Urza's Battlethopter; Garruk's Uprising and Ancient Stirrings patching the diagnosed early-game card-flow weakness; Eldrazi Conscription restored. Out: Summon: Bahamut, Eldrazi Displacer, Nulldrifter, Reality Smasher, Awakening Zone, The Great Henge, Sylvan Scrying, Worn Powerstone and the basic lands.

---

## 2. The list at a glance

Canonical file: `deck/ulalek-bracket3-v2.txt`. 99 + commander, grouped as in the file:

- **Lands (36):** Ancient Tomb, Bonders' Enclave, Boseiju Who Endures, Breeding Pool, Cavern of Souls, City of Brass, Command Tower, Eldrazi Temple, Emergence Zone, Exotic Orchard, Eye of Ugin, Hinterland Harbor, Karplusan Forest, Ketria Triome, Mana Confluence, Misty Rainforest, Path of Ancestry, Planar Nexus, Reflecting Pool, Sanctum of Ugin, Scalding Tarn, Steam Vents, Stomping Ground, Sulfur Falls, Three Tree City, Tomb of the Spirit Dragon, Ugin's Labyrinth, Urza's Mine, Urza's Power Plant, Urza's Tower, Vesuva, Wasteland, Winding Canyons, Wooded Foothills, Yavimaya Coast, Yavimaya Cradle of Growth
- **Ramp & cost reduction (16):** Arcane Signet, Basalt Monolith, Conduit of Ruin, Fellwar Stone, Forsaken Monument, Herald of Kozilek, It That Heralds the End, Mana Vault, Mind Stone, Nature's Lore, Sol Ring, Talisman of Curiosity, Talisman of Impulse, Three Visits, Thran Dynamo, Urza's Incubator
- **Draw & engines (10):** Ancient Stirrings, Crop Rotation, Echoes of Eternity, From Beyond, Garruk's Uprising, Kozilek's Command, Kozilek's Unsealing, Mystic Forge, Path of Annihilation, Shadow in the Warp
- **Interaction & removal (12):** All Is Dust, Beast Within, Heroic Intervention, Imprisoned in the Moon, Kozilek's Return, Mana Drain, Not of This World, Stubborn Denial, Ugin's Binding, Warping Wail, Ugin the Ineffable, Ugin the Spirit Dragon
- **Big threats & protection (4):** Eldrazi Conscription, Eldritch Immunity, Lightning Greaves, Ugin Eye of the Storms
- **Creatures (21):** Abstruse Archaic, Azlask the Swelling Scourge, Chittering Dispatcher, Elder Deep-Fiend, Eldrazi Linebreaker, Emrakul the World Anew, Flayer of Loyalties, Hideous Taskmaster, Kozilek the Broken Reality, Kozilek the Great Distortion, Liberator Urza's Battlethopter, Roaming Throne, Skittering Cicada, Sowing Mycospawn, Thief of Existence, Thought-Knot Seer, Ulamog the Ceaseless Hunger, Ulamog the Defiler, Ultima Origin of Oblivion, World Breaker, Zhulodok Void Gorger

Useful census numbers (measured on this exact 99):

- **52 mana sources** (36 lands + 16 ramp/reducers).
- **88 of 99 cards are colorless cards.** The 11 colored cards: Ancient Stirrings, Beast Within, Crop Rotation, Garruk's Uprising, Heroic Intervention, Imprisoned in the Moon, Mana Drain, Nature's Lore, Shadow in the Warp, Stubborn Denial, Three Visits. Consequences: Ancient Stirrings is effectively "dig 5, take the best card"; All Is Dust barely touches your board; Ugin −X sweeps miss it entirely.
- **Green is the only real splash** (~15 sources) for Nature's Lore/Three Visits/Beast Within/Heroic Intervention/Uprising/Stirrings. The hardest casts in the deck are Mana Drain `{U}{U}`, Herald of Kozilek `{1}{U}{R}` and Shadow in the Warp `{R}{G}` — watch them in testing.
- **Zero basics** (accepted 2026-08-27): no basic-only fetcher remains, and mass land denial is forbidden at bracket 3. Residual exposure: Blood Moon–style effects and opposing Field of Ruin/Ghost Quarter — revisit basics only if those appear in the pod.

---

## 3. How the deck wins (simulation-backed)

Same-script 20,000-game goldfish sims, v1 vs v2 (2026-08-27; absolute numbers are not comparable to older logs — only within-run deltas are meaningful):

| Metric | v1 | v2 |
|---|---|---|
| Ulalek castable by T4 | 63% | **65%** |
| Ulalek castable by T5 | 86% | **87%** |
| 7 effective mana by T5 | 51% | **53%** |
| 7 effective mana by T6 | 68% | **71%** |
| Urza land "powered" by T6 | — | ~18% |
| First MV7+ threat castable **and** in hand, by T6 | 48% | 40% |

The one metric that dips — haymaker in hand — is an **upper bound on the real cost**: v2 trades three of twelve MV7+ pieces for velocity the sim cannot model (Mystic Forge casting threats off the top, Sanctum/Conduit tutoring the threat you need, Liberator turning opponents' turns into deployment time). The v1-era win-mode sim (2026-08-24, near-identical threat suite) put the deck at **first opponent dead ~T9, table cleared ~T13, 98% of goldfish wins by combat** — treat those as the v2 ballpark too, slightly faster on mana.

**The plan:** ramp T1–4 → Ulalek T4 with protection → convert 7+ mana into doubled haymakers T6–8, one per turn, each chaining into the next via Sanctum/Unsealing/Forge → first kill ~T9. You are visibly the archenemy from T6; the adjudicated loss window is **T5–8**, not the early game. The two infinite lines exist so a stalled late game has an exit — 98% of wins don't need them.

---

## 4. The doubling suite — who copies what

Four permanents multiply Ulalek's output. They do **different, non-overlapping** jobs; knowing which one catches which trigger is most of piloting this deck.

| Piece | Copies/doubles | Does NOT touch | Cost per extra round |
|---|---|---|---|
| **Ulalek** (trigger) | All spells you control + all other activated/triggered abilities on the stack | Anything if you skip the payment | `{C}{C}` per instance |
| **Echoes of Eternity** | Triggered abilities of **colorless spells** (cast triggers!) *and* colorless **permanents**; separately copies every colorless spell you cast | Colored spells/permanents (Garruk's Uprising, Shadow in the Warp) | free, passive |
| **Roaming Throne** (name Eldrazi) | Triggered abilities of Eldrazi **creatures you control** — including **Ulalek's own trigger** (= two `{C}{C}` rounds per cast), annihilator and attack triggers, Azlask experience, Linebreaker, Dispatcher | **"When you cast" triggers of spells** — those trigger from the stack, and CR 109.2's "creature you control" means a permanent. Also noncreature permanents (Unsealing, From Beyond) | free, passive |
| **Abstruse Archaic** | Any one activated **or triggered** ability from a colorless source, on demand — the only piece that can copy **Eye of Ugin's activation**, a land ability, From Beyond's sac-search, Azlask's pump, or Ulalek's trigger itself | Mana abilities; sorcery-speed-only if you have no untap | `{1}` + tap (+ the copied trigger's own cost — copying Ulalek's trigger really costs `{1}` + tap + `{C}{C}`, per the official Archaic ruling) |

Stacking: these are additive. With **Echoes + Throne** out, one Eldrazi cast gives **three** instances of Ulalek's trigger — three optional `{C}{C}` payments, each a full "copy everything" round, and each later instance also copies the spell-copies the earlier ones created. This is how non-infinite turns still end games.

**Rules corner (memorize these five):**

1. **Copies are not cast.** No Ulalek/Sanctum/Unsealing/Cicada/Shadow retriggers off copies. Only real casts count.
2. **Token copies of legends die to the legend rule — *after* their ETB abilities trigger.** A copied Ulamog still sees its enter effects; a copied Azlask dying even nets an experience counter.
3. **Cast triggers stack with the spell.** Ulalek's trigger goes on the stack *above* the Eldrazi spell that caused it, so when it resolves the spell is still there to be copied — and any cast triggers (its own, Unsealing's, Sanctum's) are "abilities you control" and get copied too.
4. **Echoes is itself an Eldrazi spell** (Kindred Enchantment — Eldrazi): casting it triggers Ulalek, and From Beyond can tutor it.
5. **Thief of Existence's second exile** comes from Ulalek copying its *cast trigger* on the stack (the token copy is not cast, so it has no cast trigger of its own).

---

## 5. The golden rule: {C}{C} discipline

Never cast an Eldrazi spell without asking what the copy buys — "one extra spell for 2 mana" is the best rate in the deck. Bank `{C}{C}` from the moment Ulalek lands to the end of the game. When sequencing a turn, cast the *cheap* Eldrazi first only if you can also afford the tax on the *big* one; if you can pay only once, spend it on the spell whose copy is worth the most (cheat sheet, §12).

Cost reducers effectively discount the tax too, since they free the mana that pays it. They stack: **Eye of Ugin** (−2 colorless Eldrazi) + **Urza's Incubator** (−2 Eldrazi creatures) + **It That Heralds the End** (−1 colorless MV7+) + **Herald of Kozilek** (−1 colorless) makes Ulamog, the Ceaseless Hunger cost `{4}` — with `{C}{C}` spare for the copy.

---

## 6. The winning packages

Ranked roughly by how often they close games. None except 6f is infinite — they are "a lot of damage," which is what bracket 3 wants. Pick the package the board dictates; every tutor from T5 on should be fetching the missing piece of one of these.

### 6a. Board theft alpha strike — Flayer of Loyalties / Hideous Taskmaster / Emrakul, the World Anew

Win with **their** creatures, on **your** turn, with haste and annihilator.

- **Flayer of Loyalties** (`{8}{C}{C}`, 10/10) + `{C}{C}`: the copied cast trigger steals a **second** creature — both untapped, base 10/10, trample, annihilator 2, haste, until end of turn. That's 20 hasty trample power plus 4 annihilator sacrifices, and Flayer isn't legendary, so you *keep both* the original and the 10/10 token twin. Aim stolen commanders at their own owners.
- **Hideous Taskmaster** (`{6}{R}`, 7/2) + `{C}{C}`: "for each opponent, gain control of up to one target creature that player controls" — copied and retargeted, that's **up to two creatures per opponent**, untapped, with trample/haste/annihilator 1 until end of turn, plus a 7/2 token twin with the same keywords. Regularly 6 stolen bodies and 6 annihilator triggers against a developed table.
- **Emrakul, the World Anew** (MV 12; **madness — pay six `{C}`**) + `{C}{C}`: gain control of **all creatures two target players control** — not until end of turn; you keep them as long as Emrakul stays. The 12/12 has flying and protection from spells and from permanents cast this turn. The madness cast is real here: Kozilek, the Great Distortion refills your hand, you discard Emrakul to hand size at cleanup, and six `{C}` + `{C}{C}` steals two armies. **Timing caveat (oracle-verified):** when Emrakul *leaves* the battlefield you sacrifice **all creatures you control** — stolen *and* your own. Fire it as a finisher, not a value play, and don't cast your own board into its exit clause.

**When to fire:** the "everyone else developed while I ramped" board. Theft converts their board advantage into your lethal turn — don't fire it into an empty table.

### 6b. Conscription turns — Eldrazi Conscription is an Eldrazi spell

Eldrazi Conscription (`{8}`, Kindred Enchantment — Eldrazi Aura) triggers Ulalek. Pay `{C}{C}` and the spell copy resolves as a **second token Conscription attachable to a different creature**: two creatures each get +10/+10, trample, annihilator 2, for `{8}`+`{C}{C}` — and with Echoes out, **three** Conscriptions off one cast. Ulalek wearing two is a 22/25 trample annihilator 4: a one-shot commander-damage kill plus a 4-permanent strip.

- Best hosts: **Ulamog, the Ceaseless Hunger** (30/30 indestructible), **Ulalek** (21 commander damage arrives fast), or whatever **Eldrazi Linebreaker** is about to haste up — its begin-combat trigger grants haste and +X/+0 (X = your Eldrazi count) to any creature you control, replacing the cut Reality Smasher as the "Conscription hits this turn" enabler.
- It's a colorless MV 8 spell: it triggers **Sanctum of Ugin** (fetch the next threat) and exiles **Ugin's Binding** from the graveyard (one-sided mass bounce before the swing). It is **not** a creature spell, so Kozilek's Unsealing does not pay out on it.

### 6c. Azlask overrun — the go-wide kill

The deck's token engines (Kozilek's Unsealing, From Beyond, Path of Annihilation, Kozilek's Command, Chittering Dispatcher, Warping Wail) feed **Azlask, the Swelling Scourge**:

- Every colorless creature you control that dies — **including every Spawn/Scion sacrificed for mana** — gives an experience counter; Azlask sits on 4–8 by midgame passively (doubled by Roaming Throne, since Azlask's counter trigger is a creature's triggered ability).
- **`{W}{U}{B}{R}{G}`: creatures you control get +X/+X; Spawns and Scions gain indestructible and annihilator 1.** Eight 0/1 Spawns become 6/7 indestructible annihilators — 48 power across eight bodies, one forced sacrifice per attacker. **Garruk's Uprising gives them all trample**, which is what turns "chump-blocked all day" into lethal.
- Paying WUBRG in a colorless deck is the trick; **Path of Annihilation is the enabler** — every Eldrazi you control (Spawn and Scion tokens are Eldrazi) taps for any color. Backups: Planar Nexus (`{1},{T}`: any color), Path of Ancestry / Command Tower / City of Brass / Mana Confluence / Exotic Orchard / Reflecting Pool (Ulalek's identity is five-color, so "any color in your commander's identity" means any color), the duals, and Three Tree City naming Eldrazi (one big burst of a single color).
- Stack tricks: activate Azlask, then respond with an instant-speed Eldrazi cast (§10) + `{C}{C}` — the copied activation makes it +2X/+2X. Abstruse Archaic copies the activation for `{1}` + tap (plus the WUBRG for the copy is *not* needed — Archaic copies the ability, not its cost).

**When to fire:** board stalls, and games where the haymakers keep dying but the token engines survived — this line wins with nothing over MV 4 on the battlefield. Note Azlask is `{3}` — MV 3 — so it is a cheap early Ulalek trigger but **not** a Kozilek's Unsealing payout and **not** an Unsealing-loop starter (correcting an error in the v1 primer).

### 6d. Ulamog attrition — removal and inevitability

- **Ulamog, the Ceaseless Hunger** + `{C}{C}`: **exile four permanents** on cast — the best removal spell in the deck — leaving a 10/10 indestructible whose attack trigger mills 20 (**40 with Echoes** doubling it, **40 with Throne** too; with both, 60 — two attacks end a library).
- **Ulamog, the Defiler** + `{C}{C}`: two "target opponent exiles the top half of their library" triggers — halve two different players, or one player twice (¾ of their deck). It enters with +1/+1 counters equal to the greatest MV in exile (usually 6–10 after its own trigger) and has **annihilator X = its counters**, ward—sacrifice two permanents. Throne/Echoes doubling an annihilator-8 attack trigger is "sacrifice sixteen permanents."
- **All Is Dust** is the package's sweeper — a Kindred Sorcery — Eldrazi, so it triggers Ulalek (the copy mops up anything that dodged the first pass) and your ~88%-colorless board ignores it. It destroys *colored* permanents; remember it also pops your own **Imprisoned in the Moon** — sweep first, moon second, never the reverse.
- **Ultima, Origin of Oblivion**'s attack trigger blights a land (loses all types/abilities, taps for `{C}` only) — aim it at Gaea's Cradle, Cabal Coffers, or an opposing utility land; it's removal that never rotates off.

### 6e. Snowball engines (how the packages get paid for)

- **Zhulodok, Void Gorger** in the 99: your 7+ colorless spells **cast from hand** get cascade, cascade — and Ulalek's `{C}{C}` copies the cascade *triggers* too: a single Ulamog with both legends out is four free spells deep, and each cascaded Eldrazi **is cast**, so it triggers Ulalek again. Caveat: Mystic Forge top-of-library casts are *not* from hand — no cascade on those.
- **Mystic Forge**: ~80% of the deck castable off the top, every turn — the deck's grind engine and the direct replacement for Nulldrifter's card-advantage job. With **Conduit of Ruin** stacking an MV7+ creature on top, the tutored threat is often castable the same turn at −2 from Conduit's own reduction.
- **Kozilek, the Great Distortion** + `{C}{C}`: double refill-to-seven (stack the triggers so the first resolves while you're empty), then a counterspell engine on a 12/12 menace body — discard a card of MV X to counter a spell of MV X.
- **Kozilek, the Broken Reality** + `{C}{C}`: each trigger has up to two target players manifest two cards from hand, you draw one per manifest — up to draw 8 across both triggers, while shrinking opposing hands into face-down 2/2s.
- **Garruk's Uprising**: 15 of the deck's creatures have power 4+ — including *every* MV7+ haymaker — so each bomb now draws a card, and the Ulalek/Echoes token copy of a creature spell **also enters and draws again**. Plus team-wide trample (the annihilator bodies stop being chump-blockable). Green, so Echoes doesn't copy it — its value is all battlefield.
- **Ugin, Eye of the Storms** + Echoes: every colorless spell you cast exiles **two** colored permanents. A removal engine, not a combo — and most of your deck is colorless spells.
- **Ultima, Origin of Oblivion** + **Forsaken Monument**: each is "tap a permanent/land for `{C}`, add an extra `{C}`" — they stack, so Ancient Tomb/Eldrazi Temple/Urza's Tower start producing absurd mana, and the `{C}{C}` tax becomes free.

### 6f. The escape hatches — the two sanctioned infinite lines

Per the house bracket-3 policy these are **late-game lines only** — break a stalemate with them, don't race. Spellbook-verified on the exact v2 99: these are the only two.

- **Ulalek + Echoes of Eternity + Kozilek's Unsealing** → infinite Spawn, infinite `{C}`, draw the deck. Cast any **MV 4–6 Eldrazi creature** with `{C}{C}` spare. Echoes doubles both Ulalek's and Unsealing's triggers; resolve one Ulalek trigger paying `{C}{C}` — it copies the spell and all other triggers on the stack; the doubled Unsealing triggers make four Spawns; sacrifice two to repay `{C}{C}` for the next copied Ulalek trigger. Each cycle nets +2 Spawns and re-copies everything. Convert: infinite `{C}` → cast the whole deck (Unsealing draws 3 per MV7+ creature). **Legal starters in this 99: Thought-Knot Seer (4), Sowing Mycospawn (4), a recast Ulalek (5), Conduit of Ruin (6).** (Azlask is MV 3 — not a starter. Roaming Throne is MV 4 but not an Eldrazi *spell*, so it triggers Unsealing without triggering Ulalek.)
- **Basalt Monolith + Forsaken Monument** → infinite `{C}` (Monument makes Basalt tap for 4 and untap for 3). Not a win by itself — outlets are casting your hand, Kozilek the Great Distortion refills, and arbitrarily large Kozilek's Command / Eye of Ugin activations. Rule-0 mention it at the table per the standing adjudication.

---

## 7. The mana engine

### 7a. The lands that set the schedule

The whole deck's schedule — T4 Ulalek, T6 haymakers — runs on the 2-mana lands. Protect them; opposing Wasteland effects aimed at you go here.

- **Eye of Ugin** — not mana, better: −2 on every colorless Eldrazi spell, a ritual that never expires, plus a late-game repeatable tutor (`{7},{T}`: any colorless creature to hand — and *this* activation, unlike Sanctum, can be copied by Ulalek/Archaic).
- **Eldrazi Temple, Ancient Tomb** — `{C}{C}` every turn (Tomb costs 2 life).
- **Ugin's Labyrinth** — `{C}{C}` if you imprint a 7+ colorless card from hand (20+ hits in the deck). Don't fetch it when the hand is all small spells; you can retrieve the imprinted card later by tapping it for the return mode.
- **The Urza package: Urza's Mine / Power Plant / Tower + Planar Nexus.** Nexus is *every* nonbasic land type, so it counts as all three Urza lands at once: Nexus + Tower = 4 mana from 2 lands; the full set = 8 from 4. Sim-honest expectation: a powered pair by T6 in **~18% of games** — an upside wedge, not the engine. The floor is fine (each is a Wastes), which is why they made the cut. Nexus also taps for any color (`{1},{T}`) — an Azlask helper.
- **Vesuva** — enters tapped as a copy of any land: Temple/Tomb #2, **or Urza's Tower #2** (Tower + Vesuva-Tower + Nexus = 7 mana from 3 lands), or the table's best land. It can't usefully copy Eye (legendary).
- **Three Tree City** (name Eldrazi) — `{2},{T}`: one color × your Eldrazi count, tokens included. Ramp *and* the single biggest Azlask/colored-cost enabler after Path of Annihilation.
- **Tomb of the Spirit Dragon** — `{C}` plus a lifegain faucet (`{2},{T}`: 1 life per colorless creature) that buys archenemy turns.
- **Bonders' Enclave** — `{3},{T}`: draw a card with a power-4 creature out. Almost always on from T5.
- **Utility:** Boseiju (interaction in a land slot), Wasteland, Cavern of Souls (§9), Sanctum of Ugin (§8), Winding Canyons + Emergence Zone (§9), Yavimaya Cradle of Growth (every land taps for G — it alone fixes Beast Within/Heroic Intervention).

### 7b. Rocks and reducers

Deployment order on T1–3: **fast rock ≥ cost reducer ≥ everything else.** Sol Ring/Mana Vault/Basalt/Thran Dynamo and the 2-drops accelerate the commander; the reducer stack (§5) accelerates everything after him. Note **Fellwar Stone** taps for "any color an opponent's land could produce" — colorless is not a color, so it's the one rock that can never pay the `{C}{C}` tax, Kozilek's Command's `{C}{C}`, or Echoes' `{C}{C}{C}` (it *does* cast Ulalek, whose pips take any mana). Reflecting Pool, by contrast, adds any *type* a land you control could produce — type includes colorless — but only ever one mana (it does not copy Tomb's "2").

---

## 8. Card advantage, digging, and tutors

The deck's diagnosed structural weakness (2026-08-27 analysis) is **early/mid-game card flow**: nearly all card advantage is back-loaded onto already casting a fatty. The v2 answers, cheapest first — use them aggressively:

- **Ancient Stirrings** (`{G}`, T1 play): look at top 5, take a colorless card — with 88/99 colorless cards it's effectively "dig 5, take the best card" (odds of a total whiff: ~0.0006%). Land when land-light, rock or threat when flooded. It also finds Urza pieces opportunistically (lands are colorless cards).
- **Garruk's Uprising** (`{2}{G}`): a card per power-4 creature entering — every haymaker cantrips, token copies included.
- **Kozilek's Unsealing** (`{2}{U}`, devoid): the engine that makes the midgame function. **Creature spells only** (verified): MV 4–6 → two Spawns (ramp); MV 7+ → draw three. Echoes doubles it; Throne does not (it's an enchantment).
- **Mystic Forge / Bonders' Enclave / Kozilek refills / Ugin +2**: the T6+ grind layer.

### Tutor matrix — what to fetch, when

**Land tutors — Crop Rotation (instant!) and Sowing Mycospawn** (Sylvan Scrying was cut; Stirrings is the soft third finder):

| Phase / situation | Fetch |
|---|---|
| T1–3, developing | **Eye of Ugin**, then Eldrazi Temple / Ancient Tomb |
| Turn before your first 7-drop | **Sanctum of Ugin** — converts the haymaker into the next one |
| Blue mage holding mana | **Cavern of Souls**, name Eldrazi |
| Urza wedge live (Nexus or 2 pieces already down) | the missing **Urza land** or **Vesuva** |
| Going for the Azlask kill | **Three Tree City** or **Planar Nexus** (Path of Annihilation from hand is still better) |
| Problem land or Blood Moon meta | **Wasteland** / **Boseiju** target list |
| Wipe-heavy table | **Winding Canyons** (repeatable) or **Emergence Zone** (one shot, *everything* — including an end-of-turn All Is Dust) |
| Hand has a spare 7+ card | **Ugin's Labyrinth** |

**Crop Rotation is the deck's only instant-speed land search — spend it like a spell, not like ramp:** end-of-turn Sanctum with a haymaker in hand; Cavern *in response* to sighting counter-mana; Eye mid-combat-math on the turn the discount matters. It's one of the deck's three Game Changers — never fetch casual value with it. (It sacrifices a land as a cost — with zero basics, sac your worst dual.)

**Sowing Mycospawn is the best tutor in the deck** because Ulalek doubles it: the cast trigger searches a land **onto the battlefield**, so with `{C}{C}` you get **two lands, untapped** — Eye + Temple is +4 effective mana on the spot. Kicked (`{1}{C}`) and copied it also **exiles two lands** (Strip Mine twice, attached to a 3/3), and at MV 4 it triggers Unsealing for 2 Spawns (4 with Echoes) and can start the infinite loop.

**Creature tutors:**

- **Conduit of Ruin**: cast trigger searches an MV 7+ colorless creature **to the top** — copied, you stack your next *two* draws. Defaults: Ulamog the Ceaseless Hunger (removal + clock), Kozilek the Great Distortion (gas), Emrakul (theft finisher). With Mystic Forge out, the topped card is castable immediately; Conduit's own −2 discounts it.
- **Sanctum of Ugin** (sac on your colorless 7+ cast → any colorless creature to hand): midgame, chain haymaker → haymaker; when a §6 package is one piece short, fetch the piece — Azlask, Taskmaster/Flayer into developed boards, Elder Deep-Fiend when you need a Fog. **The sacrifice is part of the trigger's resolution, so Ulalek/Echoes copies of Sanctum's trigger fizzle — one Sanctum, one search.** Don't count on doubling it.
- **Eye of Ugin, late** (`{7},{T}`): same search, but **this one doubles** — activate, respond with an instant-speed Eldrazi + `{C}{C}` (or Abstruse Archaic), get two creatures.
- **From Beyond** (`{1}{G}` + sac): tutors **any Eldrazi *card*** — including **Echoes of Eternity**, **Eldrazi Conscription**, **Kozilek's Command**, **All Is Dust**, **Eldritch Immunity**, **Not of This World** — not just creatures. The sacrifice is an activation *cost*, so unlike Sanctum the Ulalek/Archaic copy **works**: two Eldrazi cards. (It cannot fetch Kozilek's Unsealing — devoid, but not an Eldrazi card.) Until then it makes a Scion every upkeep.

**Sequencing rule of thumb: turns 1–4 every tutor is a mana tutor; turns 5+ every tutor is a kill-package tutor.** Standing exception: fetch Sanctum the turn before any planned 7-drop, always.

---

## 9. Interaction, protection, and surviving as archenemy

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

And remember the engine core — Unsealing, Echoes, From Beyond, Path of Annihilation, Garruk's Uprising, the rocks — survives creature wipes entirely. Cast triggers mean even a swept haymaker already paid out. You rebuild faster than anyone at the table.

### Protecting the key pieces

Priority order — protect these, in order:

1. **Ulalek** — every plan runs through the trigger. **Lightning Greaves the turn it lands**; it eats every removal spell at the table. Recasting is tolerable (hybrid pips make tax payable) but each recast is a haymaker turn lost.
2. **Echoes of Eternity** — the single most powerful permanent in the list; informed opponents kill it on sight. Deploy it the turn you can *use* it — with a haymaker behind it — not into three untapped boards for value. Casting it triggers Ulalek: with `{C}{C}` you get a **token copy of Echoes itself**.
3. **Kozilek's Unsealing** — the engine that keeps the hand full; quietly wins long games alone.
4. **Eye of Ugin / Temple / Tomb** — the difference between T4 and T6 Ulalek.
5. **Mystic Forge / Roaming Throne / Forsaken Monument** — the grind and doubling layer; Throne at least has ward `{2}`.

### Threat assessment and politics

You are visibly the archenemy from T6 — plan for it. Early, ramp reads as "slow deck"; stay off the radar until the first doubled haymaker. Spend theft triggers and Ulamog exiles on the player who can punish you fastest, not the biggest creature. Your exile-based removal (Ulamogs, Ugins, Ugin's Binding, All Is Dust) ignores indestructible and graveyards — aim it accordingly. Because nearly every threat replaces itself (Sanctum, Unsealing, Uprising, Kozilek refills, Forge), you can trade haymakers one-for-one with removal all game — the opponent who runs out of answers first is the one you kill first.

---

## 10. Stack tricks — instant-speed Eldrazi as trigger keys

Ulalek only fires on an Eldrazi **cast**, so instant-speed Eldrazi are what turn your activated abilities into doubled ones. Native keys: **Kozilek's Command**, **Eldritch Immunity**, **Not of This World**. With **Liberator or Skittering Cicada** out (or a Winding Canyons/Emergence Zone activation), *every* Eldrazi is a key. The pattern: activate an ability → while it's on the stack, cast the key + pay `{C}{C}` → Ulalek's trigger copies the ability.

Confirmed-working targets:

- **From Beyond's sacrifice-search** → two Eldrazi cards (sac is a cost; the copy searches free).
- **Eye of Ugin's `{7}` tutor** → two colorless creatures.
- **Azlask's WUBRG pump** → +2X/+2X.
- **Basalt Monolith's untap**, **Kozilek's Command itself** (a copied Command keeps its modes and X).
- **Does NOT work:** Sanctum of Ugin (sac is in the resolution — the copy can't pay it); Kozilek's Return / Ugin's Binding graveyard triggers (the "exile this card" clause fails on the second copy — one each per game, spend them well).

**Kozilek's Command deserves its own note** — `{X}{C}{C}` Kindred Instant, choose two of: X Spawns / scry X + draw / exile a creature MV ≤ X / exile up to X graveyard cards. It triggers Ulalek *itself*, the copy keeps X and modes, and it's the deck's most flexible key: X=3 with `{C}{C}` is six Spawns, or double scry-draw, or two exiled creatures, at instant speed, off `{C}`-heavy mana.

**Abstruse Archaic is the fourth doubling piece** (§4) and the only *repeatable* on-demand one: `{1},{T}` copies any activated or triggered ability from a colorless source — Ulalek's trigger (true cost `{1}`+tap+`{C}{C}`), Eye's tutor, From Beyond's search, Azlask's pump, a land's ability. It snowballs because Ulalek's trigger sits above the causing spell, which is still on the stack to be re-copied.

---

## 11. Piloting: turn-by-turn shape, mulligans

**Opening hand:** 2–4 lands including a Tomb/Temple-class land or a 2+ mana rock, plus a cost reducer or an engine piece (Unsealing / Stirrings / Shadow in the Warp). A hand that casts Ulalek by T4 with one engine behind it is a keep; five haymakers is not — **this deck mulligans for its curve, not its top end.** Ancient Stirrings makes marginal one-land hands keepable more often than v1.

- **T1–3:** land, rock, reducer, in that order. Stirrings on T1 with spare mana. The only colored pips that matter early are green (~15 sources). Don't run Ulalek out on T3 without protection unless the table is friendly.
- **T4–5:** Ulalek + Greaves. **Bank `{C}{C}` from here to the end of the game.** Hold Wail/Denial when possible — the loss window is T5–8 as archenemy, and one countered sweeper usually buys the winning turn. Deploy Unsealing/Uprising before the haymaker turns start.
- **T6+:** one haymaker per turn, always with the copy tax, each chaining through Sanctum/Unsealing/Uprising/Forge into the next. Pick the §6 package the board dictates: theft into developed boards, Azlask off tokens, Ulamogs for attrition, Conscription for the commander-damage clock. With Liberator/Cicada out, shift the whole routine to opponents' end steps and keep interaction up on your own turn.
- **Echoes lands → re-read your board.** It doubles *every* triggered ability of your colorless spells and permanents, not just combo pieces: annihilator (annihilator 2 = four sacrifices), Ulamog's mill-20, Ugin Eye of the Storms' exile, Unsealing, Ulalek himself. When Echoes is out your worst spell beats their best one — play like it, because they will kill it the moment they untap.
- **Throne lands → recount your triggers.** Two `{C}{C}` rounds per Eldrazi cast, doubled annihilator and attack triggers, doubled Azlask counters. Remember what it *doesn't* do: cast triggers of spells (that's Echoes) and noncreature permanents' triggers.

---

## 12. Cheat sheet — what `{C}{C}` buys on every Eldrazi spell

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
| Azlask, the Swelling Scourge | Token twin dies to legend rule → +1 experience counter minimum |
| Eldrazi Linebreaker | 3/3 trample token twin; two begin-combat haste/pump triggers each turn after |
| Chittering Dispatcher | Token twin; every myriad copy that dies makes a Spawn |
| Zhulodok, Void Gorger | Token twin dies to legend rule, but the cast still cascaded if 7+ from hand |
| Ulalek (recast) | MV 5 Eldrazi — a legal starter for the Unsealing loop |

Colorless but **not** Eldrazi spells — they never trigger Ulalek, but Echoes copies them, and Ulalek's trigger copies them if they're on the stack under it: Ultima, Skittering Cicada, Roaming Throne, Liberator, Abstruse Archaic, Mystic Forge, all rocks, all three Ugins, Kozilek's Return, Ugin's Binding, Warping Wail, Kozilek's Unsealing, Forsaken Monument. (Ugin, Eye of the Storms + Echoes: an Eldrazi cast while both are out exiles **two** colored permanents *on top of* everything above.)

---

## 13. Bracket & house-rules compliance

- **Game Changers: exactly 3** (the bracket-3 cap) — Mana Vault, Ancient Tomb, Crop Rotation. Verified against the Aug-2026 list; Mana Drain and Boseiju are **not** on it, and none of the v2 additions is.
- **Combos: exactly the two adjudicated late-game lines** (Spellbook re-run on the exact v2 99, 2026-08-27): Basalt Monolith + Forsaken Monument, and Ulalek + Echoes + Kozilek's Unsealing. Both are kept deliberately under the house policy (only *early-game* 2-card infinites must go); rule-0 the Basalt line at the table. No early-game infinite exists in the 99 — Kinnan and Food Chain lines were cut at earlier passes and stay out.
- **No mass land denial.** Wasteland/kicked Mycospawn are single-target land removal, legal at bracket 3.

---

## 14. Known weaknesses and tuning levers

Recorded so testing knows where to look first:

1. **Haymaker-in-hand dip** (48%→40% by T6 in the sim, upper bound): if the top-end feels thin in real games, the fix is a threat re-add — Sire of Seven Deaths or Void Winnower were the flagged candidates — *not* reverting the mana base.
2. **Zero basics**: Blood Moon–style effects and opposing Field of Ruin/Ghost Quarter are the accepted edge case. If they show up in the pod, re-add a basic or two over the weakest duals.
3. **Urza package is a wedge, not an engine** (~18% powered by T6). If you want it to fire more often, the consistency add is Expedition Map; the standing house rule (Tron-style synergy lands are low-value in singleton) says don't over-invest.
4. **Specific-land tutoring is down to Crop Rotation + Sowing Mycospawn** (accepted cost of the Ancient Stirrings swap — flagged for revert only if it bites).
5. **Colored-pip watch list:** Mana Drain `{U}{U}`, Herald of Kozilek `{1}{U}{R}`, Shadow in the Warp `{R}{G}`.
6. **Exile wipes** (Farewell-class) beat Heroic Intervention and indestructible alike — the only answer is flash-speed deployment and counterspells.

---

## 15. Provenance

- Card text: Scryfall oracle, fetched 2026-08-27 for this document.
- Combos: Commander Spellbook `spellbook_find_decklist_combos` on the exact v2 99 (2026-08-27).
- Sim numbers: 20k-game Monte Carlo per the repo's standard goldfish methodology (see `CLAUDE.md`); v1↔v2 deltas from the 2026-08-27 runs, win-mode benchmarks from the 2026-08-24 run on v1. Absolute numbers are only comparable within a run.
- Decision history and owner rulings: decision log in `deck/ulalek-bracket3-v2.txt` and `deck/ulalek-v2-proposal.md`. Card choices adjudicated there (Herald of Kozilek, Hideous Taskmaster, Path of Annihilation keeps; Devourer of Destiny, Rise of the Eldrazi rejections; Fellwar/Cicada/Archaic cut reversals) are settled — don't re-litigate.
