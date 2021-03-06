---
title: Where to next?
weight: 3
---

Open the `Turtorial Team` workspace.

The goal of the game is to get Myrtle (the turtle) safely from the beach to the water.
Unfortunately there are rocks in her way, and birds that will interfere with her course.
But, whenever she reaches shelter (in this case, a beach umbrella), she'll get access to the next part of the beach.
Eventually, she should reach the water.

In terms of how the code is going to work, there are three primary components to this game; Myrtle, birds and the world itself.
Each component is explained below.

### Myrtle (the turtle)

Myrtle the turtle is trying to reach the water. She'll move when you press the arrow keys on your keyboard - which means we'll have to program that!
We also need to make sure she avoids the rocks in her way.

### Birds (the enemy)

There will be birds flying above the beach, which will move randomly.
You guessed it, we'll have to code that too!
The birds also have to avoid obstacles, and cannot hide under the beach umbrellas.

### The World (and all its obstacles)

The world itself is made up of a grid, and each character (Myrtle and the birds) and the obstacles can only occupy one cell in the grid at a time.
We'll need to figure out how to place the obstacles, and also how to move to the next part of the beach when Myrtle reaches an umbrella.

## Running the Game

{{% notice tip %}}

Whenever you want to test your code, you'll need to make sure you run the `Game.py` file (this should be the default file when you press the `Run` button).
To see the Python Turtle, hover on the `View Desktop` button, copy the link and open it in a new tab.
![](../../images/running-game.gif)

{{% /notice %}}

## So where to next?

Time to chat to your team and work out who wants to take each role!
The only way to complete the game is for every team member to consistently make it to each of their tutorial's checkpoints, so you'll have to work together to make sure you are on track and help each other out if someone is falling behind.
Each checkpoint will tell you what checkpoint your team members need to reach in order for you to continue.

Once you've decided who will do what, go to your corresponding tutorial:

-   [Myrtle](../../myrtle)
-   [Birds](../../birds)
-   [World](../../world)
