## Classes and Objects

Python Classes/Objects
Python is an object oriented programming language.

Almost everything in Python is an object, with its properties and methods.

A Class is like an object constructor, or a "blueprint" for creating objects.

The __init__() Function
The examples above are classes and objects in their simplest form, and are not really useful in real life applications.

To understand the meaning of classes we have to understand the built-in __init__() function.

All classes have a function called __init__(), which is always executed when the class is being initiated.

Use the __init__() function to assign values to object.


Object Methods
Objects can also contain methods. Methods in objects are functions that belong to the object.

The self Parameter
The self parameter is a reference to the current instance of the class, and is used to access variables that belongs to the class.

It does not have to be named self , you can call it whatever you like, but it has to be the first parameter of any function in the class

### Thinking Recursively in Python
![image](https://user-images.githubusercontent.com/79086986/121254829-67234d00-c8b3-11eb-8177-8aef9fac255c.png)

Problems (in life and also in computer science) can often seem big and scary. But if we keep chipping away at them, more often than not we can break them down into smaller chunks trivial enough to solve. This is the essence of thinking recursively, and my aim in this article is to provide you, my dear reader, with the conceptual tools necessary to approach problems from this recursive point of view.

Together, we’ll learn how to work with recursion in our Python programs by mastering concepts such as recursive functions and recursive data structures. We’ll also talk about maintaining state during recursion and avoiding recomputation by caching results. This is going to be a lot of fun. Onwards and upwards!

Dear Pythonic Santa Claus…
I realize that as fellow Pythonistas we are all consenting adults here, but children seem to grok the beauty of recursion better. So let’s not be adults here for a moment and talk about how we can use recursion to help Santa Claus.

Have you ever wondered how Christmas presents are delivered? I sure have, and I believe Santa Claus has a list of houses he loops through. He goes to a house, drops off the presents, eats the cookies and milk, and moves on to the next house on the list. Since this algorithm for delivering presents is based on an explicit loop construction, it is called an iterative algorithm.

