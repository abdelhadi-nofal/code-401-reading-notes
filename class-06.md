## How to use the Random Module in Python

Overview
In this post, I would like to describe the usage of the random module in Python. The random module provides access to functions that support many operations. 
Perhaps the most important thing is that it allows you to generate random numbers.

When to use it?
We want the computer to pick a random number in a given range Pick a random element from a list,
pick a random card from a deck, flip a coin etc. When making your password database more secure or powering a random page feature of your website.


Random functions
The Random module contains some very useful functions.

Randint
If we wanted a random integer, we can use the randint function Randint accepts two parameters:
a lowest and a highest number. Generate integers between 1,5. The first value should be less than the second.

```
import random
print random.randint(0, 5)
This will output either 1, 2, 3, 4 or 5.
````


Random
If you want a larger number, you can multiply it.


For example, a random number between 0 and 100:


```
import random
random.random() * 100'

```


Choice
Generate a random value from the sequence sequence.


random.choice( ['red', 'black', 'green'] ).
The choice function can often be used for choosing a random element from a list.

```
import random
myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
random.choice(myList)

````


Shuffle
The shuffle function, shuffles the elements in list in place, so they are in a random order.

andom.shuffle(list) Example taken from this post on Stackoverflow

```
from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)
Output:
# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
# of course your results will vary
```

Randrange
Generate a randomly selected element from range(start, stop, step)

```
random.randrange(start, stop[, step])
import random
for i in range(3):
    print random.randrange(0, 101, 5)
    
```

## What is Risk Analysis in Software Testing and how to perform it?

Why use Risk Analysis?
In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.

risk analysis - Risk Analysis in Software Testing- edureka

 

Now, you might think what could be the possible risks that you could encounter? Well here is a list:

Use of new hardware
Use of new technology
Use of new automation tool
The sequence of code
Availability of test resources for the application
Now, you must know there are certain risks that are unavoidable. I am enumerating them below:

The time that you allocated for testing

A defect leakage due to the complexity or size of the application

Urgency from the clients to deliver the project

Incomplete requirements

In such cases, you have to tackle the situation with care. Following points can be taken care of:

Conduct Risk Assessment review meeting

Use maximum resources to work on high-risk areas

Create a Risk Assessment database for future use

Identify and notice the risk magnitude indicators: high, medium, low.

Now, what are these risk magnitude indicators? Well, here is an explanation.

High: means the effect of the risk would be very high and non-tolerable. The company might face loss.

Medium: it is tolerable but not desirable. The company may suffer financially but there is a limited risk.

Low: it is tolerable. There lies little or no external exposure or no financial loss.

Moving on! Our next topic queued is as follows:

Risk Identification
There are different sets of risks included in the risk identification process. Those are as follows:

Business Risks: This risk is the most common risk associated with our topic. It is the risk that may come from your company or your customer, not from your project.

Testing Risks: You should be well acquainted with the platform you are working on, along with the software testing tools being used.

Premature Release Risk: a fair amount of knowledge to analyze the risk associated with releasing unsatisfactory or untested software is required

Software Risks: You should be well versed with the risks associated with the software development process.

After identifying the risks associated with your software, the next step is to assess the risks; i.e, Risk Assessment.

Risk Assessment
In the risk analysis process, these steps prove to be the most important one. It is said that this step is way too complex and should be tackled with the utmost care. After risk identification, assessment has to be dealt programmatically. There are a few perspectives on risk assessment. Read on!

risk assessment - risk analysis in software testing - edureka

Moving on! Our next topic on Risk Analysis in Software Testing

The perspective of Risk Assessment
There are three perspectives of Risk Assessment:

Effect

Cause

Likelihood

Effect – To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact.

Cause – To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.

Likelihood – To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.

Now, heading forward, the question that would be hovering over your mind is, how actually shall we perform risk analysis? Well, here is your solution!

How to perform Risk Analysis?
There are three steps:

Searching the risk

Analyzing the impact of each individual risk

Measures for the risk identified

With this I have reached towards the end of this blog, I hope that the content explained added value to your Java knowledge. We will keep exploring the Java world together. Stay tuned!

Now that you have understood testing, check out the Software Testing Fundamentals Course by Edureka, a trusted online learning company with a network of more than 250,000 satisfied learners spread across the globe. This course is designed to introduce you to the complete software testing life-cycle. You will be learning different levels of testing, test environment setup, test case design technique, test data creation, test execution, bug reporting, CI/CD pipeline in DevOps, and other essential concepts of software testing. Got a question for us? Please mention it in the comments section of “What is Software Testing” and we will get back to you.

Got a question for us? Please mention it in the comments section of this “Risk Analysis in Software Testing” blog and we will get back to you as soon as possible.

