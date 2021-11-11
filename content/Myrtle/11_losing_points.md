---
title: ⬇️ Losing Points
weight: 11
---

When Myrtle gets caught by a bird she is sent back to the start position.
Now that we are keeping score, let's also remove 5 points when she is caught.

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

        if self.is_collision():
+            self.game.score = self.game.score - 5
+            self.game.update_score()
            self.game.myrtle.goto_start_position()
```

{{% notice info %}}

Make Myrtle move into the same cell as the bird, 5 points should be removed.

{{% /notice %}}
