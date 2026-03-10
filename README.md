# GRIDLOCK v6.3

Play now at- https://grid-lock-black.vercel.app

---

## What's New in v6.3

### Gameplay
- **Upgrade system** — after each Survival wave a menu offers 3 random upgrades: Hollow Points, Adrenaline, Extended Mags, Speed Loader, Stim Pack, Reinforced Vest, Grenade Cache, Precision Barrel, Combat Training
- **Melee combo** — press `V` twice quickly for a combo hit (×1.65 damage, wider range)
- **Situational grenades** — enemies only throw grenades when you've been stationary (camping), not at random
- **Sniper retreat** — enemy snipers find new cover when their position is blown

### AI
- **Separation steering** — enemies push apart from each other while moving; no more funnelling into a single file
- **Enemy death fade** — enemies collapse forward and fade out instead of instantly disappearing

### Visuals
- **Procedural ground texture** — cracked concrete with multi-octave noise, tile grid, random cracks, and dirt stains baked into a canvas texture at startup
- **3D grass** — instanced blade clusters (6 draw calls for all grass on the map) layered over flat 2D ground patches; ankle-height, crossed-plane blades with per-blade colour variation
- **Minimap moved** — relocated to bottom-right to stop overlapping the grenade counter

### Performance
- **Spatial grid** — broad-phase neighbour lookup replaces O(n²) entity scan
- **Instanced grass** — ~30,000 individual mesh draw calls reduced to 6 via `THREE.InstancedMesh`
- **Minimap dirty-flag** — wall layer pre-rendered to an offscreen canvas; only dynamic elements redrawn each frame
- **Audio suspend** — Web Audio context suspends on alt-tab and resumes on focus

---

## Play

Download `gridlock_v6.3.html` and open it in any modern browser. Pointer lock is required — click the canvas to capture your mouse.

---

## Game Modes

| Mode | Objective |
|------|-----------|
| **Survival** | Survive endless enemy waves. Each cleared wave offers an upgrade. |
| **Hunt** | Eliminate a high-value target (HVT boss) protected by regular enemies. |
| **Blitz** | Kill as many enemies as possible in 60 seconds. No upgrades. |
| **Extraction** | Reach and hold the extraction zone under enemy pressure. |
| **Escort** | Keep a randomly-named VIP alive through scripted ambush waves. |

---

## Controls

| Key | Action |
|-----|--------|
| `W A S D` | Move |
| `Shift` | Sprint |
| `Ctrl` | Crouch (reduces spread) |
| `Space` | Jump |
| `LMB` | Fire |
| `RMB` (hold) | Aim down sights (ADS) |
| `Q` | Cycle weapon |
| `R` | Reload |
| `G` | Throw grenade |
| `V` | Melee attack (double-tap for combo) |
| `F` | Pick up weapon / ammo / health kit |
| `I` | Inspect weapon |
| `Esc` | Pause |

---

## Upgrades (Survival only)

Offered between waves — choose 1 of 3 random options. Stacks persist until restart.

| Upgrade | Effect |
|---------|--------|
| 🔥 Hollow Points | +20% weapon damage |
| ⚡ Adrenaline | +18% movement speed |
| 📦 Extended Mags | +8 rounds to all magazines |
| 🔁 Speed Loader | −30% reload time |
| 💊 Stim Pack | Restore 50 HP immediately |
| 🛡 Reinforced Vest | +30 max HP |
| 💣 Grenade Cache | +2 grenades |
| 🎯 Precision Barrel | −35% weapon spread |
| 🥊 Combat Training | +35 melee damage, −25% melee cooldown |

---

## Weapons

| Weapon | Damage | Mag | Mode | Notes |
|--------|--------|-----|------|-------|
| **M9 Pistol** | 30 | 12 | Semi | Starting weapon |
| **M870 Shotgun** | 14 × 6 pellets | 6 | Semi | Devastating up close |
| **MP5 SMG** | 11 | 30 | Full-auto | High DPS |
| **M24 Sniper** | 95 | 5 | Semi | One-shot most enemies; scoped ADS |

---

## Enemies

| Type | Behaviour |
|------|-----------|
| **Grunt** | Seeks cover, peeks to fire, may throw grenades |
| **Rusher** | Fast, low health, flanks aggressively |
| **Armored** | High health, throws grenades, moves slower |
| **Sniper** | Long range, elevated cover, retreats when exposed |
| **Boss** | Hunt mode only — large HP pool, red bullet tracer |

Enemies use shared flow-field pathfinding, line-of-sight checks, cover-seeking, suppression fire, separation steering, and situational grenade throws.

### Wave Modifiers

| Modifier | Effect |
|----------|--------|
| Armored Wave | Majority armored enemies |
| Rush Wave | Majority rushers |
| Sniper Wave | Majority snipers |
| Night Ops | Reduced visibility |
| Double Time | All enemies faster |

---

## Kill Streaks

| Streak | Name | Bonus |
|--------|------|-------|
| 3 | Triple Kill | +Damage |
| 5 | Killing Spree | +Speed |
| 7 | Rampage | +Damage & Speed |
| 10 | Unstoppable | +Damage & Speed |
| 15 | Legendary | +Damage & Speed |

---

## Escort Mode

- VIP wanders within ~6 units of your position, stops when under fire
- Enemies actively target the VIP
- 4 scripted ambush waves at kill-count thresholds
- On-screen arrow points to off-screen VIP
- VIP speaks contextual lines throughout the mission

---

## Map

- **Explosive barrels** — shoot to detonate
- **Health kits** — press `F` to collect, restore 50 HP
- **Weapon & ammo pickups** — scattered across the map
- **Minimap** — bottom-right; shows player, enemies, VIP, pickups
- **Compass** — enemy dots in your forward arc

---

## Tech

- **Three.js r128** — rendering, scene, geometry
- **Single HTML file** — all JS, CSS, and audio inline; no dependencies
- **Web Audio API** — procedural oscillator-based sound for all weapons and effects
- **InstancedMesh** — all 3D grass rendered in 6 draw calls
- **localStorage** — leaderboard persistence only

---

## Browser Requirements

Any modern browser with WebGL. Tested in Chrome and Firefox. Pointer lock required.
