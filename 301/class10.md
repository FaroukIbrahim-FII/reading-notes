# In memory storage

## JavaScript Call Stack

1. The call stack is primarily used for function invocation (call).

2. Since the call stack is single, function(s) execution, is done, one at a time, from top to bottom. It means the call stack is synchronous.

3. LIFO: When we say that the call stack, operates by the data structure principle of Last In, First Out, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

4. `function firstFunction(){
   console.log("Hello from firstFunction");
   }

   function secondFunction(){
   firstFunction();
   console.log("The end from secondFunction");
   }

   secondFunction();`

5. A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

## JavaScript error messages

1. This is as simple as when you try to use a variable that is not yet declared you get this type os errors.

2. This occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

3. Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.

4. Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.

5. The breakpoint can also be achieved by putting a debugger statement in your code in the line you want to break.

6. debugger statement and when running the code above you can see the “history” before reaching that breakpoint. In this case it’s not a long call stack but you can start to see why it is useful, you know the function add was executed in line 14.