---
title: 🧑‍🎨 Design your own world!
weight: 10
---

In order to use the portals, we need somewhere to go!
It's time for you to design at least one more world.
We've given you the template for the code below, you need to fill in the blanks (i.e. the `(x, y)` coordinates).
Feel free to use the first world as an example to get you started.

{{% notice tip %}}

To help you out, you have been given a print out of an 11x11 grid, with some coordinates given to help you map your design to the x and y positions.
The first grid is to give you an example of how you could design your world, and you'll notice it matches the coordinates given in the first world in the code below.
So get our your pen or pencil, plan your world, then translate it to coordinates in the code!

{{% /notice %}}

Add your world to `worlds.py`:

```diff
# worlds.py

from World import World

WORLDS = [
    ##
    World(
        obstacle_positions=[
            (0, 7), (1, 7), (2, 1), (2, 2), (3, 2), (3, 6), (4, 6),
            (4, 9), (5, 0), (5, 1), (5, 2), (5, 3), (5, 4), (5, 9),
            (5, 10), (6, 9), (7, 3), (7, 4), (7, 5), (7, 6), (7, 9),
            (8, 6), (9, 0), (9, 1), (9, 4), (9, 6), (10, 6)
        ],
        portal_position=(10, 0),
        bird_start_position=(10, 10),
        food_position=(1, 10)
-    )
+    ),
+    World(
+        obstacle_positions=[(x, y)],
+        portal_position=(x, y),
+        bird_start_position=(x, y),
+        food_position=(x, y)
+    )
    ##
]
```
