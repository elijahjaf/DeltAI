# Curtain Call

A Deltarune-style turn-based battle that runs in the browser. Three heroes fight the Hollow Marionette, and on the enemy's turn you steer a heart through bullet patterns inside the battle box.

**Play:** open `index.html` in any modern browser. It has no build step and no dependencies. It uses Google Fonts when online and falls back to a monospace font offline.

## Controls

| Key | Action |
| --- | --- |
| Arrow keys / WASD | Move the menu cursor or the heart |
| Z / Enter / Space | Confirm, or strike during FIGHT |
| X / Shift | Go back. Hold while dodging to move slowly |
| M | Sound on or off |

Touch devices get an on-screen d-pad with Z and X buttons.

## The party

| Hero | HP | Fight power | Spells (EXP cost) |
| --- | --- | --- | --- |
| VESSA, knight | 150 | 64 | Flare Edge (30%, damage), Rally Cry (45%, heals everyone) |
| BROM, brute | 200 | 80 | Quake (55%, big damage), Iron Gut (20%, heals himself) |
| LUNE, seer | 110 | 36 | Mend (25%, heals one hero and can revive), Starfall (40%, damage), Aurora (65%, heals everyone) |

## Actions

- **FIGHT**: a timing bar slides toward a mark. Press Z as it crosses. The closer you are, the more damage you deal, and a dead-center hit is a 1.5x critical.
- **MAGIC**: spends shared EXP, which works like Deltarune's TP. Each hero has their own damage and healing spells.
- **ITEM**: a shared, limited bag (4 Glow Berries, 2 Honey Loaves, 1 Phoenix Tea). Any hero can use one on any teammate, including a downed one.
- **DEFEND**: halves the damage that hero takes this turn and grants 16% EXP.

**EXP** also comes from grazing. When the heart passes close to a bullet without touching it, you get a burst of EXP, plus a little more for each frame you stay close.

A hero at 0 HP is **downed**. They skip turns and regain 1/8 of their max HP each round until they are back up. Healing revives them sooner. If all three heroes are downed, it's game over.

## The Hollow Marionette

The enemy has 3200 HP and 12 attacks. It uses them in order, one per turn, and the menu text hints at the next one:

1. Needle Rain
2. Puppet Strings
3. Card Fan
4. Loose Buttons
5. Curtain Fall
6. Paper Bloom
7. Spare Heads
8. Stage Lights
9. Tangled Thread
10. Chandelier
11. Scissor Dance
12. Grand Finale

Below half HP a string snaps and the Marionette gets frantic. Every attack becomes denser and faster and deals 25% more damage.
