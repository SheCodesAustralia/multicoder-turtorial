---
title: 🏃‍♀️ Make Myrtle Move
weight: 5
---

Cool, so she spins.
That's particularly useful by itself, so next we'll add the ability for her to move forward.

{{% notice warning %}}

You're in competition with the teammate working on the birds. They may or may not have already completed the `move_forward()` function.

{{% /notice %}}

Add the following to `MoveObject.py`:

```python
# MoveObject.py

    def move_forward(self):
        ##
        self.forward(STEP_SIZE)
        ##
        pass

```

And then add the following to `Characters.py`:

```diff
# Characters.py

class UserTurtle(CustomTurtle):

    def __init__(self, colour, shape, speed, game, start_position):
        super().__init__(colour, shape, speed, game, True, start_position)
        ##
        turtle.onkey(self.turn_left, 'Left')
+        turtle.onkey(self.move_forward, 'Up')
        ##

```

{{% notice info %}}

Run the code and try pressing both the `left` and `up` arrow keys to make Myrtle move around the grid.

{{% /notice %}}

{{% notice warning %}}

Head over to the Python Exercises to learn about lists and loops before moving to the next step. [Click here: Lists](../../exercises/lists)

{{% /notice %}}
