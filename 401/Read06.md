# Game of Greed 1

## How to use the Random Module in Python

![random](https://linuxhint.com/wp-content/uploads/2020/10/word-image-707.png)

### When to use it?

We want the computer to pick a random number in a given range Pick a random element from a list, pick a random card from a deck, flip a coin etc. When making your password database more secure or powering a random page feature of your website.

#### Random functions

The Random module contains some very useful functions.
Randint

If we wanted a random integer, we can use the randint function Randint accepts two parameters: a lowest and a highest number. Generate integers between 1,5. The first value should be less than the second.

#### import random

print random.randint(0, 5)

This will output either 1, 2, 3, 4 or 5.
Random

If you want a larger number, you can multiply it.

For example, a random number between 0 and 100:

import random
random.random() * 100

#### Choice

Generate a random value from the sequence sequence.

random.choice( ['red', 'black', 'green'] ).

The choice function can often be used for choosing a random element from a list.

import random
myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
random.choice(myList)

#### Shuffle

The shuffle function, shuffles the elements in list in place, so they are in a random order.

random.shuffle(list) Example taken from this post on Stackoverflow

from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)

#### Output

`# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]`

of course your results will vary

Randrange

Generate a randomly selected element from range(start, stop, step)

random.randrange(start, stop[, step])

import random
for i in range(3):
    print random.randrange(0, 101, 5)

## Risk analysis

![risk](https://miro.medium.com/max/1400/1*HprJpsKvGVXsDYdVNnHlEA.jpeg)

Why use Risk Analysis?

In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks.

Now, you might think what could be the possible risks that you could encounter? Well here is a list:

1. Use of new hardware
2. Use of new technology
3. Use of new automation tool
4. The sequence of code
5. Availability of test resources for the application

In such cases, you have to tackle the situation with care. Following points can be taken care of:

* Conduct Risk Assessment review meeting

* Use maximum resources to work on high-risk areas

* Create a Risk Assessment database for future use

* Identify and notice the risk magnitude indicators: high, medium, low.

## TestCoverage

If you make a certain level of coverage a target, people will try to attain it. The trouble is that high coverage numbers are too easy to reach with low quality testing. At the most absurd level you have AssertionFreeTesting. But even without that you get lots of tests looking for things that rarely go wrong distracting you from testing the things that really matter.

Like most aspects of programming, testing requires thoughtfulness. TDD is a very useful, but certainly not sufficient, tool to help you get good tests. If you are testing thoughtfully and well, I would expect a coverage percentage in the upper 80s or 90s. I would be suspicious of anything like 100% - it would smell of someone writing tests to make the coverage numbers happy, but not thinking about what they are doing.

![test](https://lh3.googleusercontent.com/proxy/VOBiv6xi311zD46ipNAjuoSu7c0t0oc9yzw9XrUtnjKI-85PZ6JqbHMr1O4rlUF8KWR7oeqnmQ1FGeetwzP4wxP7wfSiYAF5mZcjCuYnEZGzz3VNWXVBUOg)