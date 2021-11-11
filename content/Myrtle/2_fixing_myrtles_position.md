---
title: Fixing Myrtle's Position
weight: 2
---

There is a slight problem with Myrtle's position, she is on the grid lines rather than being in the center of the calls.
Let's fix that.
Add the following to `MoveObject.py`:

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

{{% notice info %}}

Run the code and make sure Myrtle is in the center of the cell.

{{% /notice %}}

{{% notice warning %}}

There is a catch here though! This will not work until the teammate working on the birds also reaches their first checkpoint.

{{% /notice %}}
