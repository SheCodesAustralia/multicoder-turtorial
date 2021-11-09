---
title: 🌏 Creating a world
weight: 5
---

TODO use printout to design your world

```python
# World.py

from World import World

WORLDS = [
    ##
    World(
        obstacle_positions=[
            (0, 7), (1, 7), (2, 1), (2, 2), (3, 2), (3, 6), (4, 6),
            (4, 9), (5, 0), (5, 1), (5, 2), (5, 3), (5, 4), (5, 9),
            (5, 10), (6, 9), (7, 3), (7, 4), (7, 5), (7, 6), (7, 9),
            (8, 6), (9, 0), (9, 1), (9, 4), (9, 6), (10, 6)
        ],
        portal_position=(10, 0),
        robot_start_position=(10, 10),
        food_position=(1, 10)
    )
    ##
]
```

```diff
# game.py

class Game:

    def __init__(self):
        self.screen = turtle.Screen()
-        self.current_world = World(
-            obstacle_positions=[],
-            portal_position=(0, 1),
-            robot_start_position=(0, 2),
-            food_position=(0, 3)
-        )
        self.bird = None
        ##
+        self.world = 0
+        self.current_world = WORLDS[self.world]
        ##

```

```diff
# World.py
    def draw_obstacles(self):
        ##
-        position = convert_coord_to_grid_pos((0, 7))
-        Obstacle(ROCK, position)
-        position = convert_coord_to_grid_pos((1, 7))
-        Obstacle(ROCK, position)
-        position = convert_coord_to_grid_pos((2, 1))
-        Obstacle(ROCK, position)
-        position = convert_coord_to_grid_pos((2, 2))
-        Obstacle(ROCK, position)
-        position = convert_coord_to_grid_pos((3, 2))
-        Obstacle(ROCK, position)
-        position = convert_coord_to_grid_pos((3, 6))
-        Obstacle(ROCK, position)
+        for position in self.obstacle_positions:
+            position = convert_coord_to_grid_pos(position)
+            Obstacle(ROCK, position)
        ##
        pass

```

TEST: make sure it's still working
