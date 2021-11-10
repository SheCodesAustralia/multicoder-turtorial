---
title: More Robots!
weight: 9
---

```diff
# game.py
class Game:

    def __init__(self):
        self.screen = turtle.Screen()
        self.bird = None
        ##
+        self.birds = []
        self.world = 0
        self.current_world = WORLDS[self.world]
        self.score = 0
        self.score_display = turtle.Turtle()
        ##
```

```diff
# game.py
    def create_robot_turtle(self):
        ##
        bird = RobotTurtle(
            colour='#000000',
            shape='classic',
            speed=3,
            game=self,
            start_position=self.current_world.robot_start_position
        )
        self.bird = bird
+        self.birds.append(bird)
        ##
        pass
```

```diff
# game.py
turtle.listen()

game = Game()
game.create_base_world()
game.draw_world()

##
game.create_user_turtle((0, 0))

game.create_robot_turtle()
+game.create_robot_turtle()
+game.create_robot_turtle()

while True:
+    for bird in game.birds:
+        bird.move()
-    game.bird.move()
##

turtle.mainloop()

```

TEST start the game - should be three birds at the start.