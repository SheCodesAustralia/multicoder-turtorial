---
title: Where are my birds?
weight: 3
---

We can't actually see the robots yet. Let's fix that:

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

This relies on the Turtle teammate to reach the first checkpoint.
