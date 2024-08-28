### Tetris Game Overview

**Tetris** is a popular tile-matching puzzle game originally designed and programmed by Alexey Pajitnov in 1984. The game consists of a grid (board) where different shapes made up of four squares each (called tetrominoes) fall from the top. The player must move and rotate these shapes to fit them together at the bottom of the grid, aiming to fill horizontal lines without gaps. When a line is completely filled, it disappears, and the player earns points. The game ends when the shapes stack up to the top of the grid and there is no room for new pieces.

### Summary of Java Code for Tetris Game

The code consists of three Java classes:

1. **`Tetris.java`**: This is the main class that initializes the game window (JFrame) and the game board (Board). It handles the GUI setup and starts the game.
2. **`Shape.java`**: This class defines the tetrominoes (Tetris pieces). It manages different shapes, their coordinates, and methods for random shape selection and rotation.
3. **`Board.java`**: This class represents the game board where the game logic is implemented. It handles the movement of shapes, collision detection, line clearing, and game cycles.

---

### Detailed Implementation

#### 1. `Tetris.java`
- **Purpose**: Initializes the game and sets up the GUI.
- **Key Components**:
  - `JLabel statusbar`: Displays the current game score or status (e.g., "paused").
  - `initUI()`: Sets up the main window (`JFrame`), status bar, and board.
  - `main()`: Runs the game on the Event Dispatch Thread (EDT) for thread safety.

#### 2. `Shape.java`
- **Purpose**: Represents the tetrominoes in the game.
- **Key Components**:
  - **Enum `Tetrominoe`**: Defines different shapes (e.g., `NoShape`, `ZShape`, `SShape`, `LineShape`, etc.).
  - `coords`: A 2D array that stores the coordinates of the shape.
  - `setShape()`, `setRandomShape()`: Methods to set a specific shape or a random shape.
  - `rotateLeft()` and `rotateRight()`: Methods to rotate the shape left or right.

#### 3. `Board.java`
- **Purpose**: Represents the game board and contains the core game logic.
- **Key Components**:
  - **Constants**: 
    - `BOARD_WIDTH` and `BOARD_HEIGHT`: Dimensions of the board.
    - `PERIOD_INTERVAL`: Timer interval for game updates.
  - `Shape curPiece`: The current tetromino.
  - `Tetrominoe[] board`: Array representing the game board and storing the positions of the tetrominoes.
  - `start()`: Initializes the game, starts the timer, and sets the first piece.
  - `doDrawing(Graphics g)`: Draws the current state of the game on the screen.
  - `tryMove()`: Checks if a piece can be moved to a new position.
  - `removeFullLines()`: Removes completed lines from the board and updates the score.
  - `GameCycle`: Handles the game loop and periodically updates the game state.
  - **Key Listeners**: 
    - `TAdapter`: A `KeyAdapter` to handle keyboard events (e.g., moving and rotating pieces, pausing the game).

### What is Tetris?
- **Gameplay**:
  - The player controls the falling tetrominoes by moving them left or right and rotating them to fit into empty spaces.
  - The goal is to complete full horizontal lines with no gaps.
  - When a line is completed, it is removed, and the player scores points.
  - As the game progresses, the speed of falling tetrominoes increases.
  - The game ends when the tetrominoes reach the top of the screen, and there is no room for a new piece.
