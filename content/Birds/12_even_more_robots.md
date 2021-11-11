---
title: Even More Robots!
weight: 12
---

To make things a little more interesting, we'll add a new bird for each world. So the first world will have one bird, the second world will have two birds, and so on...

Add the following to `Game.py`:

```diff
# Game.py
    def find_next_world(self):
        ##
        if (self.world == len(WORLDS) - 1):
            self.game_end()
        else:
            self.clear_world()
            user_turtle_start_position = self.current_world.portal_position
            self.world = self.world + 1
            self.current_world = WORLDS[self.world]
            self.draw_world()
-            self.create_robot_bird()
-            self.bird.move()
+            num_birds = self.world + 1
+            for count in range(num_birds):
+                self.create_robot_bird()
+            for bird in self.birds:
+                bird.move()
            self.create_user_turtle(user_turtle_start_position)
        ##
        pass
```

We'll need to check for collisions with all the birds.

Add the following to `MoveObject.py`:

```diff
# MoveObject.py
    def is_collision(self):
        ##
-        if self.game.myrtle.current_position == self.game.bird.current_position:
-            return True
+        for bird in self.game.birds:
+            if self.game.myrtle.current_position == bird.current_position:
+                return True
        return False
        ##
        pass
```

Finally, make sure you remove the additional birds from testing earlier.

Remove the following from 'Game.py`:

```diff
# Game.py
turtle.listen()

game = Game()
game.create_base_world()
game.draw_world()

##
game.create_user_turtle((0, 0))

game.create_robot_bird()
-game.create_robot_bird()
-game.create_robot_bird()

while True:
    for bird in game.birds:
        bird.move()
##

turtle.mainloop()
```
