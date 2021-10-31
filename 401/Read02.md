# TDD With Python

![TDD](https://python-tdd.readthedocs.io/en/latest/_images/tdd.png)

## Unit Tests

Unit tests are some pieces of code to exercise the input, the output and the behaviour of your code. You can write them anytime you want.

But Test-Driven Development is a strategy to think (and write!) tests first.

Let me explain it better — with an example (finally the code!).

## The freela

Imagine that a client has a website and through it he receives a lot of contacts from potential customers. After a while he realized that it is important for the business to identify the profile of consumer: age, gender, job and so on. But the website just receive the name and the email.

They hired you to identify the gender of a person based on his/her name. Luckily, there is an amazing API called Genderize.io that identifies the possible genders. And you quickly developed your API connection:

requests.get('https://api.genderize.io/?name=ana')

However the client demands you to write unit tests and you are curious about TDD. Here our journey begins!

Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.

* Arrange: you need to organize the data needed to execute that piece of code (input);
* Act: here you will execute the code being tested (exercise the behaviour);
* Assert: after executing the code, you will check if the result (output) is the same as you were expecting.

Now you can execute the tests. I suggest the lib pytest to do it. But you are free to choose anything you like.

## The Cycle

The cycle is made by three steps:

* 🆘 Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostbusters, really)
* ✅ Write the feature and make the test pass! (you can dance after that)
* 🔵 Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy)

Using baby steps you can go through this cycle every time you add or modify a new feature in your code.

## What does the if __name__ == “__main__”: do?

![ifNameMain](https://kirankoduru.github.io/img/python-if-name-main.png)

f the python interpreter is running that module (the source file) as the main program, it sets the special __name__ variable to have a value “__main__”. If this file is being imported from another module, __name__ will be set to the module’s name. Module’s name is available as value to __name__ global variable.

A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended.

### Why Do we need it?

Advantages :

1. Every Python module has it’s __name__ defined and if this is ‘__main__’, it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.
2. If you import this script as a module in another script, the __name__ is set to the name of the script/module.
3. Python files can act as either reusable modules, or as standalone programs.
4. if __name__ == “main”: is used to execute some code only if the file was run directly, and not imported.

## Recursion

![recursion](https://www.edureka.co/blog/wp-content/uploads/2019/08/2019-08-06-12_31_29-Window.png)

What is Recursion?
The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function. Using recursive algorithm, certain problems can be solved quite easily. Examples of such problems are Towers of Hanoi (TOH), Inorder/Preorder/Postorder Tree Traversals, DFS of Graph, etc.

Let us consider a problem that a programmer have to determine the sum of first n natural numbers, there are several ways of doing that but the simplest approach is simply add the numbers starting from 1 to n. So the function simply looks like.

There is a simple difference between the approach (1) and approach(2) and that is in approach(2) the function “ f( ) ” itself is being called inside the function, so this phenomenon is named as recursion and the function containing recursion is called recursive function, at the end this is a great tool in the hand of the programmers to code some problems in a lot easier and efficient way.

### How a particular problem is solved using recursion?

The idea is to represent a problem in terms of one or more smaller problems, and add one or more base conditions that stop the recursion. For example, we compute factorial n if we know factorial of (n-1). The base case for factorial would be n = 0. We return 1 when n = 0.
