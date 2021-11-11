---
title: 🦅 Grow the Birds
weight: 4
---

Let's also make the birds a bit bigger so they are easier to see.

Add the following to `Characters.py`:

```python
# Characters.py

class RobotBird(CustomTurtle):
    def __init__(self, colour, shape, speed, game, start_position):
        super().__init__(colour, shape, speed, game, False, start_position)
        ##
        self.shapesize(2, 2)
        ##

```

{{% notice info %}}

Run the code, the bird should now be twice as big as it was before.

{{% /notice %}}
