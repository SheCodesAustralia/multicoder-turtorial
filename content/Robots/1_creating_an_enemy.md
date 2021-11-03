---
title: Creating an Enemy
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

```python
# MoveObject.py

class MoveObject:

    def __init__(self, game, allowed_through_portal, start_position):
        self.game = game
        self.start_position = start_position
        self.current_position = start_position
        self.allowed_through_portal = allowed_through_portal
        ##
        self.goto_start_position()
        ##

```

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

TODO explain this line by line.
WARNING the robot might have added this already

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
