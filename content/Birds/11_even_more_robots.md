---
title: Even More Robots!
weight: 11
---

Create 1 bird per level.

```diff
# game.py
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
-            self.create_robot_turtle()
-            self.bird.move()
+            for count in range(self.world+1):
+                self.create_robot_turtle()
+            for bird in self.birds:
+                bird.move()
            self.create_user_turtle(user_turtle_start_position)
        ##
        pass
```

We'll need to check for collisions with all the birds:

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
