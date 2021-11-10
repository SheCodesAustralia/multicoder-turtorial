---
title: Ending the Game
weight: 12
---

```python
# game.py
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
        self.current_world.obstacle_positions = []
        self.myrtle = RobotTurtle(
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

```diff
# game.py
    def find_next_world(self):
        ##
+        if (self.world == len(WORLDS) - 1):
+            self.game_end()
+        else:
            self.clear_world()
            user_turtle_start_position = self.current_world.portal_position
            self.world = self.world + 1
            self.current_world = WORLDS[self.world]
            self.draw_world()
            self.create_robot_turtle()
            self.bird.move()
            self.create_user_turtle(user_turtle_start_position)
        ##
        pass
```
