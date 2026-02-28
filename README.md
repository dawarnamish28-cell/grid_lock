# GRID_LOCK
Fast-paced grid-based shooter built in pure HTML.

▶ Play now: https://grid-lock-black.vercel.app

Basic Controls:
. WASD - Move 
· Mouse - Aim 
· LMB - Fire 
· RMB - ADS
. R - Reload 
· Q - Cycle 
· G - Grenade 
· F - Pickup 
· Space - Jump 
. Tab - Stats

Features:
- Zero frameworks
- Single-file HTML
- Tactical grid combat

GRIDLOCK v4 is now live !! :)

IMPROVEMENTS----


Shared Flow Field Navigation — Instead of every enemy running its own BFS pathfinding every second, a single flow field is computed every 0.7s and all enemies read from it. Far fewer pathfinding calls as enemy count scales up.
Explosive Barrels — Red-striped barrels (30% of barrel tiles) now detonate when shot or caught in a blast, chain-react to nearby barrels, and deal massive AOE damage to both enemies and the player.
Suppression System — Enemy near-misses now suppress the player: your mouse sensitivity is cut roughly in half and a ⚠ SUPPRESSED indicator appears. Incentivizes actually taking cover rather than standing still trading shots.
Enemy Grenade Throwing — Armored enemies and some grunt variants now throw grenades at the player. An ⚠ ENEMY GRENADE! kill-feed warning appears. Enemy grenades only hurt the player (not each other).
Gunshot Sound Alerting — Firing your weapon now broadcasts an alert to enemies within 16 units, even without line-of-sight. Silenced play is now meaningfully different.
Extraction Mode — New 4th game mode. Reach a glowing zone in the center of the map and hold it for 30 seconds while enemies continuously swarm. Progress decays when you leave the zone.
Wave Modifiers — Starting wave 3, each wave randomly rolls a modifier: ARMORED, RUSH, SNIPER, NIGHT OPS (reduced fog/dark sky), or DOUBLE TIME. The modifier is shown on the HUD and affects which enemy types spawn.
Investigation AI — When enemies hear gunshots but don't have LOS, they now move to your last known position to investigate. A ◎ ENEMIES INVESTIGATING indicator shows on the HUD. The shared last-known-pos also shows as a yellow dot on the minimap.
Better Weapon Audio — Shotgun and sniper now use a white-noise burst buffer (real noise synthesis) instead of square waves, giving them a much more percussive, distinct sound. SMG and pistol use two detuned oscillators for a richer crack.
Chromatic Aberration on Damage — Taking damage now triggers a brief chromatic aberration effect via SVG filter on the canvas, plus the existing screen flash. Makes hits feel significantly more impactful.
