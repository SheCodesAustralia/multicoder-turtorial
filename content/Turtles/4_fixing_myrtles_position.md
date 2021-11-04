---
title: Fixing Myrtle's Position
weight: 4
---

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

This relies on the Robot teammate to reach the first checkpoint.
