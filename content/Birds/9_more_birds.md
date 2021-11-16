---
title: 🦅🦅 More Birds!
weight: 9
---

Ok, now that we have got our bird working, let's add more!

First, let's create a new variable for keeping a list of birds.

Add the following to `Game.py`:

```diff
# Game.py
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

Then everytime we create a bird we'll add it to that list.

Add the following to `Game.py`:

```diff
# Game.py
    def create_robot_bird(self):
        ##
        bird = RobotBird(
            colour='#000000',
            shape='classic',
            speed=3,
            game=self,
            start_position=self.current_world.bird_start_position
        )
        self.bird = bird
+        self.birds.append(bird)
        ##
        pass
```

Let's test it out! Make a bunch of birds and make them all move.

Add the following to `Game.py`:

```diff
# Game.py
turtle.listen()

game = Game()
game.create_base_world()
game.draw_world()

##
game.create_user_turtle((0, 0))

game.create_robot_bird()
+game.create_robot_bird()
+game.create_robot_bird()

while True:
+    for bird in game.birds:
+        bird.move()
-    game.bird.move()
##

turtle.mainloop()
```

{{% notice info %}}

Run the game and make sure you can see multiple birds moving around.

{{% /notice %}}
