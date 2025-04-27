---
title: "Something I Learned About Python This Week"
date: 2025-04-27
layout: post
categories: [Python, Programming, Automation]
tags: [Gemini 1.5 Pro, Google AI Studio, JSON, CSV, Data Extraction]
---

# Something I Learned About Python This Week

I started building with Python by learning from online tutorials and hands-on projects. But my learning had gaps. Recently, while automating a script, I started to notice something I hadn’t realized about Python before: it’s not just object-oriented. Then, I looked it up!

If, like me, you learned Python mostly through tutorials and projects, you might have noticed that Python shares loops and other features with JavaScript. Why is this? Most programming languages need ways to repeat actions, like using loops, to make code more efficient. But here's what I didn't know—loops aren't only part of object-oriented programming (OOP). They're also used in procedural programming.

## What is Procedural Programming?

Procedural programming is a style where you write step-by-step instructions, using functions, variables, and loops to control the flow. It’s like following a recipe: do this, then that, in order. You can think of it as breaking down a task into a series of steps, where each step is clearly defined.

In Python, you can use procedural programming when you:
- Write scripts that process data (like cleaning and transforming datasets).
- Automate simple tasks, such as renaming files or sending emails.
- Run machine learning or AI pipelines step-by-step, where each stage follows the previous one.

### Example of Procedural Python

```python
import csv

# Define the function to load CSV
def load_csv(filename):
    rows = []
    with open(filename, mode='r') as file:
        csv_reader = csv.reader(file)
        for row in csv_reader:
            rows.append(row)
    return rows

# Example usage
filename = 'your_file.csv'
data = load_csv(filename)
print(data)
```

This is a basic example where we load a CSV file step by step: open the file, read it row by row, and store the data in a list. It’s simple and works great for smaller tasks that don’t require complex structures.

## But You've Probably Also Used Python as OOP

Python also supports Object-Oriented Programming (OOP), which is another way to write Python code. OOP organizes code into classes and objects. Each object can have attributes (data) and methods (functions) that operate on that data. You use OOP when you want to represent real-world entities or concepts that have attributes and behaviors.

### Example of OOP in Python

```python
class Greeter:
    def __init__(self, name):
        self.name = name

    def greet(self):
        print(f"Hello, {self.name}!")

greeter = Greeter("Ashley")
greeter.greet()
```

This is an example of Python’s OOP capabilities. The `Greeter` class encapsulates a name attribute and a method to print a greeting. When you create an instance of `Greeter`, you are defining a particular greeting behavior that you can reuse.

## Why Do We Hear So Much About Python as OOP and Not Procedural?

While Python can be used for both procedural and object-oriented programming, OOP is often emphasized in courses and tutorials because it helps structure larger, more complex projects. As projects grow, OOP becomes more useful because it allows you to break the project into manageable components (like classes for different parts of your app), which makes the code more modular and reusable.

However, procedural programming is still widely used, especially in smaller scripts, data manipulation tasks, and machine learning workflows. When working with data preprocessing or running a machine learning pipeline step-by-step, procedural Python is often the simpler and more efficient approach.

## When to Use Procedural vs. OOP in Python

### Use Procedural Programming When:
- You have simple scripts that need to perform linear tasks (e.g., file manipulation, simple data cleaning).
- You’re building quick automation tasks, such as renaming files or sending emails.
- You’re working with data processing pipelines, like reading and transforming CSV files, without needing to manage complex entities.

### Use OOP When:
- You need to model real-world entities or complex systems, such as a banking system with customers, accounts, and transactions.
- You want code reuse and modularity—where multiple components (e.g., user management, authentication) interact but remain separate and manageable.
- Your application needs extensibility and the ability to add new features easily, such as adding new shapes to a graphics editor.

## Summary

Python’s versatility allows you to use it in both procedural and object-oriented ways. Procedural programming is great for small, linear tasks like automating file management or cleaning data. On the other hand, OOP shines when you need to model more complex systems or when you need to maintain, extend, and reuse your codebase as your projects grow.

By understanding both approaches, you can choose the right one based on the complexity of the task at hand. Whether you’re writing a quick script or building a large application, Python has the tools to help you do it efficiently!

Have you used Python procedurally or with OOP? Share your experiences in the comments!

**Note**: I am now going to try enabling comments in my GitHub blog using Utterances!
