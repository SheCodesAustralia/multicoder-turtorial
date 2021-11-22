---
title: Your First Python Program
weight: 2
---

Open the Python Exercises workspace.

Add the following to `variables.py`:

```python
# variables.py

print('Hello, world!')
```

To run the file, click the arrow next to the green `Run` button in the top left and select the `variables.py` file.

The output for the Python Exercises will appear as text in the console (i.e. the black screen in the bottom left).
You should see `Hello, world!` appear.

![](../../images/running-python-files.png)

Congratulations! You are now a Python developer!

![](../../images/congratulations.gif)

But what did we actually just do? We used a **print statement** to output something to the **console**.

## Variables

Sometimes we have some information that we'll want to use multiple times or modify later.
This is where **variables** come in handy.

Let's see this in action, add the following to `variables.py`:

```diff
# variables.py

print('Hello, World!')

+name = 'Myrtle'
+print(name)
```

We could also use multiple variables to build a sentence:

```diff
# variables.py

print('Hello, World!')

+greeting = 'Hello'
name = 'Myrtle'
-print(name)
+print(greeting + name)
```

{{% notice note %}}

Can you work out what to add to the print statement to get the following output: `Hello, Myrtle!`
i.e. include a comma, space and exclamation mark.

{{% /notice %}}

We can also use python to store numbers and perform calculations.

Add the following to `variables.py`:

```diff
# variables.py

print('Hello, World!')

greeting = 'Hello'
name = 'Myrtle'
print(greeting + name)

+num1 = 4
+num2 = 8
+result = num1 + num4
+print(result)
```

Try using variables to write solutions to the following challenges:

{{% notice note %}}

Use Python to find the solutions to the following equation: `89 - 54`

{{% /notice %}}

{{% notice note %}}

Use Python to find the solutions to the following equation: `3 * 29`

{{% /notice %}}

{{% notice note %}}

Use Python to find the solutions to the following equation: `459 / 6`

{{% /notice %}}
