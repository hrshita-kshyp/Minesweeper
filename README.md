# Minesweeper Game in C++

This is a C++ implementation of the classic Minesweeper game, where the player uncovers squares on a grid, avoiding mines.

## How to Play

1. Choose the difficulty level:
   - Beginner: 9x9 grid with 10 mines.
   - Intermediate: 16x16 grid with 40 mines.
   - Advanced: 24x24 grid with 99 mines.

2. Input the coordinates of the cell you want to uncover.

3. The game continues until you uncover all non-mine cells or hit a mine.

## Code Overview

### Definitions and Macros

- **BEGINNER, INTERMEDIATE, ADVANCED**: Difficulty levels.
- **MAXSIDE**: Maximum side length of the board.
- **MAXMINES**: Maximum number of mines on the board.
- **MOVESIZE**: Maximum number of moves.

### Board Class

Handles the game board and its operations:

- `isValid(int row, int col)`: Checks if a cell is within the board.
- `isMine(int row, int col)`: Checks if a cell contains a mine.
- `makeMove(int* x, int* y)`: Gets user input for the next move.
- `printBoard()`: Displays the current state of the board.
- `countAdjacentMines(int row, int col, int mines[][2])`: Counts the mines adjacent to a cell.
- `placeMines(int mines[][2])`: Randomly places mines on the board.
- `replaceMine(int row, int col)`: Replaces a mine from the specified cell to another location.

### Game Class

Handles the game logic:

- `playMinesweeperUtil(Board& myBoard, Board& realBoard, int mines[][2], int row, int col, int* movesLeft)`: The main recursive function for playing the game.
- `cheatMinesweeper(Board& realBoard)`: Reveals mine locations for cheating.
- `playMinesweeper(Board& realBoard, Board& myBoard)`: Main function to start and manage the game.

### Main Function

- `chooseDifficultyLevel()`: Sets the difficulty level based on user input.
- `main()`: Initializes the game and starts the gameplay loop.

## Compilation and Execution

To compile and run the Minesweeper game:

1. Save the code to a file, e.g., `minesweeper.cpp`.
2. Open a terminal and navigate to the directory containing `minesweeper.cpp`.
3. Compile the code using g++:
   ```sh
   g++ minesweeper.cpp -o minesweeper
