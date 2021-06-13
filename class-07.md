## Python Scope & the LEGB Rule: Resolving Names in Your Code

The concept of scope rules how variables and names are looked up in your code. It determines the visibility of a variable within the code.
The scope of a name or variable depends on the place in your code where you create that variable. 
The Python scope concept is generally presented using a rule known as the LEGB rule.

The letters in the acronym LEGB stand for Local, Enclosing, Global, and Built-in scopes. 
This summarizes not only the Python scope levels but also the sequence of steps that Python follows when resolving names in a program.

In this tutorial, you’ll learn:

What scopes are and how they work in Python
Why it’s important to know about Python scope
What the LEGB rule is and how Python uses it to resolve names
How to modify the standard behavior of Python scope using global and nonlocal
What scope-related tools Python offers and how you can use them
With this knowledge at hand, you can take advantage of Python scopes to write more reliable and maintainable programs. Using Python scope will
help you avoid or minimize bugs related to name collision as well as bad use of global names across your programs.

You’ll get the most out of this tutorial if you’re familiar with intermediate Python concepts like classes, functions, inner functions, variables,
exceptions, comprehensions, built-in functions, and standard data structures.


Understanding Scope

In programming, the scope of a name defines the area of a program in which you can unambiguously access that name, 
such as variables, functions, objects, and so on. A name will only be visible to and accessible by the code in its scope. Several programming languages
take advantage of scope for avoiding name collisions and unpredictable behaviors. Most commonly, you’ll distinguish two general scopes:

Global scope: The names that you define in this scope are available to all your code.

Local scope: The names that you define in this scope are only available or visible to the code within the scope.

Scope came about because early programming languages (like BASIC) only had global names. With this kind of name,
any part of the program could modify any variable at any time, so maintaining and debugging large programs could become
a real nightmare. To work with global names, you’d need to keep all the code in mind at the same time to know what the value of a given name is at any time.
This was an important side-effect of not having scopes.

Some languages like Python use scope to avoid this kind of problem. When you use a language that implements scope,
there’s no way for you to access all the variables in a program at all locations in that program. In this case,
your ability to access a given name will depend on where you’ve defined that name.

Note: You’ll be using the term name to refer to the identifiers of variables, constants, functions, classes,
or any other object that can be assigned a name.

The names in your programs will have the scope of the block of code in which you define them. When you can access the value of a given name from someplace in your code,
you’ll say that the name is in scope. If you can’t access the name, then you’ll say that the name is out of scope.

Names and Scopes in Python
Since Python is a dynamically-typed language, variables in Python come into existence when you first assign them a value.
On the other hand, functions and classes are available after you define them using def or class, respectively. Finally, modules exist after you import them. As a summary,
you can create Python names through one of the following operations:

![image](https://user-images.githubusercontent.com/79086986/121821435-95cd6900-cca1-11eb-826a-c9a2aa4d274d.png)

All these operations create or, in the case of assignments, update new Python names because all of them assign a name to a variable, constant, function, class, instance, module, or other Python object.

Note: There’s an important difference between assignment operations and reference or access operations. When you reference a name, you’re just retrieving its content or value. When you assign a name, you’re either creating that name or modifying it.

Python uses the location of the name assignment or definition to associate it with a particular scope. In other words, where you assign or define a name in your code determines the scope or visibility of that name.

For example, if you assign a value to a name inside a function, then that name will have a local Python scope. In contrast, if you assign a value to a name outside of all functions—say, at the top level of a module—then that name will have a global Python scope.

Python Scope vs Namespace
In Python, the concept of scope is closely related to the concept of the namespace. As you’ve learned so far, a Python scope determines where in your program a name is visible. Python scopes are implemented as dictionaries that map names to objects. These dictionaries are commonly called namespaces. These are the concrete mechanisms that Python uses to store names. They’re stored in a special attribute called .__dict__.
