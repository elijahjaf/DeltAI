# Last Wish

A Deltarune-style turn-based battle that runs in the browser. Three heroes fight one of four bosses: Marionette NEO, a half-puppet, half-robot horror; Candlemaw, a haunted candle; Deadeye, a ghost gunslinger; or Encore, a masked phantom that remixes them all. On the enemy's turn you steer a heart through bullet patterns inside the battle box.

All art is 16-bit style pixel art. Each sprite is drawn in code at low resolution, given a dark outline, and scaled up 2x. There are no image files.

**Play:** open `index.html` in any modern browser. The page has two tabs: **Play** (the game and its controls) and **How to Play** (a full guide, including a tip for every attack; fights themselves show no tips). Opening the guide pauses the game and its music. You can link straight to the guide with `#how-to-play`. It has no build step and no dependencies. It uses Google Fonts when online and falls back to a monospace font offline.

## Music

Every screen has its own original chiptune track, synthesized live with the Web Audio API (there are no audio files). The tracks are written in the style of Toby Fox's boss themes: pulse-wave leads, driving bass and busy arpeggios. Press **M** to mute music and sound effects.

| Track | Plays during | Style |
| --- | --- | --- |
| Last Wish | title screen | gentle and hopeful, F major |
| Strings Attached | Marionette NEO | funky, jazzy and glitchy, D minor; speeds up when it turns frantic |
| Wax and Wane | Candlemaw | a grand, mournful march, C minor; speeds up when its flames turn blue |
| High Noon | Deadeye, YELLOW SOUL half | a galloping western with a harmonica-like lead, E minor |
| The Last Encore | Encore | a restless medley in B minor; speeds up when it turns ECSTATIC |
| Sundown Drive | Deadeye, BLUE SOUL half | relentless spinning 16ths, E minor |

Numbers in the game use a custom 5×7 pixel digit set so that every digit is easy to tell apart: 2 has a flat base and a diagonal, 8 has two loops, and 0 is slashed.

## Controls

| Key | Action |
| --- | --- |
| Arrow keys / WASD | Move the menu cursor or the heart |
| Z / Enter / Space | Confirm, or strike during FIGHT |
| X / Shift | Go back. Hold while dodging to move slowly |
| M | Music and sound on or off |

On the title screen, use the arrow keys to pick **Normal** or **Hard**.

A **MOVE WITH** switch above the game chooses **Arrow keys** or an on-screen **Joystick**. The joystick is digital: drag it with the mouse or a finger to hold up/down/left/right, including diagonals. In joystick mode the arrow and WASD keys stop moving, but Z, X and M still work, and the choice is remembered. On touch devices in arrow-keys mode, an on-screen d-pad with Z and X buttons appears.

## The party

| Hero | HP | Fight power | Spells (EXP cost) |
| --- | --- | --- | --- |
| ASTRA, star knight | 150 | 64 | None. Astra has **ACT** instead of MAGIC |
| TERRIO, cave dweller | 200 | 80 | Crystal Spike (25%, damage), Quake (55%, big damage) |
| LUNE, moon seer | 110 | 36 | Moonbeam (15%, small heal on one hero), Mend (25%, heals one hero and can revive), Aurora (65%, heals everyone) |

- **Astra**: a knight with galaxy-colored skin and silver hair. Stars orbit her and a blue halo floats above her head.
- **Terrio**: a hulking, dark blue cave monster with glowing crystals along his spine, dragging a stone club.
- **Lune**: a hooded seer with pale, cratered moon skin and a crescent-moon staff.

## Actions

- **FIGHT**: a timing bar slides toward a mark. Press Z as it crosses. The closer you are, the more damage you deal, and a dead-center hit is a 1.5x critical.
- **MAGIC** (Terrio and Lune): spends shared EXP, which works like Deltarune's TP. Terrio only has damage spells and Lune only has healing spells.
- **ACT** (Astra): the peaceful way to progress. Against Marionette NEO, the flavor text hints each turn at what it wants. Pick the matching ACT to raise its **MERCY** by 18% (15% on Hard). A wrong ACT does nothing.
  - *Applaud*: it's playing to the crowd or waiting for applause.
  - *Dance*: it holds out a hand or looks for a partner.
  - *Oil Joints*: its joints creak or screech.
  - *Untangle*: its strings are knotted or tangled.
  - *Check*: shows its stats.
  - *Reveal*: next turn, the right ACT is revealed in the flavor text and marked with a star in the ACT menu.
- **SPARE** (everyone): once MERCY reaches 100% (200% for Encore), the enemy's name turns yellow and sparing it ends the battle peacefully. Sparing earlier does nothing.
- **ITEM**: a shared, limited bag (4 Glow Berries, 2 Honey Loaves, 1 Phoenix Tea). Any hero can use one on any teammate, including a downed one.
- **DEFEND**: halves the damage that hero takes this turn and grants 16% EXP.

**EXP** also comes from grazing. When the heart passes close to a bullet without touching it, you get a burst of EXP, plus a little more for each frame you stay close.

**Blue attacks** (Scissor Dance's blades) pass through the heart harmlessly while it stands still. They only hurt while you are moving.

A hero at 0 HP is **downed**. They skip turns and regain 1/8 of their max HP each round until they are back up. Healing revives them sooner. If all three heroes are downed, it's game over.

## The bosses

Pick the enemy on the title screen: Up/Down picks a row, Left/Right picks an option.

Attacks run in a fixed order, one per turn, and the flavor text before each one hints at the enemy's mood. Below half HP most bosses turn frantic: attacks get denser and faster and deal 25% more damage. (Deadeye switches SOULs instead, and Encore turns ECSTATIC.)

Some attacks bend the rules:
- **Blue** bullets only hurt while you move. **Orange** bullets only hurt while you stand still.
- **Darkness**: only a pool of light around the heart shows what's coming. Glowing bullets show through the dark.
- **Reversed controls**, **strings that drag the heart**, **wind that pushes it**, **wax puddles that slow it**, and **boxes that shrink** during the attack.

### Marionette NEO (3200 HP)

A scrap-metal marionette with a cracked porcelain grin, black-tear eyes, a red LED eye, torn wings, a cannon arm and a steel claw. It glitches and twitches as it fights. Its ACTs are Applaud, Dance, Oil Joints and Untangle.

Its 21 attacks: Needle Rain, Puppet Strings, Card Fan (slow cards), Loose Buttons, Cannon Beam, Curtain Fall, Puppeteer's Pull, Paper Bloom, Spare Heads, Lights Out, Blue & Orange, Stage Lights, Tangled Thread, Mirror Mirror, Chandelier, Time Bombs, String Cage, Closing Curtains, Buzzsaws, Scissor Dance and Grand Finale.

### Candlemaw (3400 HP)

A towering chapel candle with a fanged, ember-lit maw, held in a wrought-iron candelabra. Below half HP its flames burn blue. It has one ACT besides Check: **Keep Vigil**, which always works and raises its MERCY 8% per use (6% on Hard). There's no mood to read, so Reveal isn't offered against it.

Candlemaw's fire comes in two colors, so nearly every attack is a test of **blue (stand still)** and **orange (keep moving)**, with plain white wax as the only ordinary danger. Its 17 attacks:

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
| Twin Flames | fireballs fly at you in crossing pairs, one blue and one orange |
| Flame Spiral | four spiral arms of alternating blue and orange fire spin out from the center |
| Wax Icicles | blue and orange icicles hang overhead and drop when you walk under them |
| Geyser Wave | a wave of blue and orange geysers erupts column by column across the floor |
| Procession | rows of blue and orange lanterns drift past in alternating directions |
| Last Vigil | orange ember rain plus blue rings |

### Deadeye (3000 HP)

A towering skeletal ghost gunslinger, the largest boss on the stage. It wears a bullet-riddled hat and a tattered poncho torn open over its ribs, and a long tail of smoke full of drifting lost souls trails where its legs should be. Fire burns in its eye sockets and it is fully animated: its jaw chatters and cackles, its skull twitches, one revolver stays aimed at the party and kicks back with a muzzle flash as it fires, the other twirls overhead, and vultures circle above. Its eyes and aura burn red, then blue in the second half. Deadeye changes how your heart works, the way Undertale's colored SOULs do.

**First half: YELLOW SOUL.** The heart flips upside down and turns yellow. It moves freely, and **Z fires a shot straight up** (up to five on screen). Holding Z fires continuously at the fastest rate, the same as mashing it. Yellow objects break when shot. **Yellow TNT explodes** in a + shape across the entire box: it freezes in place where it was hit while a short warning flashes along its row and column, then the blast hurts you if you're still in line. The blast doesn't affect anything else: rocks, bullets and other TNT are untouched.

| Attack | What happens |
| --- | --- |
| Target Practice | rows of yellow bottles drift down; stray white bullets cross the box |
| TNT Wall | walls of rocks descend with one gap, plugged by TNT; shoot it, dodge its blast, then slip through |
| Six Shooter | aimed volleys of yellow slugs to shoot down or dodge |
| Dynamite Toss | TNT lobbed in arcs lights itself on landing; shoot it mid-air to set it off elsewhere |
| Tumbleweeds | bouncing yellow tumbleweeds |
| Ricochet | yellow slugs bounce off the walls and speed up with each bounce |
| Outlaw Gang | a Space Invaders-style gang of yellow outlaws (some are TNT) that fires back |
| High Noon | bottles, TNT and slugs together |

**Second half: BLUE SOUL.** When Deadeye drops to half HP *or* its MERCY reaches 50%, your heart turns blue and the moveset switches for the rest of the fight. Gravity pulls the heart to the floor, left/right move it, and **Z (or Up) jumps**. Tap for a short hop and hold for a full jump (about 24 px vs. 61 px). You can land on platforms.

| Attack | What happens |
| --- | --- |
| Cactus Run | short and tall cacti slide along the floor |
| Dust Devil | rolling tumbleweeds to hop over and bouncing ones to walk under |
| Last Train | train cars roll along the floor; jump over them or ride on top |
| Mine Carts | the floor fills with spikes; ride the moving carts |
| Snake Pit | snakes lunge up from marked holes while hawks swoop in at an angle |
| Low Ceiling | spikes hang from the ceiling over each cactus, so only a short hop fits |
| Gravity Slam | you're slammed to the floor, then floor spikes rise |
| Sundown | everything together |

It has one ACT besides Check: **Accept Duel**. Each use raises MERCY 7% (5% on Hard), but also makes every one of Deadeye's attacks deal 5% more damage, stacking for the rest of the fight. Reaching 50% MERCY this way also flips your heart to BLUE.

### Encore (3600 HP)

A phantom conductor in a star-lined cloak and a split comedy/tragedy mask, with the masks of the other three bosses orbiting it. Its eyes glow the color of your current SOUL. It is the hardest boss: every one of its 17 attacks runs at full strength from the first turn, about 10% faster and with 20% more damage than the attack's base level, even outside Hard Mode. Every attack remixes another boss's tricks in a new way, and Encore **switches your SOUL between red, yellow and blue**, sometimes in the middle of an attack.

| Attack | SOUL | What happens |
| --- | --- | --- |
| Masquerade | red | a breathing ring of masks orbits the center and flicks cards at you |
| Shooting Gallery | yellow | conveyor rows of targets and TNT glide past; some shoot back |
| Rising Tide | blue | wax rises under you while orange embers fall and cacti slide in |
| Conductor's Baton | red | a spinning baton that blinks, then flips between blue and orange |
| Candle Duel | yellow | shoot falling candles, and each one drips blue wax |
| Gravity Flip | blue | gravity flips up and down; Z always jumps away from the side you're on |
| Spotlight Solo | red | stay inside a wandering spotlight, because the darkness around it hurts |
| Bell Toll | yellow | shoot bells swinging on long ropes |
| Soul Swap | all | your SOUL cycles red → yellow → blue every few seconds |
| Prism | red | blue and orange beams plus falling shards |
| Curtain Crossfire | red | blue curtains fall while fans of white cards fly in |
| Mirror Match | red | your controls are reversed while blue and orange walls sweep past |
| High Wire | blue | the floor is spikes: ride moving platforms and hop over strings that snap taut |
| Burning Wheel | yellow | a spinning wheel of yellow candles; shoot candles off it to open a path |
| String Quartet | yellow | a string drags your heart around while yellow notes fall |
| Blackout Swap | red/blue | the lights go out and your SOUL swaps between red and blue; only glowing hazards show |
| Final Encore | all | everything at once, with fast SOUL swaps |

Encore's MERCY bar runs to **200%**, and it can only be spared once the bar is full (a tick marks the halfway point). Its ACTs are a gamble. **Applaud** gives a safe +6% MERCY (5% on Hard). **Cry Encore!** gives +14% (11%), but its next attack comes at full fury. Encore never turns frantic. Instead, at **30% HP or 70% MERCY** it becomes **ECSTATIC**: confetti rains down, its HP bar turns pink, and every enemy turn it performs **two different attacks back to back** before the box closes. Its theme is **The Last Encore**, a restless B-minor medley that speeds up when it turns ECSTATIC.

## Hard Mode

- Marionette NEO has 4400 HP, Candlemaw 4600, Deadeye 4200 and Encore 4800.
- Every attack runs at its frantic level from turn one and deals about 15% more damage.
- Bullets are 10% faster, rising to 20% once the enemy is below half HP.
- MERCY rises more slowly: 15% per correct ACT against Marionette NEO (instead of 18%) and 6% per Keep Vigil against Candlemaw (instead of 8%).
- The item bag holds 3 Glow Berries, 1 Honey Loaf and 1 Phoenix Tea.
- The heart's invincibility after a hit is shorter.

## Extreme Mode

Pick **EXTREME** in the MODE row of the title screen (NORMAL / HARD / EXTREME / ENDLESS). It works against every boss and keeps all of Hard Mode's rules (more boss HP, full fury from turn one, faster bullets, the smaller item bag, shorter invincibility and slower MERCY), then adds three more:

- **All damage taken is doubled** (still halved by DEFEND).
- **Lune's healing is halved:** Moonbeam heals 22 HP, Mend 42 HP and Aurora 35 HP to each hero. The spell descriptions show the reduced numbers.
- **Downed heroes drop to -150 HP and stay down.** Only **ASTRA** can come back: healing her works as normal and she recovers 1/8 of her max HP each round. TERRIO and LUNE no longer recover between turns, and Mend, items and Phoenix Tea can't target them (the target menu says "can't be revived"). Once all three are down, it's game over.

Winning shows "YOU WON ON EXTREME!".

## Endless Mode

Pick **ENDLESS** in the MODE row of the title screen (the enemy choice is ignored). There are no menus: attacks from all four bosses, 71 in total, come one after another in a completely random order (never the same attack twice in a row), and a timer shows how long the party has survived. The boss that owns the current attack appears on stage.

- **DANGER** starts at 1 and rises every 30 seconds. Each level makes bullets 8% faster (capped at +80%) and hit 10% harder, and from DANGER 3 (one minute in) every attack uses its frantic pattern. At DANGER 4 the music speeds up.
- The panel under the boss shows the timer, the wave count, the DANGER level with a bar filling toward the next level, and your best time.
- Between waves each hero recovers 8% of their max HP, so downed heroes slowly get back up.
- The run ends when all three heroes are down. The game-over screen shows your time and waves, and your best time is saved in the browser (localStorage).
