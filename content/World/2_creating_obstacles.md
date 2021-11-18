---
title: 🪨 Creating Obstacles
weight: 2
---

Now that we know where the center of each cell is, let's use that to place some obstacles.

Add the following to `Obstacle.py`:

```python
# Obstacle.py

class Obstacle(turtle.Turtle):

    def __init__(self, shape, position):
        super().__init__()
        ##
        self.hideturtle()
        self.speed(10)
        self.shape(shape)
        self.penup()
        self.shapesize(STEP_SIZE/STAMP_SIZE, STEP_SIZE/STAMP_SIZE, STEP_SIZE/STAMP_SIZE)
        self.goto(position)
        self.showturtle()
        ##
```

This code creates a template for obstacles.
It is what defines how big an obstacles should appear on the screen, and how to get to it's final position.

The next bit of code is what fills in the blanks for the template (e.g. where on the screen to go and what shape it should be) and actually creates the obstacles.

Add the following to `Game.py`:

```python
# Game.py

game = Game()
game.create_base_world()
game.draw_world()

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

turtle.mainloop()
```

{{% notice info %}}

Run the code, you should see rocks (your obstacles) appear on the screen!

{{% /notice %}}

{{% notice warning %}}

Head over to the Python Exercises to learn about functions before moving to the next step. [Click here: Functions](../../exercises/functions)

{{% /notice %}}
