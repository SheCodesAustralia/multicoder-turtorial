---
title: 🚪 Placing Portals
weight: 7
---

The world we just added to `worlds.py` included a `portal_position`, but we can't see it on the screen yet, let's fix that.

Add the following to `World.py`:

```python
# World.py

    def draw_portal(self):
        ##
        portal_grid_position = convert_coord_to_grid_pos(self.portal_position)
        Obstacle(PORTAL, portal_grid_position)
        ##
        pass
```

Notice that this code is _very_ similar to when we created obstacles. That's because thanks to the obstacle template we made earlier, we can use the same code to make lots of different shapes, in this case, a portal (well, umbrella, use your imagination).

Next let's make sure we actually call the function that we just wrote.
Add the following to `Game.py`:

```diff
# Game.py

    def draw_world(self):
        ##
        self.current_world.draw_obstacles()
+        self.current_world.draw_portal()
        ##
        pass
```

{{% notice info %}}

The portal should now appear in the grid when you run the code.

{{% /notice %}}
