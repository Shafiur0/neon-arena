# NEON ARENA

A complete 3D arena survival shooter that runs in a single HTML file.

**Play it:** https://neon-arena-dun.vercel.app

You pilot a gunship in a circular neon arena. Enemies spawn at the edge and swarm you.
Your cannons auto-target the nearest hostile, so the game is entirely about positioning,
dodging, and knowing when to dash.

## Run it

Open `index.html` in any modern browser. No build step, no install.

Needs an internet connection the first time — three.js loads from a CDN.

## Controls

| Key | Action |
| --- | --- |
| `W` `A` `S` `D` / arrows | Move |
| `Space` | Dash (brief invulnerability, 2.4s cooldown) |
| `P` | Pause |
| `M` | Mute |

On touch devices, drag anywhere to steer.

## How it plays

- **Auto-fire.** Bullets always fly at the closest enemy within range. You never aim — you place yourself.
- **Waves.** Each wave spawns more enemies. Clear them all to pick one of three upgrades.
- **Upgrades stack.** Fire rate, damage, pierce, extra barrels, hull, speed, dash cooldown.
- **Combo.** Kills within 3.4s of each other build a multiplier up to ×6. Getting hit doesn't break it, but letting the timer lapse does.
- **Health orbs** drop from about 1 in 7 kills. They magnet toward you when you get close.
- **Enemies:** pink drifters (fast, fragile), amber brutes (slow, tanky, hit hard), violet spitters (keep their distance and shoot).

Score and best run are saved to `localStorage`.

## Under the hood

- Three.js r160, ES modules via import map.
- Custom GLSL for the floor: pixel-width-constant grid lines computed from camera distance, so lines stay crisp at every angle instead of aliasing into dashes.
- `UnrealBloomPass` for the neon glow; ACES tone mapping.
- All audio is synthesized with the Web Audio API — no asset files.
- Everything else (geometry, particles, shockwaves, pools) is procedural, so the whole game is one ~1,000-line file.
