---
title: Make Myrtle Move
weight: 3
---

```python
# MoveObject.py

    def move_forward(self):
        ##
        self.forward(STEP_SIZE)
        ##
        pass

```

```python
# Turtles.py

class UserTurtle(CustomTurtle):

    def __init__(self, colour, shape, speed, game, start_position):
        super().__init__(colour, shape, speed, game, True, start_position)
        ##
        turtle.onkey(self.move_forward, 'Up')
        turtle.onkey(self.turn_left, 'Left')
        ##

```

TEST: press the up arrow key, will move the turtle forwards.

But myrtle is on the grid lines, not in the cells. Let's fix that.

```python
# MoveObject.py

class MoveObject:

    def __init__(self, game, allowed_through_portal, start_position):
        self.game = game
        self.start_position = start_position
        self.current_position = start_position
        self.allowed_through_portal = allowed_through_portal
        ##
        self.goto_start_position()
        ##

```

```python
# MoveObject.py

    def goto_start_position(self):
        ##
        self.penup()
        self.hideturtle()
        self.current_position = self.start_position
        start_position = convert_coord_to_grid_pos(self.start_position)
        self.goto(start_position)
        self.showturtle()
        ##
        pass
```

TODO explain this line by line.
WARNING the robot might have added this already
