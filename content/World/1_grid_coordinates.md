---
title: Understanding the Grid Coordinate System
weight: 1
---

TODO: diagram of grid

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
