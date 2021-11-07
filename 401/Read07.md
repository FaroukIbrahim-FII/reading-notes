# Game of Greed 2

## Understanding Scope

![Scope](https://cdn-bobah.nitrocdn.com/mDxsknkPRwKnnzdIpDlNbqFeHfgHfCqS/assets/static/optimized/rev-2917142/wp-content/uploads/scope-400x267.jpg)

In programming, the scope of a name defines the area of a program in which you can unambiguously access that name, such as variables, functions, objects, and so on. A name will only be visible to and accessible by the code in its scope. Several programming languages take advantage of scope for avoiding name collisions and unpredictable behaviors. Most commonly, you’ll distinguish two general scopes:

1. Global scope: The names that you define in this scope are available to all your code.

2. Local scope: The names that you define in this scope are only available or visible to the code within the scope.

Scope came about because early programming languages (like BASIC) only had global names. With this kind of name, any part of the program could modify any variable at any time, so maintaining and debugging large programs could become a real nightmare. To work with global names, you’d need to keep all the code in mind at the same time to know what the value of a given name is at any time. This was an important side-effect of not having scopes.

### Names and Scopes in Python

Since Python is a dynamically-typed language, variables in Python come into existence when you first assign them a value. On the other hand, functions and classes are available after you define them using def or class, respectively. Finally, modules exist after you import them.

### Python Scope vs Namespace

In Python, the concept of scope is closely related to the concept of the namespace. As you’ve learned so far, a Python scope determines where in your program a name is visible. Python scopes are implemented as dictionaries that map names to objects. These dictionaries are commonly called namespaces. These are the concrete mechanisms that Python uses to store names. They’re stored in a special attribute called .__dict__.

## Using the LEGB Rule for Python Scope

![LEGB](https://files.realpython.com/media/Scope-in-Python---LEGB-Rule_Watermarked.e5f68e7a3642.jpg)

Python resolves names using the so-called LEGB rule, which is named after the Python scope for names. The letters in LEGB stand for Local, Enclosing, Global, and Built-in. Here’s a quick overview of what these terms mean:

* Local (or function) scope is the code block or body of any Python function or lambda expression. This Python scope contains the names that you define inside the function. These names will only be visible from the code of the function. It’s created at function call, not at function definition, so you’ll have as many different local scopes as function calls. This is true even if you call the same function multiple times, or recursively. Each call will result in a new local scope being created.

* Enclosing (or nonlocal) scope is a special scope that only exists for nested functions. If the local scope is an inner or nested function, then the enclosing scope is the scope of the outer or enclosing function. This scope contains the names that you define in the enclosing function. The names in the enclosing scope are visible from the code of the inner and enclosing functions.

* Global (or module) scope is the top-most scope in a Python program, script, or module. This Python scope contains all of the names that you define at the top level of a program or a module. Names in this Python scope are visible from everywhere in your code.

* Built-in scope is a special Python scope that’s created or loaded whenever you run a script or open an interactive session. This scope contains names such as keywords, functions, exceptions, and other attributes that are built into Python. Names in this Python scope are also available from everywhere in your code. It’s automatically loaded by Python when you run a program or script.

### Functions: The Local Scope

The local scope or function scope is a Python scope created at function calls. Every time you call a function, you’re also creating a new local scope. On the other hand, you can think of each def statement and lambda expression as a blueprint for new local scopes. These local scopes will come into existence whenever you call the function at hand.

### Nested Functions: The Enclosing Scope

Enclosing or nonlocal scope is observed when you nest functions inside other functions. The enclosing scope was added in Python 2.2. It takes the form of the local scope of any enclosing function’s local scopes. Names that you define in the enclosing Python scope are commonly known as nonlocal names.

### Modules: The Global Scope

From the moment you start a Python program, you’re in the global Python scope. Internally, Python turns your program’s main script into a module called __main__ to hold the main program’s execution. The namespace of this module is the main global scope of your program.

### builtins: The Built-In Scope

The built-in scope is a special Python scope that’s implemented as a standard library module named builtins in Python 3.x. All of Python’s built-in objects live in this module. They’re automatically loaded to the built-in scope when you run the Python interpreter. Python searches builtins last in its LEGB lookup, so you get all the names it defines for free. This means that you can use them without importing any module.

## Modifying the Behavior of a Python Scope

So far, you’ve learned how a Python scope works and how they restrict the visibility of variables, functions, classes, and other Python objects to certain portions of your code. You now know that you can access or reference global names from any place in your code, but they can be modified or updated from within the global Python scope.

You also know that you can access local names only from inside the local Python scope they were created in or from inside a nested function, but you can’t access them from the global Python scope or from other local scopes. Additionally, you’ve learned that nonlocal names can be accessed from inside nested functions, but they can’t be modified or updated from there.

### The global Statement

You already know that when you try to assign a value to a global name inside a function, you create a new local name in the function scope. To modify this behavior, you can use a global statement. With this statement, you can define a list of names that are going to be treated as global names.

### The nonlocal Statement

Similarly to global names, nonlocal names can be accessed from inner functions, but not assigned or updated. If you want to modify them, then you need to use a nonlocal statement. With a nonlocal statement, you can define a list of names that are going to be treated as nonlocal.

## Using Enclosing Scopes as Closures

![Enclosing](https://cdn.educba.com/academy/wp-content/uploads/2019/11/scope-in-python.png)

Closures are a special use case of the enclosing Python scope. When you handle a nested function as data, the statements that make up that function are packaged together with the environment in which they execute. The resulting object is known as a closure. In other words, a closure is an inner or nested function that carries information about its enclosing scope, even though this scope has completed its execution.

## Bringing Names to Scope With import

When you write a Python program, you typically organize the code into several modules. For your program to work, you’ll need to bring the names in those separate modules to your __main__ module. To do that, you need to import the modules or the names explicitly. This is the only way you can use those names in your main global Python scope.

## Discovering Unusual Python Scopes

You’ll find some Python structures where name resolution seems not to fit into the LEGB rule for Python scopes. These structures include:

* Comprehensions
* Exception blocks
* Classes and instances

### Comprehension Variables Scope

The first structure you’ll cover is the comprehension. A comprehension is a compact way to process all or part of the elements in a collection or sequence. You can use comprehensions to create lists, dictionaries, and sets.

Comprehensions consist of a pair of brackets ([]) or curly braces ({}) containing an expression, followed by one or more for clauses and then zero or one if clause per for clause.

### Exception Variables Scope

Another atypical case of Python scope that you’ll encounter is the case of the exception variable. The exception variable is a variable that holds a reference to the exception raised by a try statement. In Python 3.x, such variables are local to the except block and are forgotten when the block ends.

### Class and Instance Attributes Scope

When you define a class, you’re creating a new local Python scope. The names assigned at the top level of the class live in this local scope. The names that you assigned inside a class statement don’t clash with names elsewhere. You can say that these names follow the LEGB rule, where the class block represents the L level.

In general, when you’re writing object-oriented code in Python and you try to access an attribute, your program takes the following steps:

1. Check the instance local scope or namespace first.
2. If the attribute is not found there, then check the class local scope or namespace.
3. If the name doesn’t exist in the class namespace either, then you’ll get an AttributeError.

## Using Scope Related Built-In Functions

![Built-in](data:image/jpeg;base64,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)

There are many built-in functions that are closely related to the concept of Python scope and namespaces. In previous sections, you’ve used dir() to get information on the names that exist in a given scope. Besides dir(), there are some other built-in functions that can help you out when you’re trying to get information about a Python scope or namespace. In this section, you’ll cover how to work with:

* globals()
* locals()
* dir()
* vars()

### globals()

In Python, globals() is a built-in function that returns a reference to the current global scope or namespace dictionary. This dictionary always stores the names of the current module. This means that if you call globals() in a given module, then you’ll get a dictionary containing all the names that you’ve defined in that module, right before the call to globals().

### locals()

Another function related to Python scope and namespaces is locals(). This function updates and returns a dictionary that holds a copy of the current state of the local Python scope or namespace. When you call locals() in a function block, you get all the names assigned in the local or function scope up to the point where you call locals().

### vars()

vars() is a Python built-in function that returns the .__dict__ attribute of a module, class, instance, or any other object which has a dictionary attribute. Remember that .__dict__ is a special dictionary that Python uses to implement namespaces.

### dir()

You can use dir() without arguments to get the list of names in the current Python scope. If you call dir() with an argument, then the function attempts to return a list of valid attributes.
