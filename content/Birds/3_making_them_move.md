---
title: 🏃 Make them Move
weight: 3
---

Cool, we have a bird.
Next step: make it move!

{{% notice warning %}}

You're in competition with the teammate working on Myrtle. They may or may not have already completed the `move_forward()` function.

{{% /notice %}}

Add the following to `MoveObject.py`:

```python
# MoveObject.py

    def move_forward(self):
        ##
        self.forward(CELL_WIDTH)
        ##
        pass
```

And then add the following to `Characters.py`:

```python
# Characters.py

class RobotBird(CustomTurtle):
    def __init__(self, colour, shape, speed, game, start_position):
        super().__init__(colour, shape, speed, game, False, start_position)
        ##
        # YOUR CODE HERE
        ##

    def move(self):
        ##
        num_steps = random.randint(1, 5)
        for step in range(num_steps):
            self.move_forward()
        ##
        pass
```

Finally, call the function that will actually trigger the movement in the bird.
Add the following to `Game.py`:

```diff
# Game.py
turtle.listen()

game = Game()
game.create_base_world()
game.draw_world()

##
game.create_user_turtle((0, 0))
game.create_robot_bird()

+game.bird.move()
##

turtle.mainloop()
```

{{% notice info %}}

Everytime you start the game the bird should move a random number of steps.
Try restarting the game a few times to see this in action.

{{% /notice %}}

But we want the turtle to keep moving right?
Add the following to `Game.py`:

```diff
# Game.py
turtle.listen()

game = Game()
game.create_base_world()
game.draw_world()

##
game.create_user_turtle((0, 0))
game.create_robot_bird()

-game.bird.move()
+while True:
+    game.bird.move()
##

turtle.mainloop()
```

{{% notice info %}}

Restart the game, the bird should keep moving....too far, did it just fly off the screen?
Don't worry, we'll fix that in a later step.

{{% /notice %}}

{{% notice warning %}}

Head over to the Python Exercises to learn about lists before moving to the next step. [Click here: Lists](../../exercises/lists)

{{% /notice %}}
