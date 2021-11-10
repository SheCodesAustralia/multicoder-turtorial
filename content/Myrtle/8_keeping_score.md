---
title: Keeping Score
weight: 8
---

```diff
# game.py
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

```python
# game.py
    def update_score(self):
        ##
        self.score_display.clear()
        self.score_display.write(f'Score: {self.score}', font=("Arial", 16, "normal"))
        ##
        pass
```

```python
# game.py
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

TEST you can see the score in the bottom left (will be 0 by default).
