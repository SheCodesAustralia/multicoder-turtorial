---
title: 🐢 Myrtle the Turtle
weight: 1
---

First thing's first, let's get Myrtle on the screen.

Add the following to `Game.py`:

```python
# Game.py

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

That function will create Myrtle, but we need to call the function in order for that code to run.

Add the following to `Game.py`:

```python
# Game.py

game = Game()
game.create_base_world()
game.draw_world()

##
game.create_user_turtle((0, 0))
##

turtle.mainloop()
```

{{% notice info %}}

Run the code! You should see a tiny turtle appear in the bottom left corner.

{{% /notice %}}
