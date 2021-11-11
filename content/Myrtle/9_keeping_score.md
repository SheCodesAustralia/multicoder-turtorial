---
title: 💯 Keeping Score
weight: 9
---

Ok, Myrtle moves, and depending on where your teammate working on the World is at, she might even be able to move between worlds.
The next step is keep score.
We'll get points for reaching an umbrella and later for eating food.
But we'll lose points when we get caught by a bird.

To start with, we'll set up a score variable. Add the following to `Game.py`:

```diff
# Game.py
class Game:

    def __init__(self):
        self.screen = turtle.Screen()
        self.bird = None
        ##
        self.world = 0
        self.current_world = WORLDS[self.world]
+        self.score = 0
+        self.score_display = turtle.Turtle()
        ##
```

Then complete the function that will show the scrore on the screen. Add the following to `Game.py`:

```python
# Game.py
    def update_score(self):
        ##
        self.score_display.clear()
        self.score_display.write(f'Score: {self.score}', font=("Arial", 16, "normal"))
        ##
        pass
```

Finally, call that function. Add the following to `Game.py`:

```python
# Game.py
    def create_base_world(self):
        self.screen.setup(520, 520)
        self.screen.setworldcoordinates(0, 0, 500, 500)
        self.screen.bgpic(GRID)
        self.screen.bgcolor('black')
        self.screen.addshape(ROCK)
        self.screen.addshape(BIRD)
        self.screen.addshape(PORTAL)
        self.screen.addshape(FOOD)

        canvas = self.screen.getcanvas()
        canvas.itemconfig(self.screen._bgpic, anchor="sw")
        ##
        self.update_score()
        ##
```

{{% notice info %}}

Run the code! You should see the score in the bottom left corner (it will be set to 0 by default).

{{% /notice %}}
