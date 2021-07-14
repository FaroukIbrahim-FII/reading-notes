# JS Debugging

## ORDER OF EXECUTION

To find the source of an error, it helps to know how scripts are processed. The order in which statements are executed can be complex; some tasks cannot complete until another statement or function has been run.

![debug](https://developer-chrome-com.imgix.net/image/admin/fgJB1mwfZsJ7Pv21hzSt.png?auto=format)

## The Stack

The JavaScript interpreter processes one line of code at a time. Whenm a statement needs data from another function, it stacks (or piles) the new function on top of the current task.

## EXECUTION CONTEXT & HOISTING

Each time a script enters a new execution context, there are two phases of activity:

1. PREPARE
   * The new scope is created
   * Variables, functions, and arguments are created
   * The value of the this keyword is determined.

2. EXECUTE
   * Now it can assign values to variables.
   * Reference functions and run their code.
   * Execute statements.

## UNDERSTANDING SCOPE

In the interpreter, each execution context has its own va ri ables object. It holds the variables, functions, and parameters available within it. Each execution context can also access its parent's variables object.

## UNDERSTANDING ERRORS

If a JavaScript statement generates an error, then it throws an exception. At that point, the interpreter stops and looks for exception-handling code.

## HOW TO DEAL WITH ERRORS

Now that you know what an error is and how the browser treats them, there are two things you can do with the errors.

1. DEBUG THE SCRIPT TO FIX ERRORS
If you come across an error while writing a script
(or when someone reports a bug), you will need to
debug the code, track down the source of the error,
and fix it.

2. HANDLE ERRORS GRACEFULLY
You can handle errors gracefully using try, catch, throw, and finally statements.

## A DEBUGGING WORKFLOW

Debugging is about deduction: eliminating potential causes of an error. Here is a workflow for techniques you will meet over the next 20 pages. Try to narrow down where the problem might be, then look for clues.

* WHERE IS THE PROBLEM?
First, should try to can narrow down the area where the problem seems to be. In a long script, this is especially important.

* WHAT EXACTLY IS THE PROBLEM?
Once you think that you might know the rough area in which your problem is located, you can then try to find the actual line of code that is causing the error.

## BROWSER DEV TOOLS & JAVASCRIPT CONSOLE

The JavaScript console will tell you when there is a problem with a script, where to look for the problem, and what kind of issue it seems to be.

## BREAKPOINTS

You can pause the execution of a script on any line using breakpoints. Then you can check the va lues stored in variables at that point in time.

## STEPPING THROUGH CODE

If you set multiple breakpoints, you can step through them one-by-one to see where values change and a problem might occur.

## DEBUGGING TIPS

Here are a selection of practical tips that you can try to use when debugging your scripts.

* ANOTHER BROWSER
* ADD NUMBERS
* STRIP IT BACK
* EXPLAINING THE CODE
* SEARCH
* CODE PLAYGROUNDS
* VALIDATION TOOLS

## COMMON ERRORS

Here is a list of common errors you might find with your scripts.

* GO BACK TO BASICS
* MISSED/ EXTRA CHARACTERS
* DATA TYPE ISSUES
