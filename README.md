# TetrisStyledGame (Java / Swing)

A Tetris-style game built in **Java (Swing)** with:
- **Solo** and **Extended (2-board) mode**
- **Human, AI, and External-controller** player types
- **Configurable field size & start level**
- **High score table** persisted to JSON
- Menu UI (Splash → Main Menu → Play / Configuration / High Scores)

> This project is an adaptation of a prior university group assignment and may still receive some updates.

---

## Gameplay

https://github.com/user-attachments/assets/e0733399-1d70-4f90-a240-170be6002dce

---

## How to Run

### Requirements
- Java 17+ recommended (project uses modern Java features like `switch` expressions in places)

### Run (IDE)
1. Clone the repository
2. Open in IntelliJ / Eclipse
3. Run: `src/Main.java`

`Main` launches the Swing app and opens the **Splash screen**, then the main menu.

---

## Game Modes & Player Types

The game is built around a small “game factory” that can create different game implementations depending on config:

### Modes
- **Solo mode:** one board (Player One only)
- **Extended mode:** two boards side-by-side (Player One + Player Two)

### Player Types
- **Human** – keyboard-controlled
- **AI** – the game plays for you using a board-evaluation heuristic
- **External** – driven by an `ExternalController` (intended for client/server or external input)

You can configure player types in the **Configuration** screen.

---

## Controls (as implemented)

### In-game options (GamePanel)
- `P` — Pause / Resume
- `S` — Toggle sound effects
- `M` — Toggle music

### Piece movement (default / typical player)
In the default `GameDefault` implementation:
- `←` / `→` — Move left / right
- `↓` — Soft drop (faster fall)
- `↑` — Rotate clockwise
- `Ctrl` — Rotate counter-clockwise
- `Space` — Drop (currently implemented as repeated soft-drop; effectively a faster drop)

### Multiplayer / 2P controls
When **two human players** are enabled, Player One uses a different key set:

**Player One (2P Human vs Human):**
- `,` — Move left
- `.` — Move right
- `Space` — Drop (faster fall)
- `L` — Rotate clockwise

**Player Two (2P Human):**
- `←` / `→` — Move left / right
- `↓` — Soft drop
- `↑` — Rotate clockwise
- `Ctrl` — Rotate counter-clockwise

---

## Scoring & Leveling

Scoring is based on **lines cleared at once**:
- 1 line: +100  
- 2 lines: +300  
- 3 lines: +600  
- 4 lines: +1000  

Level increases every **10 lines cleared**:
- `level = (linesCleared / 10) + initialLevel`

Speed increases by reducing a per-tick “period” value (with a minimum enforced in code).

---

## High Scores (Top 10)

High scores are stored in:
- `src/config/scores.json`

The game keeps a **top 10** list and saves when a score qualifies (and is > 0).  
High Score UI shows **Rank / Name / Player Type / Score**, and includes a reset button.

---

## Configuration Options

The Configuration dialog lets you adjust:
- Field Width (cells): **5 → 15**
- Field Height (cells): **15 → 30**
- Start Level: **1 → 10**
- Music on/off
- Sound effects on/off
- Player One type: `Human | AI | External`
- Player Two type: `None | Human | AI | External`

---
