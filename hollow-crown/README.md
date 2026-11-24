# Hollow Crown

A real-time, top-down dungeon raid that runs in the browser. You fight through five phases, carrying a maxed-out late-game loadout, and end at the Hollow King. All characters, items, art, music and sound are original and generated in code. There are no image or audio files.

**Play:** open `index.html` in a modern desktop browser. There is no build step and there are no dependencies. The VT323 font loads from Google Fonts when you're online, and the game falls back to a monospace font offline. It is built for mouse and keyboard.

## Controls

| Input | Action |
| --- | --- |
| Arrow keys | Move (and, without the mouse, aim the way you move) |
| Z / left click (hold) | Attack with the current weapon |
| X / right click (hold) | Weapon ability |
| Mouse | Aim, whenever you move it or click; otherwise you aim the way you move |
| 1–4 / mouse wheel | Swap weapon |
| E | Use a console, lever or grounding rod |
| Q | Spirit Draught (heals 50% HP over 3 seconds, 2 per phase) |
| F | Wish (full heal and 2 seconds of invulnerability, once per phase) |
| P / Esc | Pause |
| M | Sound on or off |

Z also confirms on the title, loadout and dialogue screens. In console puzzles, arrow keys move a gold cursor, Z presses the highlighted tile, and X or E steps away. Clicking still works too.

## Loadout

Your character is at **Delver Mastery 50** (the maximum), with the Spellblade class.

| Stat | Value |
| --- | --- |
| Health | 5,200 |
| Defense | 1,650 (about 94% damage reduction) |
| Strength | 640 |
| Crit Chance / Crit Damage | 72% / 380% |
| Intelligence (mana) | 1,400 |
| Speed | 215 |

- **Voidforged Aegis** is a full armor set: Helm, Plate, Greaves and Treads. Its set bonus, *Last Stand*, triggers once per phase. When a hit would kill you, it leaves you at 1 HP with 2 seconds of invulnerability instead.
- **Riftcleaver** (sword, 3/3 inscriptions). *Riftstep* teleports you 260px toward the cursor and implodes for 600,000 damage around you. It also gives you a shield worth 25% of your HP. It costs 180 mana and can be spammed.
- **Tri-Seraph Longbow** (bow, max tier) fires three arrows per shot, five shots a second. *Seraph Beam* is a piercing ray that deals 900,000 to everything in its line.
- **Gale Scepter** (staff) fires orbs that bounce off walls and jump between enemies. *Mending Gale* heals 30% of your HP and clears nearby enemy projectiles.
- **Breaker's Pick** (pickaxe, 20 charges) is the only tool that can break Heart-Locks. Its hits crack enemy armor, so they take 30% more damage. *Seismic Slam* hits everything in a ring and stuns minions.
- **Emberwing** (pet) revives you at full HP once per raid.

## The raid

1. **Vessk, the Chain Warden.** A ward makes him immune. Hit the four rune pillars until they go out, and the ward shatters. He is then stunned and exposed for about 11 seconds. Pillars relight if you're too slow. He attacks with chain lashes, charges, chain rings and Bound Thralls.
2. **Ysolde, the Storm Choir.** She resists 80% of your damage until you ground her. Lure her inside a grounding rod's circle, then hit the rod or press E next to it. Watch for triple lightning strikes, spiral orbs and gusts. The *Storm Choir* hits the whole arena: stand in a SAFE circle to avoid it.
3. **The Lockworks.** Grav, the Iron Steward, can't be harmed. He chases you, throws gears and sweeps lasers across the room, and he speeds up after 2 minutes. To shut him down, break 8 seals:
   - five consoles, each a different puzzle: click runes in order, select tiles of one color, lights-out, repeat a memory pattern, turn dials upright
   - two levers
   - a target array, where you shoot the lit target six times

   Once all 8 are broken, crack his Heart-Lock with the Breaker's Pick.
4. **Orrin, the Hollow Flame.** A fast fighter who uses flame cones, leaps that slam down with a ring of fire, fireball volleys and magma pools. When you bring him to zero, he comes back once with less HP. After that he is faster and the arena edges burn.
5. **The Hollow King.** He sits on his throne, immune, and rains crown shards on the arena. Meanwhile he raises three Echoes of earlier bosses, one at a time. Once all three are defeated he comes down to fight you. His attacks are void spirals, rotating cross-beams, a grasp that pulls you toward him, and thralls. Below 30% HP he enrages.

If you die, you can retry the current phase. Your total time and death count carry over. The end screen shows a raid report with split times for each phase and a grade from C to S+. It also has a reward chest, and a better grade makes the rarer drops more likely.
