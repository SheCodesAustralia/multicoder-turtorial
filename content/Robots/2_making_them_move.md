---
title: 🏃 Make them Move
weight: 2
---

```python
# MoveObject.py

    def move_forward(self):
        ##
        self.forward(STEP_SIZE)
        ##
        pass
```

```python
# Turtles.py

class RobotTurtle(CustomTurtle):
    def __init__(self, colour, shape, speed, game, start_position):
        super().__init__(colour, shape, speed, game, False, start_position)
        ##
        self.shapesize(2, 2)
        ##

    def move(self):
        ##
        num_steps = random.randint(1, 5)
        for step in range(num_steps):
            self.move_forward()
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

game.bird.move()

##

turtle.mainloop()
```

Everytime you start the game, the turtle should move a random number of steps.