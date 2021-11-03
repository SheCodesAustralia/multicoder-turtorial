---
title: Creating a World
weight: 3
---

```diff
# game.py

game = Game()
game.create_base_world()
game.draw_world()

##
-position = convert_coord_to_grid_pos((0, 7))
-Obstacle(ROCK, position)
-position = convert_coord_to_grid_pos((1, 7))
-Obstacle(ROCK, position)
-position = convert_coord_to_grid_pos((2, 1))
-Obstacle(ROCK, position)
-position = convert_coord_to_grid_pos((2, 2))
-Obstacle(ROCK, position)
-position = convert_coord_to_grid_pos((3, 2))
-Obstacle(ROCK, position)
-position = convert_coord_to_grid_pos((3, 6))
-Obstacle(ROCK, position)
##

turtle.mainloop()
```

```python
# World.py

    def draw_obstacles(self):
        ##
        position = convert_coord_to_grid_pos((0, 7))
        Obstacle(ROCK, position)
        position = convert_coord_to_grid_pos((1, 7))
        Obstacle(ROCK, position)
        position = convert_coord_to_grid_pos((2, 1))
        Obstacle(ROCK, position)
        position = convert_coord_to_grid_pos((2, 2))
        Obstacle(ROCK, position)
        position = convert_coord_to_grid_pos((3, 2))
        Obstacle(ROCK, position)
        position = convert_coord_to_grid_pos((3, 6))
        Obstacle(ROCK, position)
        ##
        pass

```

```python
# game.py

    def draw_world(self):
        ##
        self.current_world.draw_obstacles()
        ##
        pass
```

TEST: obstacles should appear
