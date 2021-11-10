---
title: Gaining Points
weight: 12
---

```diff
# game.py
    def find_next_world(self):
        ##
        self.clear_world()
        user_turtle_start_position = self.current_world.portal_position
+        self.score = self.score + 10
+        self.update_score()
        self.world = self.world + 1
        self.current_world = WORLDS[self.world]
        self.draw_world()
        self.create_robot_turtle()
        self.bird.move()
        self.create_user_turtle(user_turtle_start_position)
        ##
        pass
```

TEST going through a portal should increase the score
