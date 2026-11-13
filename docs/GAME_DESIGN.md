# Game Design Document — The Tower: Idle Defense

## Overview
**Genre:** Idle / incremental tower defense  
**Platform:** Web (HTML5 Canvas, JavaScript and CSS)  
**Core loop:** Survive waves → earn Cash → buy temporary upgrades → die → earn Coins → buy permanent Workshop upgrades → replay.

A fixed tower in the center automatically attacks incoming enemies. The player optimizes upgrades, damage output and survivability to reach higher waves.

## Pillars
1. Satisfying auto-combat with projectiles, particles and damage feedback.
2. Strategic choices among Attack / Defense / Utility in-run upgrade categories.
3. Permanent Workshop progression between runs.
4. Idle-friendly auto waves and adjustable 1× / 2× / 4× speed.

## Tower
Stats include Damage, Attack Speed, Range, Multishot, Rapid Fire Chance, Max HP, HP Regen, Defense, Thorns, Cash/Kill, Cash Bonus and Coin Bonus.
Nearest targets in range are prioritized; Multishot adds targets, and Rapid Fire can add an extra shot.

## Enemies
| Type | HP multiplier | Speed multiplier | Radius | Style |
| --- | ---: | ---: | ---: | --- |
| Normal | 1.0 | 1.0 | 10 | Magenta |
| Fast | 0.6 | 1.6 | 8 | Yellow |
| Tank | 2.8 | 0.65 | 14–15 | Purple |

Enemy HP scales as `15 × 1.15^(wave−1) × typeMult`.  
Enemy speed scales as `min((1.1 + wave × 0.02) × typeMult, 3.5)` in the base design.  
Contact damage scales as `8 × 1.1^(wave−1)`.

## Waves and economy
- Wave size: `8 + floor(wave × 3.5)`.
- Enemies spawn around the outer perimeter.
- After the last enemy is defeated, the next wave starts automatically (if enabled) or through Next Wave.
- Cash is run-only and spent on temporary upgrades.
- Coins are awarded on death: `floor((wave × 5 + kills × 0.5) × Coin Bonus)`.

## Upgrades
**Attack:** Damage, Attack Speed, Range, Multishot, Rapid Fire Chance.  
**Defense:** Max Health, Health Regen, Defense %, Thorns.  
**Utility:** Cash/Kill, Cash Bonus, Coin Bonus.

Upgrade cost formula: `floor(baseCost × costMultiplier^level)`, subject to caps.

**Permanent Workshop:** Base Damage, Base Health, Base Health Regen, Base Cash Bonus, Base Coin Bonus, Starting Cash. Workshop upgrades are purchased with Coins and apply to the next run.

## Interface
Responsive battlefield and controls with Wave, Enemies, Cash, Coins and Tower Integrity HUD. Round Upgrade tabs, Workshop, speed control, auto-wave toggle, pause and game-over summary.

## Visual direction
Dark sci-fi / neon cyberpunk: near-black background, cyan tower, magenta/purple/yellow enemies, glowing trails, hit feedback and a subtle grid.

## Technical design
Pure client-side HTML/Canvas/JavaScript, browser localStorage for Workshop progress (`THE_TOWER_IDLE_SAVE_V1`), fixed-step simulation, no external engine.

## Future ideas (not part of V1.1)
Bosses, new abilities, prestige, achievements, audio, offline progress and tower skins. Gamepad/controller support is planned separately.
