---
title: 🎯 Understanding the Grid Coordinate System
weight: 1
---

The world is created using a grid system, and is therefore broken in cells (squares).

{{% notice warning %}}

TODO: explain the system and include a diagram of the grid.

{{% /notice %}}

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
