---
title: 😵‍💫 Make Myrtle Spin
weight: 4
---

Now that Myrtle is on the screen, let's start adding the ability for the user to interact with her!

Add the following to `MoveObject.py`:

```python
# MoveObject.py

    def turn_left(self):
        ##
        self.left(90)
        ##
        pass

```

Then add the following to `Characters.py`:

```python
# Characters.py
class UserTurtle(CustomTurtle):

    def __init__(self, colour, shape, speed, game, start_position):
        super().__init__(colour, shape, speed, game, True, start_position)
        ##
        turtle.onkey(self.turn_left, 'Left')
        ##

```

Now when you press the `left` arrow key, Myrtle will rotate to the left!

{{% notice info %}}

Run the code and press the `left` arrow key, watch Myrtle spin!

{{% /notice %}}
