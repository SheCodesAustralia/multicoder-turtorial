---
title: 🏃‍♀️ Make Myrtle Move
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
