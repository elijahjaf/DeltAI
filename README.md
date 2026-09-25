# Curtain Call

A Deltarune-style turn-based battle that runs in the browser. Three heroes fight Marionette NEO, a half-puppet, half-robot boss. On the enemy's turn you steer a heart through bullet patterns inside the battle box.

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
| TERRESTRO, cave dweller | 200 | 80 | Quake (55%, big damage), Iron Gut (20%, heals self) |
| LUNE, moon seer | 110 | 36 | Mend (25%, heals one hero and can revive), Starfall (40%, damage), Aurora (65%, heals everyone) |

- **Astra**: a knight with galaxy-colored skin and silver hair. Stars orbit her and a blue halo floats above her head.
- **Terrestro**: a hulking, dark blue cave monster with glowing crystals along his spine, dragging a stone club.
- **Lune**: a hooded seer with pale, cratered moon skin and a crescent-moon staff.

## Actions

- **FIGHT**: a timing bar slides toward a mark. Press Z as it crosses. The closer you are, the more damage you deal, and a dead-center hit is a 1.5x critical.
- **MAGIC** (Terrestro and Lune): spends shared EXP, which works like Deltarune's TP. Each has their own damage and healing spells.
- **ACT** (Astra): the peaceful way to progress. Each turn the flavor text hints at what Marionette NEO wants. Pick the matching ACT to raise its **MERCY** by 25% (20% on Hard). A wrong ACT does nothing.
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

## Marionette NEO

A porcelain-and-steel marionette that hangs from a control rail. It has striped wings, a cannon arm, a puppet glove and a pulsing heart core. It has 3200 HP and 12 attacks. It uses them in order, one per turn, and the menu text hints at the next one:

1. Needle Rain
2. Puppet Strings
3. Card Fan (slow-moving cards)
4. Loose Buttons
5. Curtain Fall
6. Paper Bloom
7. Spare Heads
8. Stage Lights
9. Tangled Thread
10. Chandelier
11. Scissor Dance (blue: stand still to let the blades pass)
12. Grand Finale

Below half HP a string snaps and Marionette NEO gets frantic. Its eye and core turn red, one arm and wing go limp, and every attack becomes denser and faster and deals 25% more damage.

## Hard Mode

- The enemy has 4400 HP.
- Every attack runs at its frantic level from turn one and deals about 15% more damage.
- Bullets are 10% faster, rising to 20% once the enemy is below half HP.
- MERCY rises 20% per correct ACT instead of 25%.
- The item bag holds 3 Glow Berries, 1 Honey Loaf and 1 Phoenix Tea.
- The heart's invincibility after a hit is shorter.
