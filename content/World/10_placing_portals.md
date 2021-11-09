---
title: 🚪 Placing Portals
weight: 6
---

```python
# World.py

    def draw_portal(self):
        ##
        portal_grid_position = convert_coord_to_grid_pos(self.portal_position)
        Obstacle(PORTAL, portal_grid_position)
        ##
        pass
```

```python
# game.py

    def draw_world(self):
        ##
        self.current_world.draw_obstacles()
        self.current_world.draw_portal()
        ##
        pass
```

NEXT: conditionals
