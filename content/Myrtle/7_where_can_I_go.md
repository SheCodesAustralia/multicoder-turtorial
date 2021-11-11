---
title: Where can I go?
weight: 7
---

TODO could provide a diagram for headings, so they have to work out three of them.

```python
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

        if not self.game.current_world.cell_contains_obstacle(new_pos):
            self.current_position = new_pos
            self.forward(STEP_SIZE)
        ##
        pass
```
