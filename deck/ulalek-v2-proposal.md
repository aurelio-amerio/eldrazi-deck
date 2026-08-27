# Ulalek v2 proposal — feedback pass (2026-08-27)

Sources: `feedback.md`, `temurlalek.txt` (friend's Temur Ulalek), `5c-eldrazi-20260818-090308.txt` (friend's 5c Eldrazi).
Draft list: `deck/ulalek-bracket3-v2.txt` (v1 untouched).

## TL;DR

10 swaps (revised 2026-08-27 after owner review — Herald of Kozilek, Hideous Taskmaster
and Path of Annihilation stay; Devourer of Destiny rejected). Lands 34 → 36 (Urza package
+ Planar Nexus + Reflecting Pool + Boseiju), ramp quality up (Thran Dynamo, Mystic
Forge), and the two requested creatures (Roaming Throne, Liberator) are in. The two slots
for Liberator and Forge come from **Emergence Zone** (Liberator is the repeatable version
of the same effect) and **Nulldrifter** (Forge takes over its card-advantage job; the
only big-Eldrazi cut, and the weakest cast trigger of the ten). Sim says v2 is ~2-3
points faster on every mana metric; bracket-3 status unchanged (same 2 late-game combos,
same 3 Game Changers).

## Response to the feedback, point by point

1. **"Basalt Monolith + Eldrazi Monument is an early 2-card combo"** — the friend means
   Basalt + **Forsaken** Monument (Eldrazi Monument isn't in the deck). Already adjudicated
   2026-08-19: it's 8 mana across two artifacts, ruled a *late-game* line and deliberately
   kept. Action: none, but do rule-0 it at the table as they suggest.
2. **"More lands, more ramp"** — accepted. 34 → 36 lands; Worn Powerstone → Thran Dynamo
   (+2 mana on the rock), Mystic Forge added as colorless velocity. Mana sources 50 → 52.
3. **"Urza lands + Planar Nexus, Reflecting Pool, Cloudpost"** — Urza trio + Nexus + Pool
   in; Cloudpost evaluated and rejected (math below).
4. **"Roaming Throne, Liberator"** — both in, with one important rules correction on Throne
   (below).
5. **"Eldrazi that are good alone and brutal when doubled — interaction on a stick"** —
   Devourer of Destiny was proposed for this and rejected by owner ruling (Hideous
   Taskmaster keeps the slot).

## The Urza package — how good is it really?

**Planar Nexus is every nonbasic land type**, so it counts as Urza's Mine *and*
Power-Plant *and* Tower (and Locus) simultaneously:

- Nexus + Tower = 4 mana from 2 lands (Tower taps for 3)
- Nexus + Mine or Power Plant = 3 mana from 2 lands
- All four = 8 mana from 4 lands
- Nexus is fetchable by Crop Rotation, Sylvan Scrying, kicked Sowing Mycospawn (it is
  **not** a Forest — Nature's Lore/Three Visits can't get it)
- Ultima, Origin of Oblivion doubles every {C} these lands make (Tower + Ultima = 6)

**Honest sim numbers** (20k games, greedy tutors included): a powered Urza land by T5 in
~16% of games, T6 ~18%, T8 ~22%. So in singleton this is an **upside wedge, not the
deck's engine** — the collection-of-memories house rule about Tron lands in singleton was
directionally right. The reason the package still makes the cut: the floor is fine. An
unpowered Urza land in this deck is just a Wastes, and we're cutting exactly the three
lands whose floor was worse (Snow-Covered Wastes, Cascading Cataracts, and a painland
whose colors we barely use). If after testing you want the wedge to fire more often, the
first consistency adds are **Vesuva → copy your own Tower** and **Expedition Map** (see
optional module).

**Cloudpost: rejected.** Max 2 Loci in singleton (Cloudpost + Nexus) → Cloudpost taps for
2 and enters tapped. Reflecting Pool and any Urza land have a better ceiling and floor.

**Reflecting Pool: in.** With 35 other lands it's a second Command Tower that can also
copy Ancient Tomb/Eldrazi Temple's "2".

## Roaming Throne — one rules correction

Throne (naming Eldrazi) does **not** double "when you cast" triggers of Eldrazi spells
(Ulamog's exile-two, Flayer's steal, etc.). Those abilities trigger from the *stack*, and
Throne's "triggered ability of another **creature you control**" means a creature
*permanent* (CR 109.2). Compare Echoes of Eternity, which was explicitly worded "a
colorless **spell** you control *or* another colorless permanent" to catch both. Echoes
doubles cast triggers; Throne doesn't.

Throne is still a core add because what it *does* double is better:

- **Ulalek's own trigger** (Ulalek is an Eldrazi creature on the battlefield): every
  Eldrazi cast gives you **two** {C}{C} payments → two rounds of "copy all spells and
  abilities". The second instance re-copies the original spell still on the stack, so one
  Eldrazi cast + 4 mana = spell + 2 copies plus doubled ability copies.
- Annihilator attack triggers of every other Eldrazi (Ulamog the Defiler attacks for 8×2).
- ETB/LTB/battlefield triggers: kicked Sowing Mycospawn (2 land searches), Chittering
  Dispatcher myriad + death-spawn, Azlask experience counters.
- 4/4 ward {2} colorless body, castable off Eye of Ugin/Incubator discounts? (No — it's a
  Golem, not an Eldrazi, so Incubator/Eye/Cavern don't help it. Minor.)

## Liberator, Urza's Battlethopter

Nearly every spell in the deck is colorless or artifact → the whole deck gains flash.
This directly upgrades the 2026-08-26 resilience pass (deploy into a wipe-threatening
board only at the last end step). Emergence Zone initially made way for it, then came
back in the Forest slot by owner follow-up — Liberator is a 1/2 that eats removal, and
the Zone also flashes *noncreature* spells (end-of-turn All Is Dust). It also weaponizes
Mana Drain mana and idle interaction mana:
hold up Drain/Wail/Denial, and if nothing needs countering, flash in a threat. Flash, a
growing body, and {3} generic make it strictly on-plan. Note it does *not* untap your
lands — big flashy turns still want Thran Dynamo/Basalt online.

## Sim results (20k games per side, same script and assumptions both sides)

| Metric | v1 | v2 |
|---|---|---|
| Commander castable by T4 | 63.4% | **64.9%** |
| Commander castable by T5 | 85.6% | **87.1%** |
| 7 effective mana by T4 | 27.8% | **29.6%** |
| 7 effective mana by T5 | 50.8% | **53.0%** |
| 7 effective mana by T6 | 68.0% | **70.8%** |
| First MV7+ threat castable & in hand, by T6 | 48.0% | 39.9% |

The metric that dips is "haymaker in hand": v1 ran 12 MV7+ pieces, v2 runs 9
(Conscription, Bahamut and Nulldrifter left), so you *hold* one less often. The sim
can't model the three things pulling the other way — Mystic Forge casting threats off the
top (the direct replacement for exactly this), Liberator converting opponents' turns into
deployment time, and Sanctum/Conduit tutoring the threat you need — so treat the dip as
an upper bound. Roaming Throne isn't modeled either (no mana effect). If the dip bothers
you in testing, the fix is a threat re-add from the optional module (Sire of Seven
Deaths, Void Winnower) rather than reverting the mana base.

Caveat: this is a fresh re-implementation of the sim, so absolute numbers differ slightly
from the 2026-08-19 benchmarks; only the v1↔v2 deltas are meaningful.

## Bracket / combo verification

- Commander Spellbook on the full v2 list: included combos are exactly the two adjudicated
  late-game lines — **Basalt + Forsaken Monument** and **Ulalek + Echoes + Kozilek's
  Unsealing**. No new combo from any add.
- Game Changers (Aug-2026 list checked): none of the 11 adds is a GC. Still at the cap of
  3 (Mana Vault, Ancient Tomb, Crop Rotation). Boseiju confirmed **not** a GC. The One
  Ring (in the friend's deck) is a GC and stays out per the existing deferred ruling.

## The 10 swaps (as revised by owner review, 2026-08-27)

| Out | In | Why |
|---|---|---|
| Snow-Covered Wastes | Planar Nexus | strict upgrade in the same "colorless land" slot |
| Cascading Cataracts | Urza's Tower | Cataracts' fixing was for pips the deck barely uses |
| Shivan Reef | Urza's Mine | U/R painland; U covered by 8+ other sources |
| Awakening Zone | Urza's Power Plant | From Beyond is the better copy of this effect and stays |
| Eldrazi Conscription | Reflecting Pool | 8-mana win-more aura; no cast-trigger synergy |
| Summon: Bahamut | Boseiju, Who Endures | slow saga; Boseiju = interaction in a land slot |
| Eldrazi Displacer | Roaming Throne | Displacer had no ETB engine left after the Fleshraker cut |
| Forest | Liberator, Urza's Battlethopter | net effect of two owner-reviewed steps (Emergence Zone → Liberator, then Forest → Emergence Zone back). Boseiju keeps a green land in the slot; Lore/Visits keep 3 untapped-dual targets (they never wanted the basic first anyway); Prismatic Vista down to 2 basics |
| Worn Powerstone | Thran Dynamo | feedback: denser ramp |
| Nulldrifter | Mystic Forge | Forge does Nulldrifter's card-advantage job every turn; weakest cast trigger in the crowded 7+ slot. Alternate cut if no big should go: Abstruse Archaic |

Owner rulings recorded in this pass: **keep Herald of Kozilek, Hideous Taskmaster, Path
of Annihilation; Devourer of Destiny rejected.**

Colored-pip audit after the swaps: green stays the main splash (~15 sources for Beast
Within/Heroic Intervention/ramp), Mana Drain {U}{U} and Herald of Kozilek {1}{U}{R}
remain the hardest casts (Shivan Reef's departure costs Herald one U/R source — Steam
Vents, Ketria, City/Confluence/Tower and Reflecting Pool still cover it), and Shadow in
the Warp ({R}{G}) is kept on raw power — watch those in testing.

## Card-by-card: everything in the example decks not already covered

Cards already in v1 are skipped (≈45 overlaps). ✅ = added in v2, 🔶 = optional module,
❌ = evaluated and passed.

### From `temurlalek.txt` (Temur Ulalek)

| Card | Verdict | Notes |
|---|---|---|
| Roaming Throne | ✅ | see rules note above |
| Thran Dynamo | ✅ | |
| Mystic Forge | ✅ | |
| Ancient Stirrings | 🔶 #1 | {G}: dig 5 for any colorless card = ~75/99 hits incl. every Urza piece; first non-land add if a slot opens |
| Up the Beanstalk | 🔶 | {1}{G}, draws on ~every real spell you cast; cheap engine |
| Herald's Horn | 🔶 | Eldrazi cost −{1} + ~22% free top-of-library hits |
| Deflecting Swat | 🔶 | free with commander out; was already a runner-up in the GC-slot review |
| Farseek | 🔶 | complements Lore/Visits (fetches the non-Forest duals) if you want a 16th ramp slot |
| Gemstone Caverns | 🔶 | free T0 land when not on the play; pure variance, fine in a proxy deck |
| Sire of Seven Deaths | 🔶 | great standalone 7-drop, but no cast trigger = no Ulalek payoff beyond a token copy; first threat re-add if the top-end feels thin |
| Snapping Voidcraw | 🔶 | 3-mana creature that taps for {C}{C}; fine if creature-count ramp is wanted |
| Wastescape Battlemage | 🔶 | cheap Eldrazi body + kicker interaction |
| Emrakul, the Promised End | 🔶 | usually ~{9}-{10} here; only if a big slot ever opens |
| Glaring Fleshraker | 🔶⚠️ | legal again (Food Chain gone), but Ulalek+Fleshraker+Throne and +Echoes are listed infinites — late-game by mana cost, policy-OK, but know you're adding combo #3/#4 |
| Kinnan, Bonder Prodigy | ❌ | house policy: Kinnan+Basalt is an early 2-card infinite |
| The One Ring | ❌ | Game Changer; deck is at cap (existing deferred ruling) |
| Descendants' Path | ❌ | ~23/99 hit rate → whiffs most upkeeps |
| Birds of Paradise / Kiora's Follower / Fanatic of Rhonas / Notary Hobbits | ❌ | colored dorks, weak topdecks; deck ramps on rocks+lands |
| Elemental Bond / Garruk's Uprising / Rishkar's Expertise | ❌ | Unsealing/Henge/Shadow already cover draw without extra green pips (Shamanic Revelation precedent) |
| Darksteel Monolith | ❌ | 8-mana rock; at 8 mana this deck wants to cast Eldrazi, and free casts skip Ulalek value less than they add |
| Time Spiral | ❌ | {U}{U}, uncastable here (and refills opponents) |
| Mana Maze | ❌ | cute (colorless spells share no color, so it's one-sided vs multicolor tables) but dead vs mono/colorless; Null Elemental Blast precedent |
| Cascade Bluffs / Fire-Lit Thicket / Flooded Grove / Taiga | ❌ | filter lands and a redundant R/G dual (Karplusan + Stomping Ground cover it) |
| Tropical Island | ✅ | promoted (owner follow-up, 2026-08-27): replaced basic Island — with Prismatic Vista gone, no basic-only fetcher remains, so duals are strictly better for the same fetches. Volcanic Island came in for Mountain the same way. Zero basics accepted: MLD is forbidden at bracket 3; revisit only if Blood Moon-style effects appear in the pod |
| Secluded Courtyard / Unclaimed Territory | ❌ | creature-only fixing; Cavern + Path of Ancestry already cover it |
| Tendo Ice Bridge / Temple of the False God / Reliquary Tower / Corrupted Crossroads | ❌ | weak floors; Crossroads only fixes devoid spells (not Beast Within etc.) |
| Ghostfire Slice | ❌ | conditional 4 dmg; deck's removal wants to hit permanents, not dome |
| Eldrazi Confluence | ❌ | flexible but 3 small modes for 4 mana; Kozilek's Command covers |
| Spawnbed Protector / Twins of Discord / Benthic Anomaly | ❌ | weak 7s (Benthic was already cut 2026-08-19) |
| Selective Obliteration / Null Elemental Blast | ❌ | previously cut, nothing changed |

### From `5c-eldrazi-20260818-090308.txt` (only cards not covered above)

| Card | Verdict | Notes |
|---|---|---|
| Planar Nexus | ✅ | best card in their deck per the feedback; agreed for the land package |
| Urza's Mine / Power Plant / Tower | ✅ | full trio — any one + Nexus already pays off |
| Reflecting Pool | ✅ | |
| Boseiju, Who Endures | ✅ | |
| Liberator, Urza's Battlethopter | ✅ | |
| Devourer of Destiny | ❌ | proposed (exile-on-cast that doubles, free opening-hand filter) — rejected by owner ruling 2026-08-27 |
| Vesuva | ✅ | promoted from the optional module (owner follow-up, 2026-08-27): replaced Prismatic Vista, which had become the deck's only basic-only fetcher with just 2 targets left |
| Expedition Map | 🔶 | {1}+{2}: any land to hand; the consistency knob for the package |
| Urza's Cave | 🔶 | land-slot land tutor, but {3}+sac+tapped is slow |
| Strip Mine | 🔶 | Wasteland #2 if the meta calls for it |
| Talon Gates of Madara | 🔶 | phase-out is real interaction/protection in a land slot; {4} from hand late |
| Thespian's Stage | 🔶 | weaker Vesuva (costs 2+tap each use) |
| Sensei's Divining Top | 🔶⚠️ | good with Forge + fetches; note Top+Forge+Ugin the Ineffable is a listed draw engine (late-game, policy-OK) |
| Void Winnower | 🔶 | best "big stax" option if a big slot ever opens |
| It That Betrays | 🔶 | brutal with our annihilator count, but 12 MV and the top-end is full |
| Breaker of Creation | 🔶 | hexproof-from-colors is real protection; top-end is full |
| Anticausal Vestige | 🔶 | warp = two Ulalek triggers from one card; interesting midgame value |
| Spawn-Gang Commander | 🔶 | 3 spawn on cast (6 with Ulalek) feed {C}{C} payments; R pip |
| Void Grafter / Writhing Chrysalis | ❌ | protection/value covered by Cicada/Immunity/Heroic; Chrysalis is a combo piece with Ulalek+Echoes we don't need |
| Cloudpost | ❌ | max 2 Loci in singleton (with Nexus); enters tapped; see math above |
| Sarkhan's Unsealing | ❌ | Kozilek's Unsealing + Shadow in the Warp already cover cast payoffs without the R pip |
| Chromatic Lantern | ❌ | 3-mana pure fixing; the deck casts everything off {C} already |
| Kindred Dominance / Toxic Deluge / Blasphemous Act | ❌ | {B}{B}/{B}/{R} pips; All Is Dust + Kozilek's Return + Ugins cover sweepers |
| Adarkar Wastes / Battlefield Forge / Brushland / Caves of Koilos / Llanowar Wastes / Sulfurous Springs / Underground River / Plains / Swamp | ❌ | W/B splash lands for a build we're not playing |
| Shrine of the Forsaken Gods | ❌ | 7-lands conditional {C}{C}; Urza package is the better version of this slot |
| Herd Heirloom | ❌ | creature-only mana + a trample/draw mode our threats don't need |
| Sensei's Top covered above; The One Ring / Kinnan covered above | | |

### v1 cards the friend also runs, that v2 cuts anyway

Eldrazi Displacer is in the 5c list, Awakening Zone and Nulldrifter in the Temur list —
the cuts are about *this* deck's slot pressure, not the cards being bad. Displacer in
particular comes back the moment Glaring Fleshraker does.

## What was NOT cut (per owner rulings)

Herald of Kozilek, Hideous Taskmaster and Path of Annihilation stay (2026-08-27 rulings);
nine of ten MV7+ Eldrazi creatures survive — only Nulldrifter goes, its card-advantage
job inherited by Mystic Forge. If you ever want to go deeper on speed, the next candidate
would be Flayer of Loyalties (best in 1v1 archenemy spots, worst when behind) — but
nothing in the sim forces it.

## Sources

- [Roaming Throne rulings (MTG Assist / Gatherer)](https://www.mtgassist.com/cards/The-Lost-Caverns-of-Ixalan/Roaming-Throne/rulings/)
- [Game Changers list, Aug 2026 (Playgroup.gg)](https://playgroup.gg/commander/game-changers)
- [Commander Brackets Beta Update — Feb 9, 2026 (WotC)](https://magic.wizards.com/en/news/announcements/commander-brackets-beta-update-february-9-2026)
- Combo data: Commander Spellbook via `spellbook_find_decklist_combos`
