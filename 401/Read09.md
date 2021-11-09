# Game of Greed 4

## Enriching Your Python Classes With Dunder (Magic, Special) Methods

### What Are Dunder Methods?

![dunder](https://miro.medium.com/max/1400/1*7eglYMfJEwMo4qbil2O28g.png)

In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example __init__ or __str__.

As it quickly became tiresome to say under-under-method-under-under Pythonistas adopted the term “dunder methods”, a short form of “double under.”

These “dunders” or “special methods” in Python are also sometimes called “magic methods.” But using this terminology can make them seem more complicated than they really are—at the end of the day there’s nothing “magical” about them. You should treat these methods like a normal language feature.

    class NoLenSupport:
        pass

    >>> obj = NoLenSupport()
    >>> len(obj)
    TypeError: "object of type 'NoLenSupport' has no len()"

    To fix this, you can add a __len__ dunder method to your class:

    class LenSupport:
        def __len__(self):
            return 42

    >>> obj = LenSupport()
    >>> len(obj)
    42

### Special Methods and the Python Data Model

![data](https://www.researchgate.net/profile/Sam-Neymotin/publication/328726676/figure/fig2/AS:689044627410944@1541292449226/Instantiated-network-example-showing-hierarchical-data-model-The-instantiated-network-is.ppm)

This elegant design is known as the Python data model and lets developers tap into rich language features like sequences, iteration, operator overloading, attribute access, etc.

You can see Python’s data model as a powerful API you can interface with by implementing one or more dunder methods. If you want to write more Pythonic code, knowing how and when to use dunder methods is an important step.

### Enriching a Simple Account Class

Throughout this article I will enrich a simple Python class with various dunder methods to unlock the following language features:

* Initialization of new objects
* Object representation
* Enable iteration
* Operator overloading (comparison)
* Operator overloading (addition)
* Method invocation
* Context manager support (with statement)

### Object Initialization: `__init__`

Right upon starting my class I already need a special method. To construct account objects from the Account class I need a constructor which in Python is the `__init__` dunder:

    class Account:
        """A simple account class"""

        def __init__(self, owner, amount=0):
            """
            This is the constructor that lets us create
            objects from this class
            """
            self.owner = owner
            self.amount = amount
            self._transactions = []

### Object Representation: `__str__, __repr__`

It’s common practice in Python to provide a string representation of your object for the consumer of your class (a bit like API documentation.) 

    class Account:
        # ... (see above)

        def __repr__(self):
            return 'Account({!r}, {!r})'.format(self.owner, self.amount)

        def __str__(self):
            return 'Account of {} with starting amount: {}'.format(
                self.owner, self.amount)

### Iteration: `__len__, __getitem__, __reversed__`

In order to iterate over our account object I need to add some transactions. So first, I’ll define a simple method to add transactions.

    def add_transaction(self, amount):
        if not isinstance(amount, int):
            raise ValueError('please use int for amount')
        self._transactions.append(amount)

### Operator Overloading for Comparing Accounts: `__eq__, __lt__`

    >>> 2 > 1
    True

    >>> 'a' > 'b'
    False

Context Manager Support and the With Statement: __enter__, __exit__

My final example in this tutorial is about a slightly more advanced concept in Python: Context managers and adding support for the with statement.

    class Account:
    # ... (see above)

    def __enter__(self):
        print('ENTER WITH: Making backup of transactions for rollback')
        self._copy_transactions = list(self._transactions)
        return self

    def __exit__(self, exc_type, exc_val, exc_tb):
        print('EXIT WITH:', end=' ')
        if exc_type:
            self._transactions = self._copy_transactions
            print('Rolling back to previous transactions')
            print('Transaction resulted in {} ({})'.format(
                exc_type.__name__, exc_val))
        else:
            print('Transaction OK')

## Basic Statistics in Python — Probability

![statiscs](https://miro.medium.com/max/640/1*hqSyzuqPknl_fAneNx39gA.jpeg)

### What is probability?

At the most basic level, probability seeks to answer the question, “What is the chance of an event happening?” An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur. The quintessential representation of probability is the humble coin toss. In a coin toss the only events that can happen are:

1. Flipping a heads
2. Flipping a tails

### From statistics to probability

Our data will be generated by flipping a coin 10 times and counting how many times we get heads. We will call a set of 10 coin tosses a trial. Our data point will be the number of heads we observe. We may not get the “ideal” 5 heads, but we won’t worry too much since one trial is only one data point. If we perform many, many trials, we expect the average number of heads over all of our trials to approach the 50%.

![coin](https://i.imgur.com/GtbawRt.jpg)

    import random
    def coin_trial():
    heads = 0
    for i in range(100):
    if random.random() <= 0.5:
    heads +=1
    return headsdef simulate(n):
    trials = [] for i in range(n):
    trials.append(coin_trial())
    return(sum(trials)/n)
    simulate(10)
    >>> 5.4
    simulate(100)
    >>> 4.83
    simulate(1000)
    >>> 5.055
    simulate(1000000)
    >>> 4.999781

###  The data and the distribution

Before we can tackle the question of “which wine is better than average,” we have to mind the nature of our data. Intuitively, we’d like to use the scores of the wines to compare groups, but there comes a problem: the scores usually fall in a range. How do we compare groups of scores between types of wines and know with some degree of certainty that one is better than the other? Enter the normal distribution.

![distribution](https://i.imgur.com/3vDS2Au.png)

###  Three Sigma Rule

The Three Sigma rule, also known as the empirical rule or 68-95-99.7 rule, is an expression of how many of our observations fall within a certain distance of the mean. Remember that the standard deviation (a.k.a. “sigma”) is the average distance an observation in the data set is from the mean. The Three Sigma rule dictates that given a normal distribution, 68% of your observations will fall between one standard deviation of the mean. 

![segma](https://i.imgur.com/Mt3RyE0.png)