---
title: Collisions
weight: 8
---

Ok, so our bird now randomly flies around, but that's about it.
When the bird is in the same cell as Myrtle, we want to sent Myrtle back to her start position. That means we need to know when the bird and Myrtle are both in the same cell.

Add the following to `MoveObject.py`:

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

Then call that function when either the bird or Myrtle move.

Add the following to `MoveObject.py`:

```diff
# MoveObject.py

    def move_forward(self):
        ##
        direction = self.heading()
        if direction == 90.0:  # facing up
            new_pos = self.get_up_position()
        if direction == 0.0:  # facing right
            new_pos = self.get_right_position()
        if direction == 270.0:  # facing down
            new_pos = self.get_down_position()
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

{{% notice info %}}

Test it out by moving Myrtle into the same cell as the bird - Myrtle should reappear at her start position.

{{% /notice %}}
