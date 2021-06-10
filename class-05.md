## Linked Lists
What is a Linked List
A Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.

There are two types of Linked List - Singly and Doubly. We will be implementing a Singly Linked List in this implementation.

Terminology:
Linked List - A data structure that contains nodes that links/points to the next node in the list.
Singly - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.
Doubly - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.
Node - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.
Next - Each node contains a property called Next. This property contains the reference to the next node.
Head - The Head is a reference of type Node to the first node in a linked list.
Current - The Current is a reference of type Node to the node that is currently being looked at. When traversing, you create a new Current variable at the Head to guarantee you are starting from the beginning of the linked list.
What does it look like
This is what a Singly Linked List looks like

Singly Linked List

![image](https://user-images.githubusercontent.com/79086986/121452216-b8ad0400-c9a7-11eb-87a0-11586b275769.png)


Traversal
When traversing a linked list, you are not able to use a foreach or for loop. We depend on the Next value in each node to guide us where the next reference is pointing. The Next property is exceptionally important because it will lead us where the next node is and allow us to extract the data appropriately.

The best way to approach a traversal is through the use of a while() loop. This allows us to continually check that the Next node in the list is not null. If we accidentally end up trying to traverse on a node that is null, a NullReferenceException gets thrown and our program will crash/end.

When traversing through a linked list, the Current variable will tell us where exactly in the linked list we are and will allow us to move/traverse forward until we hit the end.

Traversal Example
Let’s put a use case on our traversal. We want to check whether or not our LinkedList Includes a specific value.

The pseudo-code for an Includes is as so:

```
ALGORITHM Includes (value)
// INPUT <-- integer value
// OUTPUT <-- boolean

  Current <-- Head

  WHILE Current is not NULL
    IF Current.Value is equal to value
      return TRUE

    Current <-- Current.Next

  return FALSE
```

Let’s talk out what exactly is happening:

We are first creating Current at the Head to guarantee we are starting from the beginning. (Remember that Head is always the first node in a Linked List)

We create a while loop. This loop will only run if the node that Current is pointing to is not null.
This also means we can guarantee that we are still looking at a Node while the loop is running.

Once we are in the while loop, we are checking if the value of the current node is equal to the value we are looking for. Given the logic,
if that condition is true, then we have found the value we were looking for, so we return true.

If the Current node does not contain the value we are looking for, we then must move Current to the next node that is being referenced. Again,
because the condition of this while loop is to only run if we are still at a node,
we can safely traverse to the next node without fear of getting a NullReferenceException.

At this point, the while loop is re-evaluated. Step 3 & 4 will continue until Current reaches the end of the LinkedList.
We will know we are at the last node in the linked list because the current node will be null. Once this condition becomes true,
the while loop breaks, and we now know that we are at the end.

Once we hit the end, we know that we did not find the value and return true at any point, so the value is not in the LinkedList. We return false.

Traversal Big O

The Big O of time for Includes would be O(n). This is because, at its worse case, the node we are looking for will be the very last node in the linked list. n represents the number of nodes in the linked list.

The Big O of space for Includes would be O(1). This is because there is no additional space being used than what is already given to us with the linked list input.

Adding a Node

Adding O(1)
Order of operations is extremely important when it comes to working with a Linked List. 
What I mean by this is you must be careful that all references to each link/node is properly assigned.

An example can be with adding a node to a linked list. If we want to add a node with an O(1) efficiency,
we have to replace the current Head of the linked list with the new node, without losing the reference to the next node in the list.

Here are the required steps to add a new node with an O(1) efficiency.

We can then instantiate the new node that we are adding. The values passed in as arguments into the Add() method will define what the value of the Node will be.

![image](https://user-images.githubusercontent.com/79086986/121452487-29542080-c9a8-11eb-935f-757273879f50.png)


Singly Linked List

newNode.Next by default is set to null. We want to set newNode.Next property to the same location that the Head node is pointing towards. 
Because Head is just a reference type, we will be assigning it to the same allocation in memory as the node it is pointing too. In this case, it’s Node1.

![image](https://user-images.githubusercontent.com/79086986/121452463-235e3f80-c9a8-11eb-8dc8-e045acab8dba.png)


Singly Linked List

At this point in the program we now “technically” have newNode at the beginning of the linked list, 
but we are not done yet. We now have to re-assign where Head is pointing too. Since Node1 is no longer the first node in the list, we want to re-assign Head to point at newNode.

![image](https://user-images.githubusercontent.com/79086986/121452453-1c373180-c9a8-11eb-925c-a3f836968638.png)


Singly Linked List

Add Code
Here is the Pseudo code for an Add method on a Linked list

```
ALGORITHM Add(newValue)
// INPUT <-- Value to add
// OUTPUT <-- No output

  newNode <-- NEW Node
  newNode.Value <-- newValue
  newNode.Next <-- Head
  Head <-- newNode
```

## What’s a Linked List, Anyway?

Information is all around us.
In the world of software, the ways that we choose to organize our information is half the battle. Here’s the thing though: there are so many ways to solve a problem. And when it comes to organizing our data, there are lots of tools that could work for the job. The trick is knowing which tool is the right one to use.
Regardless of which language we start coding in, one of the first things that we encounter are data structures, which are the different ways that we can organize our data; variables, arrays, hashes, and objects are all types of data structures. But these are still just the tip of the iceberg when it comes to data structures; there are a lot more, some of which start to sound super complicated the more that you hear about them.
One of those complicated things for me has always been linked lists. I’ve known about linked lists for a few years now, but I can never quite keep them straight in my head. I only really think about them when I’m preparing for (or sometimes, in the middle of) a technical interview, and someone asks me about them. I’ll do a little research and think that I understand what they’re about, but after a few weeks, I forget them again. The whole thing is pretty inefficient, and it all stems from the fact that I know they exist, but I don’t fundamentally understand them! So, it’s time to change that and answer the question: what on earth is a linked list, anyway?
Linear data structures
If we really want to understand the basics of linked lists, it’s important that we talk about what type of data structure they are.
One characteristic of linked lists is that they are linear data structures, which means that there is a sequence and an order to how they are constructed and traversed. We can think of a linear data structure like a game of hopscotch: in order to get to the end of the list, we have to go through all of the items in the list in order, or sequentially. Linear structures, however, are the opposite of non-linear structures. In non-linear data structures, items don’t have to be arranged in order, which means that we could traverse the data structure non-sequentially.

Linear versus non-linear data structures
We might not always realize it, but we all work with linear and non-linear data structures everyday! When we organize our data into hashes (sometimes called dictionaries), we’re implementing a non-linear data structure. Trees and graphs are also non-linear data structures that we traverse in different ways, but we’ll talk more about them in more depth later in the year.
Similarly, when we use arrays in our code, we’re implementing a linear data structure! It can be helpful to think of arrays and linked lists as being similar in the way that we sequence data. In both of these structures, order matters. But what makes arrays and linked lists different?
Memory management
The biggest differentiator between arrays and linked lists is the way that they use memory in our machines. Those of us who work with dynamically typed languages like Ruby, JavaScript, or Python don’t have to think about how much memory an array uses when we write our code on a day to day basis because there are several layers of abstraction that end up with us not having to worry about memory allocation at all.
But that doesn’t mean that memory allocation isn’t happening! Abstraction isn’t magic, it’s just the simplicity of hiding away things that you don’t need to see or deal with all of the time. Even if we don’t have to think about memory allocation when we write code, if we want to truly understand what’s going on in a linked list and what makes it powerful, we have to get down to the rudimentary level.
We’ve already learned about binary and how data can be broken up into bits and bytes. Just as characters, numbers, words, sentences require bytes of memory to represent them, so do data structures.
When an array is created, it needs a certain amount of memory. If we had 7 letters that we needed to store in an array, we would need 7 bytes of memory to represent that array. But, we’d need all of that memory in one contiguous block. That is to say, our computer would need to locate 7 bytes of memory that was free, one byte next to the another, all together, in one place.
On the other hand, when a linked list is born, it doesn’t need 7 bytes of memory all in one place. One byte could live somewhere, while the next byte could be stored in another place in memory altogether! Linked lists don’t need to take up a single block of memory; instead, the memory that they use can be scattered throughout.

Memory allocation in static versus dynamic data structures
The fundamental difference between arrays and linked lists is that arrays are static data structures, while linked lists are dynamic data structures. A static data structure needs all of its resources to be allocated when the structure is created; this means that even if the structure was to grow or shrink in size and elements were to be added or removed, it still always needs a given size and amount of memory. If more elements needed to be added to a static data structure and it didn’t have enough memory, you’d need to copy the data of that array, for example, and recreate it with more memory, so that you could add elements to it.
On the other hand, a dynamic data structure can shrink and grow in memory. It doesn’t need a set amount of memory to be allocated in order to exist, and its size and shape can change, and the amount of memory it needs can change as well.
By now, we can already begin to see some major differences between arrays and linked lists. But this begs the question: what allows a linked list to have its memory scattered everywhere? To answer this question, we need to look at the way that a linked list is structured.
Parts of a linked list
A linked list can be small or huge, but no matter the size, the parts that make it up are actually fairly simple. A linked list is made up of a series of nodes, which are the elements of the list.
The starting point of the list is a reference to the first node, which is referred to as the head. Nearly all linked lists must have a head, because this is effectively the only entry point to the list and all of its elements, and without it, you wouldn’t know where to start! The end of the list isn’t a node, but rather a node that points to null, or an empty value.

