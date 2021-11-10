---
title: Snacks
weight: 14
---

```python
# World.py
    def draw_food(self):
        ##
        food_grid_position = convert_coord_to_grid_pos(self.food_position)
        self.food = Obstacle(FOOD, food_grid_position)
        ##
        pass
```

```diff
# game.py

    def draw_world(self):
        ##
        self.current_world.draw_obstacles()
        self.current_world.draw_portal()
+        self.current_world.draw_food()
        ##
        pass
```

TEST should draw a snack
