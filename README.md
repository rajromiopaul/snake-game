# 🐍 Snake Game

A classic Snake game built with Python's `turtle` module. Guide the snake to eat food, grow longer, and beat your high score — but don't hit the walls or yourself!

---

## Demo

The game runs in a 600×600 pixel window with a black background. The snake is white, and food appears as a small blue circle at a random position each time it is eaten.

---

## Features

- Smooth snake movement with arrow key controls
- Randomly spawning food that grows the snake on contact
- Live score display with persistent high score tracking
- Automatic reset on wall collision or self-collision
- High score saved to disk between sessions

---

## Requirements

- Python 3.x
- No third-party packages required — the game uses only the Python standard library (`turtle`, `random`, `time`)

---

## Installation

Clone the repository and navigate into the project directory:

```bash
git clone https://github.com/rajromiopaul/snake-game.git
cd snake-game
```

---

## How to Run

```bash
python main.py
```

A game window will open automatically. Click on the window to give it focus before using the keyboard.

---

## Controls

| Key | Action |
|-----|--------|
| ↑ Arrow | Move up |
| ↓ Arrow | Move down |
| ← Arrow | Move left |
| → Arrow | Move right |

The snake cannot reverse direction directly — for example, pressing ↓ while moving up has no effect.

---

## Project Structure

```
snake-game/
├── main.py          # Game loop, screen setup, and collision detection
├── snake.py         # Snake class — movement, growth, and reset logic
├── food.py          # Food class — random positioning on each spawn
├── scoreboard.py    # Scoreboard class — live score and high score display
├── data.txt         # Persistent high score storage (plain text integer)
└── README.md        # Project documentation
```

---

## How It Works

**`main.py`** sets up the game window, instantiates the snake, food, and scoreboard, and runs the main game loop. Each iteration moves the snake, checks for food collisions (triggering growth and a score increment), and checks for wall or self-collisions (triggering a reset).

**`snake.py`** manages the snake as a list of `Turtle` segments. On each move, segments shift forward one position and the head advances. The snake resets by hiding all current segments, clearing the list, and rebuilding from the starting positions.

**`food.py`** extends `Turtle` as a small blue circle. Its `refresh()` method teleports it to a new random position within the play area each time it is eaten.

**`scoreboard.py`** extends `Turtle` to draw the score display at the top of the screen. It reads the stored high score from `data.txt` on startup and writes back to the file whenever a new high score is set.

---

## Concepts Demonstrated

- Object-oriented programming and class inheritance
- Modular code organisation across multiple files
- Basic 2D collision detection
- File I/O for persistent state
- Real-time animation with `turtle.tracer(0)` and `screen.update()`

---

## License

This project is open source and available for personal and educational use.
