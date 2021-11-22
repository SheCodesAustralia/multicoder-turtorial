---
title: 🕵️ Checking for Obstacles
weight: 5
---

Our characters need a way to check if there are obstacles in their path. Let's write a function to check for us:

```python
# World.py

    def cell_contains_obstacle(self, cell):
        ##
        if cell in self.obstacle_positions:
            return True
        if cell[0] < 0 or cell[0] >= NUM_GRID_ROWS:
            return True
        if cell[1] < 0 or cell[1] >= NUM_GRID_ROWS:
            return True
        ##
        return False
```

{{% notice tip %}}

Note that we are also checking that we haven't reached the end of the grid.
We are checking we are not too far to the left or below the grid by checking the x and y values are greater than 0.
We are also checking we are not too far to the right or above the grid by checking the x and y values are not greater than the number of rows/columns.

{{% /notice %}}

We'll also add a check to another function for checking a cell is completely empty.
Right now we only have obstacles to worry about, but soon we'll also have portals and food to worry about.

Add the following to `World.py`:

```python
# World.py

    def cell_is_empty(self, cell):
        ##
        if self.cell_contains_obstacle(cell):
            return False
        ##
        return True
```
