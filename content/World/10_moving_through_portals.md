---
title: 🔀 Moving Through Portals
weight: 10
---

Make at least one more world to move into:

```diff
# worlds.py

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
-    )
+    ),
+    World(
+        obstacle_positions=[(x, y)],
+        portal_position=(x, y),
+        robot_start_position=(x, y),
+        food_position=(x, y)
+    )
    ##
]
```

```python
# MoveObject.py

    def enter_portal(self):
        ##
        self.game.find_next_world()
        ##
        pass
```

```python
# game.py

    def clear_world(self):
        ##
        turtle.clearscreen()
        self.create_base_world()
        ##
        pass
```

```python
# game.py

    def find_next_world(self):
        ##
        self.clear_world()
        user_turtle_start_position = self.current_world.portal_position
        self.world = self.world + 1
        self.current_world = WORLDS[self.world]
        self.draw_world()
        self.create_robot_turtle()
        self.bird.move()
        self.create_user_turtle(user_turtle_start_position)
        ##
        pass
```

TEST entering a portal - the next world should appear.
