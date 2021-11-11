---
title: Where can I go?
weight: 6
---

```diff
# Characters.py
    def move(self):
        ##
+        turning_angles = [0, 90, 180, 270]
+        turning_angle = random.choice(turning_angles)
+        current_direction = self.heading()
+        self.setheading(current_direction + turning_angle)
        num_steps = random.randint(1, 5)
        for step in range(num_steps):
            self.move_forward()
        ##
        pass
```

But what if they try to turn into a rock?

TODO challenge to calculate some of these themselves

```python
# MoveObject.py
    def get_possible_positions(self):
        ##
        forwards_position = self.get_up_position()
        right_position = self.get_right_position()
        left_position = self.get_left_position()
        backwards_position = self.get_down_position()

        valid_directions = []
        if self.game.current_world.cell_is_empty(forwards_position):
            valid_directions.append(0)
        if self.game.current_world.cell_is_empty(right_position):
            valid_directions.append(90)
        if self.game.current_world.cell_is_empty(backwards_position):
            valid_directions.append(180)
        if self.game.current_world.cell_is_empty(left_position):
            valid_directions.append(270)
        return valid_directions
        ##
        pass
```

```diff
# Characters.py
    def move(self):
        ##
-        turning_angles = [0, 90, 180, 270]
+        turning_angles = self.get_possible_positions()
        turning_angle = random.choice(turning_angles)
        current_direction = self.heading()
        self.setheading(current_direction + turning_angle)
        num_steps = random.randint(1, 5)
        for step in range(num_steps):
            self.move_forward()
        ##
        pass
```
