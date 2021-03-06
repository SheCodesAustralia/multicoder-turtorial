---
title: 😈 Creating an Enemy
weight: 1
---

First thing's first, let's get a bird on the screen.

Add the following to `Game.py`:

```python
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
        ##
        pass
```

That function will create a bird, but we need to call the function in order for that code to run.

Add the following to `Game.py`:

```python
# Game.py
turtle.listen()

game = Game()
game.create_base_world()
game.draw_world()

##
game.create_robot_bird()
##

turtle.mainloop()
```

Finally, to actually see the bird on the screen we need to add the following to `MoveObject.py`:

```python
# MoveObject.py

    def goto_start_position(self):
        ##
        self.penup()
        self.hideturtle()
        self.current_position = self.start_position
        start_position = convert_coord_to_grid_pos(self.start_position)
        self.goto(start_position)
        self.showturtle()
        ##
        pass
```
