---
title: Activating Portals
weight: 8
---

So we got some portals to appear, but they don't actually do anything yet... Let's fix that.

When Myrtle lands on a cell, she needs to know if there is an umbrella there, if so, then we'll "enter the portal", i.e. draw the next world.

First we'll write a function to check if a cell contains a portal.
Add the following to `World.py`:

```python
# World.py

    def cell_contains_portal(self, cell):
        ##
        if cell == self.portal_position:
            return True
        return False
        ##
        pass
```

Then we'll use that function to enter a portal when we land on one.
Add the following to `MoveObject.py`:

```diff
# MoveObject.py
    def move_forward(self):
        ##
        direction = self.heading()
        if direction == 90.0:  # facing up
            new_pos = self.get_forwards_position()
        if direction == 0.0:  # facing right
            new_pos = self.get_right_position()
        if direction == 270.0:  # facing down
            new_pos = self.get_backwards_position()
        if direction == 180.0:  # facing left
            new_pos = self.get_left_position()

        if self.game.current_world.cell_is_empty(new_pos):
            self.current_position = new_pos
            self.forward(STEP_SIZE)

+        if self.allowed_through_portal:
+            if self.game.current_world.cell_contains_portal(new_pos):
+                self.current_position = new_pos
+                self.forward(STEP_SIZE)
+                self.enter_portal()
        ##
        pass
```

And then to test that the function is called correctly, we'll just pop a print statement in there.
Add the following to `MoveObject.py`:

```python
# MoveObject.py
    def enter_portal(self):
        ##
        print('Enter the portal!')
        ##
        pass
```

{{% notice info %}}

Run the code, move Myrtle to the portal and check the print statement appears in the console.

{{% /notice %}}
