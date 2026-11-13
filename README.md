# THE TOWER — Idle Defense

A neon sci-fi idle/incremental tower-defense browser game. Defend a central tower, buy upgrades with in-run Cash, collect Coins on defeat, and improve the permanent Workshop for your next run.

**Current release:** V1.1  
**Platforms:** Desktop browser (including Ubuntu/Firefox) and mobile browsers  
**Stack:** HTML5 Canvas, vanilla JavaScript, CSS  
**Owner:** Geo / Smilley222

## Play
Open [index.html](index.html) in a modern browser. The game is client-side, with no build step or dependency installation.

For public hosting, enable **GitHub Pages** in **Settings → Pages → Build and deployment → Deploy from a branch**. Choose the `Game` branch and `/(root)` folder, then save. Once GitHub reports deployment, the intended public link is:
https://smilley222.github.io/the-tower-idle-defense/

**Note:** GitHub Pages deployment is a separate setting. Uploading this repository does not by itself confirm that Pages is live.

## How to play
- The central tower fires at enemies automatically.
- Enemies approach from the edges in waves.
- Defeating enemies gives **Cash** for temporary Attack, Defense, and Utility upgrades.
- When the tower falls, earn **Coins** based on your wave and kills.
- Spend Coins on permanent Workshop upgrades. These apply **starting with the next run**.
- Toggle Auto Wave or manually start the next wave after the current one ends.

## Keyboard shortcuts
| Key | Action |
| --- | --- |
| Space | Pause / resume |
| G | Cycle 1× → 2× → 4× |
| A | Toggle Auto Wave |
| N | Start next wave when ready |
| W | Switch Run / Workshop |
| 1, 2, 3 | Attack / Defense / Utility upgrades |
| R | Restart after game over |

Touch controls are available in the interface.

## Saves
- Permanent Workshop progress is stored locally in your browser (key `THE_TOWER_IDLE_SAVE_V1`).
- Use the game's **Export Save** and **Import Save** features when changing browsers, devices, or site origins.
- Browser storage is not synced across devices automatically. Clearing browser data can delete the save.

## Repository contents
- `index.html`: Current playable V1.1 browser game
- `archive/the_tower_defense_v1.html`: Preserved initial implementation
- `docs/GAME_DESIGN.md`: Game design overview
- `docs/ROADMAP.md`: Planned development
- `CHANGELOG.md`: Release history

## Status
V1.1 includes wave controls, fixed game-speed scaling, pause, responsive layout, keyboard shortcuts, a Workshop flow and save transfer. Boss encounters, prestige, offline progress, and controller support are planned, **not implemented**.

## Rights
Copyright © Geo / Smilley222. All rights reserved. No open-source license has been granted.
