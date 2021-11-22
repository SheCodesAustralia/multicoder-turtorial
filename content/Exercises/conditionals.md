---
title: Conditionals
---

Sometimes we want our program to do different things depending on different situations.

## Example 1

For example, let's write a program that checks whether someone is tall enough to ride a rollercoaster or not.
Let's say they need to be at lest 165cms tall to ride the rollercoaster.

Add the following to `conditionals.py`:

```python
# conditionals.py

height = 185

if height > 165:
    print('Hop on!')
```

Change the `height` variable to a number less than 165, what happens?
We get no output.
This isn't very meaningful to the user, let's add an else statment to fix that.

Add the following to `conditionals.py`:

```diff
# conditionals.py

height = 185

if height > 165:
    print('Hop on!')
+else:
+    print('Sorry, not today :(')
```

But what if someone is exactly 165cms? Change `height` to `165`.
Our program still says they are not tall enough.

Let's modify our _if statement_ to allow 165 and taller, rather than only taller than 165.
Add the following to `conditionals.py`:

```diff
# conditionals.py

height = 185

-if height > 165:
+if height >= 165:
    print('Hop on!')
else:
    print('Sorry, not today :(')
```

{{% notice info %}}

Try running the program with the `height` set to `155`, then `165`, then `175` (i.e. less than, the same as, and greater than 165) and make sure you get the correct output each time.

{{% /notice %}}

{{% notice tip %}}

So how does this actually work?
We are writing what we call **if statements**.
We are saying _if something is true, do this, otherwise, do this_.
In our case, we are telling the user they can ride the rollercoaster if checking their height is greater than or equal to 165cm is true, otherwise it is false and they cannot ride the rollercoaster.

{{% /notice %}}

## Example 2

What if we want to check that something is _exactly_ the same as something else?

For example, maybe we are checking someone has entered the correct pincode to unlock their phone.

Add the following to `conditionals.py`:

```python
# conditionals.py

correct_code = 1234
entered_code = 1234

if entered_code == correct_code:
    print('Unlocked!')
```

{{% notice note %}}

Modify your code to print `Access denied!` if the `entered_code` is incorrect.
Hint: an `else` statement like we used in our last example would be useful here.

{{% /notice %}}

## Example 3

Quite often we have situations that can only be in two states, for example, it is either raining or it isn't.

Let's write a program that tells you whether or not to take an umbrella based on if it is raining or not:

```python
# conditionals.py

is_raining = True
if is_raining:
    print('Take an umbrella.')

```

{{% notice note %}}

Try changing `is_raining` to `False` and adding an `else` to tell you do not need an umbrella.

{{% /notice %}}

{{% notice tip %}}

Up until now, our if statements have been doing **comparisons**, i.e. they compare two things (`height` vs a number, `correct_code` and `entered_code`.
This time we just use the variable name.
That is because comparisons either result in a `True` or `False`, but our `is_raining` umbrella is already defined as either `True` or `False` so we don't need to compare it against anything.

{{% /notice %}}

## Challenges

{{% notice note %}}

Write a program that defines a variable for `temperature` and set its value to a number.
Tell the user to take a jumper if the temperature is less than or equal to 18, and not to worry if it is greater than 18.

{{% /notice %}}

These next one is a little tougher, it's an extra challenge for those of you who have programmed before!

{{% notice note %}}

Modify your program to define another variable for `wind_chill`, and set its value to a number.
Calculate the real feel temperature (the temperature minus the wind chill).
Tell the user to take a jumper if the real feel temperature is less than or equal to 18, and not to worry if it is greater than 18.

{{% /notice %}}

If you've used nested if statements before, give this a go too...

{{% notice note %}}

This time we are going to also factor in if it is raining or not.
If the real feel temperature is less than or equal to 16 and it is raining, tell the user to just stay home.
Otherwise if it is raining tell them to take an unbrella, or if the real feel temperature is less than or equal to 16 tel lthem to take a jumper.

{{% /notice %}}

## Back to the game!

How did you get here?

-   [Myrtle](../../myrtle/8_where_can_i_go)
-   [Birds](../../birds/6_where_can_i_go)
-   [World](../../world/1_grid_coordinates)
