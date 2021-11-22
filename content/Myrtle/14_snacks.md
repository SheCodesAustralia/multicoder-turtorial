---
title: 🥬 Snacks
weight: 14
---

Last but not least, let's add a way for Myrtle to gain bonus points!
We'll do this by putting a snack in the grid somewhere.

Add the following to `World.py`:

```python
# World.py
    def draw_food(self):
        ##
        food_grid_position = convert_coord_to_grid_pos(self.food_position)
        self.food = Obstacle(FOOD, food_grid_position)
        ##
        pass
```

Then call this function by adding the following to `Game.py`:

```diff
# Game.py

    def draw_world(self):
        ##
        self.current_world.draw_obstacles()
        self.current_world.draw_portal()
+        self.current_world.draw_food()
        ##
        pass
```

{{% notice info %}}

Run the code, you should see a plant (the food) appear in the grid.

{{% /notice %}}
