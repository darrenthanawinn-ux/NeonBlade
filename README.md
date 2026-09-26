# Neon Blade: Survivor

A single-file, browser-based rogue-lite arena survivor. No installs, no build tools —
just open `index.html` in any modern browser (Chrome, Edge, Firefox, Safari) and play.

## How to Run

1. Extract the zip.
2. Double-click `index.html` (or drag it into your browser).
3. Click **Enter The Grid** and survive.

No internet connection is required except for the one-time load of the Tailwind CSS
CDN script used for menu styling — the game itself runs entirely offline once loaded.

## Controls

| Action | Key |
|---|---|
| Move | `W` `A` `S` `D` or Arrow Keys |
| Dash-Slash | `Space` (short cooldown; damages enemies you pass through and grants brief invulnerability) |
| Pause / Resume | `Esc` |
| Choose upgrade | Mouse click on a card |

Your blade **auto-attacks the nearest enemy** the moment it's in range — there's no
manual aiming for your primary weapon. Your job is positioning, dashing through danger,
and picking the right upgrades.

## Core Loop

- Enemies spawn in increasing numbers around you and close in.
- Killing them drops **EXP shards** — walk near one (or build up your Magnetic Field
  upgrade) to auto-collect it.
- Fill the EXP bar to level up and choose **1 of 3 random upgrades**.
- A **boss construct** ("Sentinel") spawns every **2 minutes**, gets tougher each time,
  and hits much harder than regular enemies — watch for its charge attack and radial
  projectile bursts.
- Survive as long as possible. Your score is based on time survived, kills, and level.

## Enemy Types

| Type | Behavior |
|---|---|
| **Grunt** (magenta) | Basic melee chaser, moderate HP |
| **Runner** (cyan) | Fast, low HP, swarms in numbers — unlocks ~15s |
| **Shooter** (violet) | Keeps distance and fires projectiles — unlocks ~35s |
| **Tank** (amber) | Slow, heavy HP and contact damage — unlocks ~60s |
| **Sentinel (Boss)** | Spiked red construct: charges at you, fires radial bullet bursts, big HP pool — spawns every 2 minutes and scales up each time |

## Upgrade List

**Blade**
- **Overclocked Blade** — +35% blade damage per stack
- **Rapid Cycler** — -14% attack cooldown per stack
- **Extended Arc** — +18% blade range and wider swing arc
- **Precision Chip** — +7% crit chance, +20% crit damage

**Deployables**
- **Laser Drone** — adds an orbiting drone that fires homing bolts at the nearest enemy
- **Orbital Shield** — adds a rotating energy blade that damages anything it touches

**Mobility**
- **Dash Amplifier** — +40% dash damage, -12% dash cooldown
- **Servo Legs** — +10% move speed

**Defense**
- **Reinforced Hull** — +22 max HP and a full heal on pickup
- **Nanite Regen** — +1.1 HP/s passive regeneration
- **Plated Armor** — -8% damage taken per stack

**Utility**
- **Magnetic Field** — +45 pickup radius for EXP shards
- **Data Siphon** — +20% EXP gained per stack

Most upgrades can be picked multiple times (up to a per-upgrade cap) and stack
multiplicatively or additively as noted, so a run late-game can have several drones
and shields running at once.

## Survival Tips

- **Never stop moving.** Standing still is how you get surrounded — kite in circles
  and let your auto-attack, shields, and drones do the killing.
- **Save your dash for emergencies** (or for punching through a wall of enemies when
  you're boxed in) — it also grants brief invulnerability, so it can bail you out of
  a bad boss charge.
- **Prioritize Orbital Shield and Laser Drone early** — they give you damage that
  doesn't depend on the blade's short range, which matters once swarms get dense.
- **Watch the boss timer.** A Sentinel spawns every 2 minutes and gets tougher each
  time — make sure your build has enough sustained damage and survivability (HP/armor/
  regen) before the next one shows up.
- **Don't ignore defense upgrades.** Late-game swarms deal chip damage constantly;
  Reinforced Hull, Nanite Regen, and Plated Armor keep you alive long enough for your
  offense to matter.
- **Runners can be ignored briefly** if you're mid-fight with a Tank or Shooter —
  they're low HP and your AoE (shield/drones) will usually clean them up.

## Technical Notes

- Single `index.html` file — all HTML, CSS, and JavaScript are embedded.
- Rendering: raw HTML5 Canvas 2D, camera-following-player in a bounded 4200×4200 arena.
- Audio: tiny procedurally-synthesized sound effects via the Web Audio API — no audio
  files.
- High scores (top 5 runs by score) are saved to your browser's `localStorage`, so they
  persist between sessions on the same browser/device.
- No frameworks, no build step, no external assets besides the Tailwind CDN stylesheet
  used purely for a handful of utility classes.

Have fun, and don't flatline.
