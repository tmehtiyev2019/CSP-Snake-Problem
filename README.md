# Constrained Characters Puzzle Solver: Snake Problem
This Python script solves a constrained character placement puzzle on a square grid. The goal of the puzzle is to fill the empty cells with letters of the alphabet in such a way that each letter has at least one neighboring cell (horizontally or vertically) containing the previous or next letter in the alphabet. The script uses a backtracking algorithm to find a valid solution if one exists. It uses the **Minimum Remaining Values (MRV)** heuristic to select the next unassigned position to be filled on the board. The **find_most_constrained_position** function implements this heuristic by first creating a list of unassigned positions on the board and then selecting the unassigned position with the maximum number of filled neighboring cells.

## Functions
* **is_valid_move(board, x, y, ch)**
This function checks if placing the character **ch** at position (x, y) in the board is a valid move.

* **is_solution_valid(board)**
This function checks if the entire board is a valid solution.

* **find_most_constrained_position(board)**
This function finds the most constrained unassigned position in the board. This position has the most filled neighboring cells.

* **solve_csp(board, letters, remaining_slots, index=0)**
This function solves the constraint satisfaction problem (CSP) by filling the remaining_slots in the board using the given letters. **Backtracking** happens in the solve_csp function when the placement of a letter at the current position does not lead to a valid solution. In such a case, the function backtracks by removing the letter from the board and adding it back to the set of available letters. It then proceeds to try the next available letter in the set. This backtracking is implemented using recursive calls to solve_csp, where the function returns True if a valid solution is found and False otherwise. If the function returns True, the solution is propagated up the call stack until the final solution is returned by the main function. If the function returns False, the current branch of the recursive call is abandoned, and the function backtracks to the previous position on the board to try a different letter.

* **main()**
This function defines the initial board, calculates the number of remaining slots, creates a set of available letters, and calls the solve_csp function to find a solution. If a solution is found, it prints the board; otherwise, it prints an appropriate message.


The script will either print the solved board or a message indicating that no feasible solution exists. You can modify the board variable in the main() function to try different puzzles.
