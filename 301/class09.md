# functional programming

## functional programming

1. Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.

2. Given the same parameters, pure functions will always return the same result. We don’t need to think of situations when the same parameter has different results — because it will never happen.

3. The code’s definitely easier to test. We don’t need to mock anything.

4. When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.

5. This pure function will always have the same output, given the same input.

## Modules

1. A module is a plit of code that has a certain functionality in our application.

2. *require* allows us to use a functionality or module else where in our application.

3. We use `require`

4. We use `module.exports = the functionality that we want to be used out side its file`. Then we make `const var = require to the function we want`.
