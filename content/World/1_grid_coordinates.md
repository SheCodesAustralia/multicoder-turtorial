---
title: 🎯 Understanding the Grid Coordinate System
weight: 1
---

The world is created using a grid system, and is therefore broken in cells (squares).

The world is represented by a grid, and every cell in that grid has a coordinate. Each coordinate is made up of two numbers, a number for it’s x position, and a number for it’s y position.

Take this grid as an example:

![](../../images/grid.png)

Let’s focus on the highlighted cell. This cell’s (x,y) coordinates are (2,1).

-   x = 2 because we are in the second column (we start at zero, not one).
-   y = 1 because we are in the first row (again, we start at zero) counting from the bottom up.

See if you can fill in the coordinates of the three blank cells and show a mentor to check your understanding (use the grid on your worksheet).

So the first thing that we are going to do is write some code that will help all the characters and obstacles in the game to work out where the center of the cell is.

Add the following code to `utils.py`:

```python
# utils.py

def convert_coord_to_grid_pos(coordinates):
    ##
    x = coordinates[0]
    y = coordinates[1]
    if x == 0:
        x = STEP_SIZE * 0.5
    else:
        x = STEP_SIZE * (0.5 + x)
    if y == 0:
        y = STEP_SIZE * 0.5
    else:
        y = STEP_SIZE * (0.5 + y)
    return (x, y)
    ##
    return (22.5, 22.5)
```
