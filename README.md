# GRIDLOCK v6

Play now at https://grid-lock-black.vercel.app
---

## Game Modes

| Mode | Objective |
|------|-----------|
| **Survival** | Survive endless enemy waves. Each wave grows larger and harder. |
| **Hunt** | Eliminate a high-value target (HVT boss) protected by regular enemies. |
| **Blitz** | Kill as many enemies as possible in 60 seconds. Score attack. |
| **Extraction** | Reach and hold the extraction zone under enemy pressure. |
| **Escort** | Keep a randomly-named VIP alive as they wander near you. Survive scripted ambush waves at key phases. |

---

## Controls

| Key | Action |
|-----|--------|
| `W A S D` | Move |
| `Shift` | Sprint |
| `Ctrl` | Crouch (reduces spread and recoil) |
| `Space` | Jump |
| `LMB` | Fire |
| `RMB` (hold) | Aim down sights (ADS) |
| `Q` | Cycle weapon |
| `R` | Reload |
| `G` | Throw grenade |
| `V` | Melee attack |
| `F` | Pick up weapon / ammo / health kit |
| `I` | Inspect weapon |
| `Esc` | Pause |

---

## Weapons

| Weapon | Damage | Mag | Fire Rate | Mode | Notes |
|--------|--------|-----|-----------|------|-------|
| **M9 Pistol** | 30 | 12 | Semi | Semi-auto | Starting weapon, reliable at all ranges |
| **M870 Shotgun** | 14 × 6 pellets | 6 | Slow | Semi-auto | Devastating up close |
| **MP5 SMG** | 11 | 30 | Fast | Full-auto | High DPS, manageable spread |
| **M24 Sniper** | 95 | 5 | Very slow | Semi-auto | One-shot most enemies; scoped ADS |

Weapons spawn as pickups on the map. Ammo crates and dropped ammo refill reserves. Crouching reduces spread by 50%.

---

## Enemies

| Type | Indicator | Behaviour |
|------|-----------|-----------|
| **Grunt** | Blue | Standard AI — seeks cover, peeks to fire |
| **Rusher** | Orange | Fast, low health, flanks aggressively |
| **Armored** | Dark/grey | High health, throws grenades, moves slower |
| **Sniper** | Green | Long range, seeks elevated cover, high damage |
| **Boss (HVT)** | Red aura | Hunt mode only — large health pool, high damage, red bullet tracer |

Enemies use shared flow-field pathfinding, line-of-sight checks, cover-seeking, suppression fire, and grenade throws.

### Wave Modifiers

Each wave after wave 2 may roll a modifier:

- **Armored Wave** — majority of spawns are armored enemies
- **Rush Wave** — majority of spawns are rushers
- **Sniper Wave** — majority of spawns are snipers
- **Elite Wave** — all stats boosted
- **Night Wave** — reduced visibility (fog thickens)

---

## Kill Streaks

Kill multiple enemies without dying to trigger streak bonuses. Streak resets on death.

| Streak | Name | Bonus |
|--------|------|-------|
| 3 | Triple Kill | +Damage |
| 5 | Killing Spree | +Speed |
| 7 | Rampage | +Damage & Speed |
| 10 | Unstoppable | +Damage & Speed |
| 15 | Legendary | +Damage & Speed |

Headshots and melee kills count toward streaks. Score multiplier scales with current streak count.

---

## Scoring

- Standard kill: 100 pts
- Headshot: 2× multiplier
- Melee kill: bonus points
- Active streak: score scales by `1 + streak × 0.1`
- Scores are saved to a local leaderboard (top 10, stored in `localStorage`)

---

## Escort Mode — Details

The VIP is a randomly named agent (Agent Zero, Dr. Atlas, Colonel Rex, etc.) who wanders near you while you keep enemies off them.

- VIP moves to random points within ~6 units of your position
- Stops moving when taking fire — crouches and suppresses
- Passively regenerates HP when not under fire
- Enemies actively check line-of-sight to the VIP and shoot if close enough
- **4 scripted ambush waves** trigger at phases 2, 4, 6, and 8 — larger enemy bursts with increasing speed
- A directional arrow appears on-screen pointing toward the VIP when they're off-screen
- VIP speaks contextual lines (start, moving, under fire, low HP, etc.)
- Mission fails if VIP HP reaches 0

---

## Map Features

- **Explosive barrels** — shoot to detonate; damages nearby enemies and players
- **Health kits** — 4 fixed spawn locations, restore 50 HP, press `F` to collect
- **Weapon pickups** — SMG, Shotgun, Sniper spawn at fixed spots
- **Ammo drops** — enemies occasionally drop ammo on death
- **Minimap** — top-right corner; shows player, enemies (by alert state), VIP (Escort mode), and health kit locations
- **Compass** — enemy dots appear on the compass bar when in your forward arc

---

## Tech

- **Three.js r128** — rendering, scene, geometry
- **Single HTML file** — all JS, CSS, and assets inline; no dependencies to install
- **Web Audio API** — procedural sound (oscillators + noise) for all weapons and effects
- **localStorage** — leaderboard persistence only; no other data is stored or transmitted

---
Thanks 


Made with <3 by Namish
