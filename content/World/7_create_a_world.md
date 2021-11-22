---
title: 🌏 Creating a world
weight: 7
---

The end goal of the game is to have multiple sections of a beach that Myrtle moves through.
Right now we have one section of beach, or "world", but eventually we are going to want many.
Each world will have obstacles in different places, as well as an umbrella for shelter, which acts as the portal to next part of the beach (aka the next world).
Eventually we'll also have food that Myrtle can eat to collect extra points.

We're going to put all of these worlds in a list together.
We've designed the first one for you, you'll make your own shortly.
Add the following to `worlds.py`:

```python
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
        bird_start_position=(10, 10),
        food_position=(1, 10)
    )
    ##
]
```

Since we have now saved a world in our `worlds.py` file, we can remove the starter world from `Game.py`, and use our new world instead:

```diff
# Game.py

class Game:

    def __init__(self):
        self.screen = turtle.Screen()
-        self.current_world = World(
-            obstacle_positions=[],
-            portal_position=(0, 1),
-            bird_start_position=(0, 2),
-            food_position=(0, 3)
-        )
        self.bird = None
        ##
+        self.world = 0
+        self.current_world = WORLDS[self.world]
        ##

```

Previously, we manually defined each obstacle, but now we want to create an obstacle for every coordinate given in the list in `worlds.py`.
Let's remove our code from earlier and replace it with a for loop:

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

Not only does this make our code neater, but it also means that if you change the coordinates in `worlds.py`, the obstacles will still be created in the correct place.

{{% notice info %}}

Run the code an make sure you can see all the obstacles!

{{% /notice %}}
