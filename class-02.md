## In Tests We Trust — TDD with Python


### The freela

Imagine that a client has a website and through it he receives a lot of contacts from potential customers. After a while he realized that it is important for the business to identify the profile of consumer: age, gender, job and so on. But the website just receive the name and the email.
They hired you to identify the gender of a person based on his/her name. Luckily, there is an amazing API called Genderize.io that identifies the possible genders. And you quickly developed your API connection:
requests.get('https://api.genderize.io/?name=ana')
However the client demands you to write unit tests and you are curious about TDD. Here our journey begins!
Baby Steps
The API is pretty straightforward and your work was almost done. But with TDD we need to think about tests first. And to be ok with the possibility of the beginning to be hard sometimes — and it’s totally fine. Really.
Coming back to the code and thinking with baby steps, what is the smaller test that we can do against a function (method/class) that will return the gender?
Time for you to think
Just recaping: we have a name as input and we need to return a gender as output. So, the smaller test is: given a name, return a gender.

Input: Ana [name]
Output: female [gender]

Important aspects about the unit test
Let’s write our first test!
def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’
There are some details to pay attention. The first one is the test name. The tests can be considered as your alive documentation. We need to be descriptive about it and to say what is expected and what we are testing. In this case we explicitly said:
should return female when the name is from a female.
The test file name should follow the same name of module name. For instance,
if our module is gender.py, our test name should be test_gender.py.
It’s ideal to separate the tests folder from production code (the implementation) and to have something like this:

`
mymodule/
 — module.py
 — another_folder/
 — — another_module.py
tests/
 — test_module.py
 — another_folder/
 — — test_another_module.py`
 
 
Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.
Arrange: you need to organize the data needed to execute that piece of code (input);
Act: here you will execute the code being tested (exercise the behaviour);
Assert: after executing the code, you will check if the result (output) is the same as you were expecting.
Now you can execute the tests. I suggest the lib pytest to do it. But you are free to choose anything you like.
Yay! We have our first test. It’s beautiful but it fails. And that is awesome!


### The Cycle


I hope at this time you didn’t give up of this text because this is an example of an important thing about TDD: the cycle.
The cycle is made by three steps:
🆘 Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostbusters, really)
✅ Write the feature and make the test pass! (you can dance after that)
🔵 Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy)
Using baby steps you can go through this cycle every time you add or modify a new feature in your code.
And talking about feature… let’s do the cycle!
We made our test fail. Awesome! Now it’s time to implement the feature. Thinking with baby steps,
our implementation should follow the same rule, ok? So, what is needed to make this test pass? Don’t think about the whole feature, just about the test.

### Time for you to think
We just need to write the method that returns the right answer: FEMALE!
`
def run(self, name):
    return 'female'`
    
### TDD is not about the money/tests

More than any checking, we need to think about our software design first.
One of the things that amaze me about TDD is how we can grow our software design consciously and well, just building what is needed to make the test pass. When we are writing tests we are forced to think about the design first and how we can break it into small pieces.
Let’s write one more test. Besides female names, we need to identify male names as well.
def test_should_return_male_when_the_name_is_from_male_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Pedro’)
    assert expected_gender == ‘male’
But when we run it will fail because we just return female, right? Let’s fix it using our real code.
`import requests

def run(self, name):
    result = requests.get('https://api.genderize.io/?name{}'
.format(name))
    return result['gender']
Now our tests are passing! Yay! `

![image](https://user-images.githubusercontent.com/79086986/120941726-e9353980-c72c-11eb-9603-e7333c120ecb.png)

### Takeaways

I hope this was fun for you! To remember:
The greatest advantage about TDD is to craft the software design first
Your code will be more reliable: after a change you can run your tests and be in peace
Beginning may be hard — and that’s fine. You just need to practice!
Two books to dive into TDD:
Test Driven Development: By Example
Growing Object-Oriented Software, Guided by Tests
Have fun!

