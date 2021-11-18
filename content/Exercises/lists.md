---
title: Lists
---

Sometimes it's useful to store multiple pieces of data in one variable.
We can use **lists** to do this.

## Example 1

For example, let's create a list of pets.
Add the following to `lists.py`:

```python
# lists.py

pets = ['Chili', 'Ivy', 'Remus', 'Enzo']
```

Every **item** in the list has an **index**, i.e. it's position.
Computers start counting at zero, so if I want to get the first pet, I use the inded `0`.

Try it out, add the following to `lists.py`:

```diff
# lists.py

pets = ['Chili', 'Ivy', 'Remus', 'Enzo']
+print(pets[0])
```

{{% notice note %}}

Try and print the second and third items in the list, i.e. `Ivy` and `Remus`.

{{% /notice %}}

If I wanted to add another pet to the list, I could do so using `.append()`.

Add the following to `lists.py`:

```diff
# lists.py

pets = ['Chili', 'Ivy', 'Remus', 'Enzo']
print(pets[0])
+pets.append('Rex')
+print(pets)
```

## Challenges

{{% notice note %}}

Create a new list of 6 items.
Print the first, third and fifth items.
Append two new items to the list.
Print the list so you can see the new items.

{{% /notice %}}

## Back to the game!

How did you get here?

-   [Myrtle](../../myrtle/)
-   [Birds](../../birds/)
-   [World](../../world/3_creating_obstacles_but_better)

p.s. Here are Chilli + Ivy, Remus and Enzo:

![](../../images/chilli_and_ivy.gif)
![](../../images/remus.jpg)
![](../../images/enzo.jpg)
