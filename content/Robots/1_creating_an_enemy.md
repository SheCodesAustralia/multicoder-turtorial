---
title: 😈 Creating an Enemy
weight: 1
---

```python
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
        ##
        pass
```

```python
# game.py
turtle.listen()

game = Game()
game.create_base_world()
game.draw_world()

##
game.create_robot_turtle()
##

turtle.mainloop()
```

TEST: but the turtle doesn't appear, let's fix that...

Let's also make the birds a bit bigger so they are easier to see:

```python
# Turtles.py

class RobotTurtle(CustomTurtle):
    def __init__(self, colour, shape, speed, game, start_position):
        super().__init__(colour, shape, speed, game, False, start_position)
        ##
        self.shapesize(2, 2)
        ##

```

TODO: loops before step 2
