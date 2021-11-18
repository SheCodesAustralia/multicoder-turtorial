---
title: 🧮 Calculating Positions
weight: 1
---

Ok, so, we have a bird, we have a Myrtle.
Currently they are both able to walk/fly over obstacles (yes, I know a bird could just fly over a rock anyway, try not to think too hard about it).
We need to fix this so neither can go over obstacles.

For Myrtle the steps will be:

1. Figure out which way she is facing.
2. Calculating what is in front of her.
3. Only go forwards if there is no obstacle there.

For the birds the steps will be:

1. Get all cells to the left, right, forwards and backwards.
2. Figure out which of those cells are empty.
3. Randomly pick one of those cells to move into.

There is a common denominator here: both Myrtle and the birds will need to know what the neighbouring cells are in order to check if they are clear of obstacles.

Your task is to work together to figure out how to calculate those positions.

I've done the first one for you.

Add the following to `MoveObject.py`:

```python
# MoveObject.py

    def get_up_position(self):
        ##
        return (self.current_position[0], self.current_position[1] + 1)
        ##
        pass
```

This function will get the coordinates of the cell above the given cell.

You will need to complete the following functions:

-   `get_right_position()`
-   `get_down_position()`
-   `get_left_position()`

{{% notice tip %}}

The explanation of the grid coordinate system in your printout might be a useful reference here.

{{% /notice %}}

Once you've completed the functions, head back to your tutorial:

-   [Myrtle](../../exercises/conditionals)
-   [Birds](../../exercises/conditionals)
