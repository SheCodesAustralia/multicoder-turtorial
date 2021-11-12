---
title: 🕵️ Checking for Obstacles
weight: 4
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

We'll also add a check to another function for checking a cell is completely empty.

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
