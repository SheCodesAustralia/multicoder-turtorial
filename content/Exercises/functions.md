---
title: Functions
---

Sometimes we have some code that we might want to run at multiple points in our program.
In this situation, we put that code into a **function**, which we can then **call** again and again.

## Example 1

For example, maybe we want to print the same greeting for many different people.
Lets' write a function to handle that.

Add the following to `functions.py`:

```python
# functions.py

def generate_greeting(name):
    print('Hello, ' + name)
```

What happens when you run your code?
Nothing (hopefully).

That's because the code inside our function does not run until we **call** the function.

Add the following to `functions.py`:

```diff
# functions.py

def generate_greeting(name):
    print('Hello, ' + name)

+generate_greeting('Myrtle')
```

Now when you run the code, you should see the print statement appear in the console.

But the point of writing a function is being able to reuse the code.
Let's try calling our function more than once, to handle greeting multiple names.

Add the following to `functions.py`:

```diff
# functions.py

def generate_greeting(name):
    print('Hello, ' + name)

generate_greeting('Myrtle')
+generate_greeting('Shelley')
+generate_greeting('Sheldon')
+generate_greeting('Enzo')
```

Now when you run the code, you should see multiple print statements appear in the console.

The names that we are **passing** to the function are called **parameters**.
When we **pass** `Enzo` to the function, it becomes the value of `name`, which we can then use in our function.

## Example 2

Let's see another example.

Maybe there is a equation that we want to reuse.
For example, let's write a function that converts temperatures given in fahrenheit to celsius.

Add the following to `functions.py`:

```python
# functions.py

def convert_f_to_c(temp_in_f):
    print(temp_in_f - 32) * (5/9)
```

{{% notice note %}}

Use this function to convert the following temperatures from fahrenheit to celsius: 32, 0, 350.

{{% /notice %}}

## Challenges

{{% notice note %}}

Write a function that converts a distance in meters to kilometers and prints the result.

{{% /notice %}}

{{% notice note %}}

Write a function that takes two numbers, adds them together and prints the result.

{{% /notice %}}

## Back to the game!

How did you get here?

-   [Myrtle](../../myrtle/3_myrtle_spins)
-   [Birds](../../birds/2_checkpoint_a)
-   [World](../../world/3_creating_obstacles_but_better)
