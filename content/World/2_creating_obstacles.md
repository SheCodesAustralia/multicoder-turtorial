---
title: 🪨 Creating Obstacles
weight: 2
---

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

```python
# game.py

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

TEST: obstacles should appear
