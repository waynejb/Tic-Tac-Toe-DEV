# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the Project

Open `index.html` directly in any modern web browser. No build process, server, or dependencies required.

## Architecture

Single-file web application (`index.html`) with inline CSS and JavaScript — no external libraries or frameworks.

**Key JavaScript structures:**
- `WINS`: Array of 8 winning combinations (rows, columns, diagonals)
- `board`: 9-element array (`''`, `'X'`, or `'O'`)
- `scores`: `{X, O, D}` object persisting across games
- `gameOver`: boolean lock to prevent moves after game ends

**Core functions:**
- `init()` — reset board, set X as first player
- `renderBoard()` — rebuild all 9 cell DOM elements
- `handleClick(i)` — process a move, check win/draw, advance turn
- `checkWin()` — scan all 8 winning lines, return winning line or null
- `highlight(line)` — add pulse animation to winning cells
- `updateScores()` — sync score counters to the DOM

**UI theme:** Dark (`#1a1a2e` bg), red accent (`#e94560`), cyan accent (`#a8dadc`), 3×3 grid with 120px cells.

## Testing

Manual browser testing only. Key scenarios to verify:
- Win detection across all 8 lines (3 rows, 3 columns, 2 diagonals)
- Draw when board fills with no winner
- Score counters increment correctly and persist across restarts
- Winning cells highlight with pulse animation and board locks
