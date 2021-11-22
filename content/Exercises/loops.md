---
title: Loops
---

Ok, so we just learned about lists, and how they are useful for storing related information in the same variable.
But what if we also wanted to do something with each item in that list.

## Example 1

Let's start with just printing each item in a list.
With the skills we've learned so far, this is how we would achieve this.

Add the following to `loops.py`:

```python
# loops.py

pets = ['Chili', 'Ivy', 'Remus', 'Enzo']
print(pets[0])
print(pets[1])
print(pets[2])
print(pets[3])
```

But that is very repetative, and what if we added another pet?
We'd have to also add another print statement.
What if we added 100 more pets?
That's a lot of print statements to write out!

Instead, we can use a **for loop** to do this for us.
Add the following to `loops.py`:

```diff
# loops.py

pets = ['Chili', 'Ivy', 'Remus', 'Enzo']
+for pet in pets:
+   print(pet)
```

When you run this, you should see each pet name appear on it's own line in the console.

This is how that for loop works:

1. Assigns the value of `pet` to be the first item in the list (`Chilli`), so this is like writing `pet = 'Chilli'`
2. Prints the value of pet, i.e. prints `Chilli`.
3. Assigns the value of `pet` to be the second item in the list (`Ivy`), so this is like writing `pet = 'Ivy'`
4. Prints the value of pet, i.e. prints `Ivy`.
5. Assigns the value of `pet` to be the first item in the list (`Remus`), so this is like writing `pet = 'Remus'`
6. Prints the value of pet, i.e. prints `Remus`.
7. Assigns the value of `pet` to be the second item in the list (`Enzo`), so this is like writing `pet = 'Enzo'`
8. Prints the value of pet, i.e. prints `Enzo`.

Notice any patterns here?
It does the same thing for each item in the list.

{{% notice note %}}

Try adding 3 more items to the list, you should see them also printed line by line in the console.

{{% /notice %}}

## Example 2

But what if instead of doing something for every item in a list, we actually just wanted to do something a specific number of times?
In this situation, we can use `range`.

Add the following to `loops.py`:

```python
# loops.py

for number in range(10):
    print(number)
```

This will run the loop 10 times.
But did you notice the numbers it printed were actually `0` to `9`, not `1` to `10` like you might expect?
That is because computers start counting at 0, not 1 (you might recall learning this when we were learning about lists).

But what if I did want to start at `1`, and also skip every other number?
Add the following to `loops.py`:

```python
# loops.py

for number in range(1, 10, 2):
    print(number)
```

When you run the code, the numbers you should see printed are: `1`, `3`, `5`, `7`, `9`.

{{% notice note %}}

Use for loop and `range()` to print the numbers: `0`, `5`, `10`, `15`, `20`, `25`, `30`, `35`, `40`, `45` and `50`.

{{% /notice %}}

## Back to the game!

How did you get here?

-   [Myrtle](../../myrtle/6_teamwork)
-   [Birds](../../birds/4_teamwork)
-   [World](../../world/3_creating_obstacles_but_better)
