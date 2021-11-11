---
title: Collisions
weight: 8
---

```python
# MoveObject.py

    def is_collision(self):
        ##
        if self.game.myrtle.current_position == self.game.bird.current_position:
            return True
        return False
        ##
        pass
```

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

        if self.allowed_through_portal:
            if self.game.current_world.cell_contains_portal(new_pos):
                self.current_position = new_pos
                self.forward(STEP_SIZE)
                self.enter_portal()

+        if self.is_collision():
+            self.game.myrtle.goto_start_position()
        ##
        pass
```

TEST: moving into the same cell as the bird will put you back to the start position.
