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


Gameplay

Kill streaks — 3/5/7/10/15 kills trigger announcements + damage/speed boosts (streak resets if you take damage)
Score system — points for kills, headshots give 2×, streaks multiply further; shown top-left
⚡ Blitz mode — new 3rd game mode, 60-second kill race with endless enemy respawns

Enemy AI

3-state alert system — enemies now patrol → alert → combat instead of always rushing. Grey dots on minimap = patrolling, orange = alerted, red = combat
Patrol routes — idle enemies walk between waypoints; map feels alive between engagements
Alert propagation — shooting an enemy alerts nearby enemies within radius
Sniper peek mechanic — sniper enemies duck in/out of cover (peek 1.2s, hide 2.5s)
Armored enemy type — spawns in wave 4+, tanky with armor plates visual

Visual Polish

Enemy health bars — floating billboard bars above every enemy head, color-coded green → yellow → red
Low HP vignette — pulsing red border when below 30 HP
Pooled particles & sparks — no more GC spikes; everything reuses object pools
Improved death tumble — enemies fall sideways, not just forward
ADS breathing sway — subtle organic drift while aiming

Performance

Spark effects now fully pooled (was creating/destroying meshes every frame)
Blood/blast particles fully pooled
LOS checks throttled by alert state (less frequent when patrolling)




BUG FIXES----
GAME CRASHED AND FROZE RANDOMLY -- FIXED
