---
title: Myrtle the Turtle
weight: 1
---

```python
# game.py

    def create_user_turtle(self, start_position):
        ##
        self.myrtle = UserTurtle(
            colour='#402e08',
            shape='turtle',
            speed=2,
            game=self,
            start_position=start_position
        )
        ##
        pass
```

```python
# game.py

game = Game()
game.create_base_world()
game.draw_world()

##
game.create_user_turtle((0, 0))
##

turtle.mainloop()
```

TEST: turtle should appear in bottom left corner
