---
title: 🧭 Where can I go?
weight: 8
---

Now that we are able to calculate the coordinates of the neighbouring cells, we can use those functions to get the correct cell depending on which way we are facing.

We want to get the cell in front of Myrtle, which means that if she is facing up, she needs to get the cell in `up_position`.

Add the following to `MoveObject.py`:

```diff
# MoveObject.py
    def move_forward(self):
        ##
-        self.forward(CELL_WIDTH)
+        direction = self.heading()
+        new_pos = (0, 0)
+        if direction == 90.0:  # facing up
+            new_pos = self.get_up_position()
        ##
        pass
```

I've given you the code for if she is facing up, you now need to complete the code for if she is facing right, down or left.

I'll give you a hint to get started:

```diff
# MoveObject.py

     def move_forward(self):
        # figure out new position
        direction = self.heading()
        new_pos = self.get_up_position()
        if direction == 90.0:  # facing up
            new_pos = self.get_up_position()
+        if direction == x.x:  # facing right
+            # your code here
+        if direction == x.x:  # facing down
+            # your code here
+        if direction == x.x:  # facing left
+            # your code here
```

You'll need to replace the `x.x` with the correct numbers, and call the correct function for calculating that position.

{{% notice tip %}}

Your printout includes information about how the turtle's headings work.

{{% /notice %}}

Then we'll need to make sure that cell does not contain any obstacles.
Also add the following to `MoveObject.py`:

```diff
# MoveObject.py

    def move_forward(self):
        ##
        direction = self.heading()
        if direction == 90.0:  # facing up
            new_pos = self.get_up_position()

+        if not self.game.current_world.cell_contains_obstacle(new_pos):
+            self.current_position = new_pos
+            self.forward(CELL_WIDTH)
        ##
        pass
```
