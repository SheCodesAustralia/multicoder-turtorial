---
title: Checking for Obstacles
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
