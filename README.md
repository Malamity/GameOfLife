# Project instructions
To create & start using python venv:

python -m venv venv
source venv/bin/activate

Install specific modules with pip:
f.e.:   pip install pygame
Requirements
1. Make simulation real time
2. Add pause / resume logic
3. Add save / load logic
High-level logic
1. Create and init the simulation grid
2. Start the simulation with a tick interval of <n> seconds
3. At each tick:
    3.1. Update the grid - loop over each element of the board
    3.2. Render new generation

General approach
1. Plan & write down the general workflow
  1.1. Define Input&Output 
  1.2. Consider adding validation
2. Separate the main algorithms / actors in the code. Try to abstract as much common code as possible
3. Define communication between the objects
4. List the patterns you could apply
5. Build PoCs (Proof of concepts). Try to separate implementation of specific steps. Prepare smaller modules
    and combine them into a complete application
6. Refine if needed
Deadline - 15th of December 2023
Mail with: 
1. short screen recording demonstrating the new features
2. Linked code
3. Short description of the changes. Which design patterns you used and how you applied them. 

# Game of Life

Project "Game of Life" using Python and the tkinter library for the graphical user interface.

## Libraries Used

- **tkinter**: Used for building the GUI and handling user interactions.
- **random**: Utilized for randomizing the initial state of the grid.
- **pickle**: Enables the saving and loading of game states.

## Techniques and Methods

### Abstract Classes
- **AbstractCell**: An abstract class defining the structure for cells in the grid.
- **AbstractCellFactory**: An abstract class providing a blueprint for creating different types of cells.

### Classes and Methods
- **Cell**: Inherits from AbstractCell, implements the behavior for updating cell states.
- **CellFactory**: Inherits from AbstractCellFactory, generates instances of Cell.
- **GameOfLife**: Manages the game's logic, such as grid updates and checking cell neighbors.
    - `step()`: Advances the game by one step based on the rules.
    - `count_live_neighbours()`: Counts the live neighbors around a cell.
    - `randomize()`: Randomizes the initial state of the grid.

- **GameOfLifeGUI**: Builds the GUI and manages user interactions.
    - `toggle_game_state()`: Starts or stops the game loop.
    - `run_game()`: Controls the continuous running of the game loop.
    - `draw_grid()`: Initializes the grid layout in the GUI.
    - `update_canvas()`: Updates the GUI to reflect the current state of the grid.
    - `toggle_cell()`: Toggles the state of a cell in the grid.
    - `save_game()`: Saves the current game state to a file.
    - `load_game()`: Loads a saved game state from a file.

## Usage
To run the Game of Life, execute the main file `game_of_life.py`. Adjust the grid size and cell size in the `GameOfLifeGUI` instantiation.