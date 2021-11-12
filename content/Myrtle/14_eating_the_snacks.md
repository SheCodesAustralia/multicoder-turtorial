---
title: 🍽️ Eating the Snacks
weight: 14
---

Now that we have snacks, let's make them worth points.

When Myrtle moves into a cell, we'll need to be able to check if there is food in a cell or not.

Add the following to `World.py`:

```python
# World.py
    def cell_contains_food(self, cell):
        ##
        if cell == self.food_position:
            return True
        ##
        return False
```

Then add a check for food in the existing function for checking if a cell is empty or not.

Add the following to `World.py`:

```diff
# World.py
    def cell_is_empty(self, cell):
        ##
        if self.cell_contains_portal(cell):
            return False
        if self.cell_contains_obstacle(cell):
            return False
+        if self.cell_contains_food(cell):
+            return False
        ##
        return True
```

Then we'll use this to check if Myrtle has landed in a cell with food.

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
+            if self.game.current_world.cell_contains_food(new_pos):
+                self.current_position = new_pos
+                self.forward(STEP_SIZE)
+                self.eat_food()

        if self.is_collision():
            self.game.score = self.game.score - 5
            self.game.update_score()
            self.game.myrtle.goto_start_position()
        ##
        pass
```

If she did land in a cell with food, then we'll add 5 points.

Add the following to `MoveObject.py`:

```python
# MoveObject.py

    def eat_food(self):
        ##
        self.game.score = self.game.score + 5
        self.game.update_score()
        self.game.current_world.food.hideturtle()
        ##
        pass
```

{{% notice info %}}

Try moving Myrtle to the food, the score should go up by 5.

{{% /notice %}}
