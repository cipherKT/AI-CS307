# 8-Puzzle Problem Solver

This Python script provides a solution to the classic 8-puzzle problem using a Breadth-First Search (BFS) algorithm. It features a unique approach to generating valid moves, implemented by the agent.

## Problem Description

The 8-puzzle is a sliding puzzle that consists of a frame of numbered square tiles in random order with one tile missing. The objective is to rearrange the tiles to reach a goal configuration.

## Implementation

The problem is solved using the following key components:

1. State representation: A list of 9 integers, where 0 represents the empty space.
2. Node class: Represents a state in the search tree, with a parent reference for path reconstruction.
3. Functions:
   - `valid_moves(index)`: Returns valid moves for each position (implemented by agent)
   - `get_successors(node)`: Generates all possible valid next states
   - `bfs(start_state, goal_state)`: Implements Breadth-First Search to find a solution

### Unique Approach

The agent has implemented a brute-force approach to determine valid moves:

```python
def valid_moves(index):
    valid_moves = [[1, 3], [-1, 1, 3], [-1, 3], [-3, 1, 3], [-3, -1, 1, 3], [-3, -1, 3], [-3, 1], [-3, -1, 1], [-3, -1]]
    return valid_moves[index]
```

This function returns a pre-computed list of valid moves for each position on the board, allowing for quick lookup during the search process.

## Usage

To run the script, execute it with Python:

```
python puzzle8_solver.py
```

The script will output:
- The randomly generated start and goal states
- The number of nodes explored during the search
- The sequence of states from the initial state to the goal state

## Solution Interpretation

Each state in the solution is represented as a list of 9 integers, where 0 represents the empty space. The tiles are numbered 1-8.

## Random Goal State Generation

The script generates a random goal state by applying 20 random moves to the solved state. This ensures that the puzzle is solvable.
