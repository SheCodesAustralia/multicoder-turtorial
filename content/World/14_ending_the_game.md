---
title: 🎬 Ending the Game
weight: 14
---

But what happens if I go through a portal and there are no more worlds?
That means Myrtle has finally reached the beach!

Let's fill in the `game_end()` function in `Game.py`:

```python
# Game.py
    def game_end(self):
        ##
        turtle.clearscreen()
        ##
        self.screen.setup(520, 520)
        self.screen.setworldcoordinates(0, 0, 500, 500)
        self.screen.bgpic(OCEAN)
        canvas = self.screen.getcanvas()
        canvas.itemconfig(self.screen._bgpic, anchor="sw")
        ##
        self.update_score()
        self.current_world.obstacle_positions = []
        self.myrtle = RobotBird(
            colour='#402e08',
            shape='turtle',
            speed=1,
            game=self,
            start_position=self.current_world.portal_position
        )
        while True:
            self.myrtle.move()
        ##
```

Then, call this function when we've reached the umbrella in the last world.
Add the following to `Game.py`:

```diff
# Game.py
    def find_next_world(self):
        ##
+        if self.world == len(WORLDS) - 1:
+            self.game_end()
+        else:
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

{{% notice info %}}

Test it! Go through all the worlds and make you can see Myrtle in the ocean at the end!

{{% /notice %}}
