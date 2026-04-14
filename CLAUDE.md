# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a collection of browser-based games and scripts, all self-contained in single files. No build system, no dependencies, no package manager.

## Running the Projects

Open any HTML file directly in a browser:
```
open tictactoe.html
open dungeon.html
```

Run the Python script:
```
python main.py
```

## Architecture

All games are single-file HTML — HTML, CSS, and JavaScript in one file with no external dependencies except Google Fonts (loaded via CDN).

### tictactoe.html
- 2-player or vs-AI mode toggled by a button
- AI uses minimax; difficulty selector (Beginner/Easy/Medium/Advanced) controls how often random vs. minimax moves are made
- Game state: `board[]`, `current`, `gameOver`, `vsAI`, `scores`

### dungeon.html
- Turn-based dungeon crawler with a 5×5 grid
- 3 levels: Stone Cellar → Crypt → Dark Keep
- Player is a wizard; click adjacent floor tile to move, click adjacent enemy tile to attack
- State: `player` object, `grid[][]` (2D array of `{type, enemy}`), `enemies[]` array, `currentLevel`
- `generateMap(levelIdx)` builds the grid with walls, enemies, and stairs using BFS connectivity check
- `render()` redraws the entire grid each turn
- Level progression triggers on stepping onto the stairs tile; boss kill on level 3 triggers victory

### main.py
- Minimal Python entry point with a `main()` function
