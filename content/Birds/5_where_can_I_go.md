---
title: 🤷🏾‍♂️ Where can I go?
weight: 5
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
To handle this, we'll complete the `get_possible_positions()` function to check if neighbouring cells are empty, if they are, the direction will be returned in a list of valid directions.

Add the following to `MoveObject.py`:

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
        return valid_directions
        ##
        pass
```

I've given you the code for checking the cell above the bird, you now to need to complete the code for the the cells to the right, below and left.

I'll give you a hint to get started:

```diff
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
+        if self.game.current_world.cell_is_empty(some_position):
+            valid_directions.append(x)
+        if self.game.current_world.cell_is_empty(some_position):
+            valid_directions.append(x)
+        if self.game.current_world.cell_is_empty(some_position):
+            valid_directions.append(x)
        return valid_directions
        ##
        pass
```

You will need to replace the `some_position` and `x` values with the correct variables and numbers.

Once your function is ready to go, call it it by adding the following to `Characters.py`:

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
