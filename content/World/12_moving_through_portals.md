---
title: 🔀 Moving Through Portals
weight: 12
---

Now that we have somewhere to go, let's make our portals functional.
Add the following to `MoveObject.py`:

```python
# MoveObject.py

    def enter_portal(self):
        ##
        self.game.find_next_world()
        ##
        pass
```

Then we'll hop over to that `find_next_world()` function in `Game.py` and add the following:

```python
# Game.py

    def find_next_world(self):
        ##
        self.clear_world()
        user_turtle_start_position = self.current_world.portal_position
        self.world = self.world + 1
        self.current_world = WORLDS[self.world]
        self.draw_world()
        self.create_robot_bird()
        self.bird.move()
        self.create_user_turtle(user_turtle_start_position)
        ##
        pass
```

Finally, we'll complete the the `clear_world()` function.
It needs to clear what is on the screen, and set up the base world (the background and grid) again.
Add the following to `Game.py`:

```python
# Game.py

    def clear_world(self):
        ##
        turtle.clearscreen()
        self.create_base_world()
        ##
        pass
```

{{% notice info %}}

Run the code, move Myrtle to a portal. The next world should appear.

{{% /notice %}}
