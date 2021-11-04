---
title: 😵‍💫 Make Myrtle Spin
weight: 2
---

```python
# MoveObject.py

    def turn_left(self):
        ##
        self.left(90)
        ##
        pass

```

```python
# Turtles.py
class UserTurtle(CustomTurtle):

    def __init__(self, colour, shape, speed, game, start_position):
        super().__init__(colour, shape, speed, game, True, start_position)
        ##
        turtle.onkey(self.turn_left, 'Left')
        ##

```

TEST: press the left arrow key, will spin the turtle.
