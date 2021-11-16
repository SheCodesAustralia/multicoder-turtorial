---
title: ⬆️ Gaining Points
weight: 12
---

Myrtle looses points for colliding with a bird, but gains points when she reaches an umbrella. Let's add the latter step now.

Add the following to `Game.py`:

```diff
# Game.py
    def find_next_world(self):
        ##
        self.clear_world()
        user_turtle_start_position = self.current_world.portal_position
+        self.score = self.score + 10
+        self.update_score()
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

Make Myrtle move to an umbrella, the score should increase by 10.

{{% /notice %}}
