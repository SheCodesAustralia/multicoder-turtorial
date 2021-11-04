---
title: 🔀 Moving Through Portals
weight: 9
---

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

```diff
# MoveObject.py
    def move_forward(self):
        ##
-        self.forward(STEP_SIZE)
+        direction = self.heading()
+        if direction == 90.0:  # facing up
+            new_pos = self.get_forwards_position()
+        if direction == 0.0:  # facing right
+            new_pos = self.get_right_position()
+        if direction == 270.0:  # facing down
+            new_pos = self.get_backwards_position()
+        if direction == 180.0:  # facing left
+            new_pos = self.get_left_position()

+        if not self.game.current_world.cell_contains_portal(new_pos):
+            self.forward(STEP_SIZE)

+        if self.allowed_through_portal:
+            if self.game.current_world.cell_contains_portal(new_pos):
+                self.current_position = new_pos
+                self.forward(STEP_SIZE)
+                self.enter_portal()
        ##
        pass
```

```python
# MoveObject.py
    def enter_portal(self):
        ##
        print('Enter the portal!')
        ##
        pass
```

TEST the print statement appears
