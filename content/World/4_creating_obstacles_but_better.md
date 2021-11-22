---
title: 💁🏽 Creating Obstacles, but better
weight: 4
---

Ok, so we just created a bunch of obstacles.
But becuase of where we put that code, we'll create the obstacles once, and then have to write that code all over again later when we want to move to a new world.
Instead, let's move that code into a function that we'll be able to call as many times as we want.

Cut that code from `Game.py`:

```diff
# Game.py

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

And add it to `World.py`:

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

Then we'll call that function from `Game.py` instead.

```python
# Game.py

    def draw_world(self):
        ##
        self.current_world.draw_obstacles()
        ##
        pass
```

{{% notice info %}}

Run the code, you should see rocks (your obstacles) appear on the screen just as they did before - but this time us developers are happier because that code is neater 😍

{{% /notice %}}

{{% notice warning %}}

Head over to the Python Exercises to learn about **Conditionals** before moving to the next step. [Click here: Conditionals](../../exercises/functions)

{{% /notice %}}
