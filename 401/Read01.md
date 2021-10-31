# Big O

Big O notation is used in Computer Science to describe the performance or complexity of an algorithm. Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used (e.g. in memory or on disk) by an algorithm.

## O(1)

**O(1)** describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.

## O(N)

**O(N)** describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set. The example below also demonstrates how Big O favours the worst-case performance scenario; a matching string could be found during any iteration of the for loop and the function would return early

## O(N²)

**O(N²)** represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set. Deeper nested iterations will result in O(N³), O(N⁴) etc.

## O(2^N)

**O(2^N)** denotes an algorithm whose growth doubles with each addition to the input data set. The growth curve of an O(2^N) function is exponential — starting off very shallow, then rising meteorically.

## Logarithms

**Logarithms** are slightly trickier to explain so I’ll use a common example:

Binary search is a technique used to search sorted data sets. It works by selecting the middle element of the data set, essentially the median, and compares it against a target value.

# The Python Environment
## The Interpreter
Let’s get started with the most important thing when working with python: the interpreter. For sure you could just simply download and install your favorite version of python and put everything into that.
Pyenv is a set of three tools, from which I present two here, that are pyenv (used to install python) and pyenv-virtualenv (used to configure your global tools)
After that, add the following lines to your .bashrc (same for .zshrc) to have pyenv available in your terminal
export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
and finally, restart your terminal. Now, you can use pyenv to install almost any python interpreter, including pypy, and anaconda. Note, that pyenv builds python locally on your machine.

## Dependency Management
Managing project dependencies in python can become messy or manual. There exists a bunch of tools to help you with that.

## Type-Correctness
Since Python 3.5, please correct me if I am wrong, type annotations are part of the standard library.

## Automate the Automation
With black and mypy we can avoid formatting code manually or run into avoidable errors. But, we still have to execute those tools manually. Shouldn’t that be automated too? Yes!
Pre-commit is all you need.
