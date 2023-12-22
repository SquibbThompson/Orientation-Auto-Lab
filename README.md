________Overview_________

    For Off Cells (0):
        If h_v is greater than d, the cell turns on.
        Conversely, if d is greater than h_v, the cell turns on, and so do its horizontal and vertical neighbors.

    For On Cells (1):
        If h_v equals d, the cell turns off.
        If d is greater, certain diagonal neighbors turn off.
        If h_v is greater, certain diagonal neighbors turn on, while some horizontal/vertical neighbors turn off.





This Python script simulates a unique type of cellular automaton, leveraging numpy and matplotlib for numerical operations and visualization, respectively. The automaton's evolution rules differ based on the orientation of the cells' neighbors (vertical/horizontal vs. diagonal).
Key Features

    Custom Cellular Automaton Rules: Implements unique rules for cell states based on the count of horizontal/vertical and diagonal neighbors.
    Dynamic Visualization: Uses matplotlib.animation to create a dynamic visualization of the automaton's evolution.
    Binary String to Matrix Conversion: Converts a binary string representing the initial state into a matrix for processing.

Components~~~~~~
String to Binary Matrix Conversion

    string_to_bin_matrix(bin_string): Converts a formatted binary string into a 2D matrix. This matrix represents the initial state of the automaton.

::;;Neighbor Counting Function;::~~

    count_neighbors(grid, x, y): Counts the number of active neighbors for a cell located at (x, y). It differentiates between horizontal/vertical neighbors and diagonal neighbors.

Matrix Update Function:::~~~~~~~

    update_matrix(grid): Applies the automaton rules to update the state of the grid. These rules vary based on the counts of different types of neighbors.

Visualization:::~~~

    Using matplotlib.animation.FuncAnimation, the script animates the evolution of the cellular automaton.

Usage

    Initial State: Define the initial state of the automaton in a binary string format.
    Animation: Run the script to visualize the evolution of the automaton over time.

~~~~~:::Custom Rules::;~~~~~

    The automaton's behavior is governed by distinct rules based on the relative number of active neighbors (horizontal/vertical vs. diagonal).
    For 'off' cells (0), the state changes depending on whether there are more horizontal/vertical neighbors or diagonal neighbors.
    For 'on' cells (1), the state changes are determined by comparing the counts of different types of neighbors.

~~~~~:::Visualization Output:::~~~~~

    The script generates an animated GIF that visualizes the evolution of the cellular automaton over time.


~~~~:::Initialization:::~~~~~ 

The function starts by setting the counts of horizontal/vertical and diagonal neighbors to zero.

    Neighbor Offsets Definition: It defines the relative positions of all possible neighbors around a cell:
        (-1, -1), (-1, 0), (-1, 1), (0, -1), (0, 1), (1, -1), (1, 0), (1, 1)
        These pairs represent the relative positions of the eight neighboring cells in a grid.

    Neighbor Counting Loop:
        The function iterates over these neighbor positions.
        For each position, it calculates the actual grid coordinates of the neighbor by adding the offsets to the current cell's coordinates (x, y).

    Boundary Check: For each neighboring position, it checks if the neighbor lies within the bounds of the grid.

    Neighbor Type Determination and Counting:
        If the neighbor is aligned horizontally or vertically (dx == 0 or dy == 0), it increments the h_v_neighbors count if the neighbor cell is active (1).
        If the neighbor is diagonal (neither dx nor dy is 0), it increments the d_neighbors count for an active neighbor.

    Return Values: The function returns two counts: h_v_neighbors and d_neighbors, representing the number of active neighbors in each category for the cell at (x, y).
![Path_Auto_2for_Cantor_Bakers_Map](https://github.com/SquibbThompson/Orientation-Auto-Lab/assets/124839124/5ae0252c-79f3-4771-83ed-2ae9465c0c83)
