# Last Wish

A Deltarune-style turn-based battle that runs in the browser. Three heroes fight one of two bosses: Marionette NEO, a half-puppet, half-robot horror, or Candlemaw, a haunted candle. On the enemy's turn you steer a heart through bullet patterns inside the battle box.

All art is 16-bit style pixel art. Each sprite is drawn in code at low resolution, given a dark outline, and scaled up 2x. There are no image files.

**Play:** open `index.html` in any modern browser. It has no build step and no dependencies. It uses Google Fonts when online and falls back to a monospace font offline.

## Controls

| Key | Action |
| --- | --- |
| Arrow keys / WASD | Move the menu cursor or the heart |
| Z / Enter / Space | Confirm, or strike during FIGHT |
| X / Shift | Go back. Hold while dodging to move slowly |
| M | Sound on or off |

On the title screen, use the arrow keys to pick **Normal** or **Hard**.

Touch devices get an on-screen d-pad with Z and X buttons.

## The party

| Hero | HP | Fight power | Spells (EXP cost) |
| --- | --- | --- | --- |
| ASTRA, star knight | 150 | 64 | None. Astra has **ACT** instead of MAGIC |
| TERRESTRO, cave dweller | 200 | 80 | Crystal Spike (25%, damage), Quake (55%, big damage) |
| LUNE, moon seer | 110 | 36 | Moonbeam (15%, small heal on one hero), Mend (25%, heals one hero and can revive), Aurora (65%, heals everyone) |

- **Astra**: a knight with galaxy-colored skin and silver hair. Stars orbit her and a blue halo floats above her head.
- **Terrestro**: a hulking, dark blue cave monster with glowing crystals along his spine, dragging a stone club.
- **Lune**: a hooded seer with pale, cratered moon skin and a crescent-moon staff.

## Actions

- **FIGHT**: a timing bar slides toward a mark. Press Z as it crosses. The closer you are, the more damage you deal, and a dead-center hit is a 1.5x critical.
- **MAGIC** (Terrestro and Lune): spends shared EXP, which works like Deltarune's TP. Terrestro only has damage spells and Lune only has healing spells.
- **ACT** (Astra): the peaceful way to progress. Against Marionette NEO, the flavor text hints each turn at what it wants. Pick the matching ACT to raise its **MERCY** by 18% (15% on Hard). A wrong ACT does nothing.
  - *Applaud*: it's playing to the crowd or waiting for applause.
  - *Dance*: it holds out a hand or looks for a partner.
  - *Oil Joints*: its joints creak or screech.
  - *Untangle*: its strings are knotted or tangled.
  - *Check*: shows its stats.
  - *Reveal*: next turn, the right ACT is revealed in the flavor text and marked with a star in the ACT menu.
- **SPARE** (everyone): once MERCY reaches 100%, the enemy's name turns yellow and sparing it ends the battle peacefully. Sparing earlier does nothing.
- **ITEM**: a shared, limited bag (4 Glow Berries, 2 Honey Loaves, 1 Phoenix Tea). Any hero can use one on any teammate, including a downed one.
- **DEFEND**: halves the damage that hero takes this turn and grants 16% EXP.

**EXP** also comes from grazing. When the heart passes close to a bullet without touching it, you get a burst of EXP, plus a little more for each frame you stay close.

**Blue attacks** (Scissor Dance's blades) pass through the heart harmlessly while it stands still. They only hurt while you are moving.

A hero at 0 HP is **downed**. They skip turns and regain 1/8 of their max HP each round until they are back up. Healing revives them sooner. If all three heroes are downed, it's game over.

## The bosses

Pick the enemy on the title screen: Up/Down picks a row, Left/Right picks an option.

Attacks run in a fixed order, one per turn, and the flavor text before each one hints at the enemy's mood. Below half HP every boss turns frantic: attacks get denser and faster and deal 25% more damage.

Some attacks bend the rules:
- **Blue** bullets only hurt while you move. **Orange** bullets only hurt while you stand still.
- **Darkness**: only a pool of light around the heart shows what's coming. Glowing bullets show through the dark.
- **Reversed controls**, **strings that drag the heart**, **wind that pushes it**, **wax puddles that slow it**, and **boxes that shrink** during the attack.

### Marionette NEO (3200 HP)

A scrap-metal marionette with a cracked porcelain grin, black-tear eyes, a red LED eye, torn wings, a cannon arm and a steel claw. It glitches and twitches as it fights. Its ACTs are Applaud, Dance, Oil Joints and Untangle.

Its 21 attacks: Needle Rain, Puppet Strings, Card Fan (slow cards), Loose Buttons, Cannon Beam, Curtain Fall, Puppeteer's Pull, Paper Bloom, Spare Heads, Lights Out, Blue & Orange, Stage Lights, Tangled Thread, Mirror Mirror, Chandelier, Time Bombs, String Cage, Closing Curtains, Buzzsaws, Scissor Dance and Grand Finale.

### Candlemaw (3400 HP)

A towering chapel candle with a fanged, ember-lit maw, held in a wrought-iron candelabra. Below half HP its flames burn blue. It has one ACT besides Check: **Keep Vigil**, which always works and raises its MERCY 8% per use (6% on Hard). There's no mood to read, so Reveal isn't offered against it.

Candlemaw's fire comes in two colors, so nearly every attack is a test of **blue (stand still)** and **orange (keep moving)**, with plain white wax as the only ordinary danger. Its 12 attacks:

| Attack | What it asks of you |
| --- | --- |
| Wax Drip | blue and white wax drops; white wax leaves puddles that slow you |
| Ember Rain | a dense orange shower: keep moving while dodging white wax |
| Chord of Fire | expanding blue and orange rings |
| Candle Row | five columns flare at once, each blue or orange: read your column |
| Fire Wheel | a spinning wheel of alternating blue and orange spokes |
| Cold Draft | wind carries blue flames: let it push you and don't touch the keys |
| Hymn | wavy streams of blue or orange notes |
| Vespers | the whole stage flares blue or orange |
| Candle Volley | lobbed candles burst into blue or orange sparks |
| Meltdown | rising wax plus blue and white drips |
| Wick Whips | one blue and one orange wick sweep like pendulums |
| Last Vigil | orange ember rain plus blue rings |

## Hard Mode

- Marionette NEO has 4400 HP and Candlemaw has 4600.
- Every attack runs at its frantic level from turn one and deals about 15% more damage.
- Bullets are 10% faster, rising to 20% once the enemy is below half HP.
- MERCY rises more slowly: 15% per correct ACT against Marionette NEO (instead of 18%) and 6% per Keep Vigil against Candlemaw (instead of 8%).
- The item bag holds 3 Glow Berries, 1 Honey Loaf and 1 Phoenix Tea.
- The heart's invincibility after a hit is shorter.
