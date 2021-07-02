# Loops

We use Loops to perform an operation that would need so much time and code to be done otherwise in JavaScript

There are so many Loops to be used in JavaScript, however, we'll talk about **For Loop** and **While Loop**.

## For Loop:

A for loop repeats until a specified condition evaluates to false. The JavaScript for loop is similar to the Java and C for loop.

A for statement looks as follows:

> for ([initialExpression]; [conditionExpression]; [incrementExpression]) {statement}

![For Loop](https://www.toolsqa.com/wp-content/gallery/javascript/forin-statement.png)


## While Loop:

A while statement executes its statements as long as a specified condition evaluates to true. A while statement looks as follows:

>while (condition) {statement}
 
![While Loop](https://i.ytimg.com/vi/kUkqapBCsdE/hqdefault.jpg)

# Operators

JavaScript has the following types of operators. This section describes the operators and contains information about operator precedence.
* Assignment operators
* Comparison operators
* Arithmetic operators
* Bitwise operators 
* Logical operators
* String operators
* Conditional (ternary) operator
* Comma operator
* Unary operators
* Relational operators

JavaScript has both binary and unary operators, and one special ternary operator, the conditional operator. A binary operator requires two operands, one before the operator and one after the operator:

> operand1 operator operand2

For example, *3+4* or *x/y*.

### Assignment operators

An assignment operator assigns a value to its left operand based on the value of its right operand. The simple assignment operator is equal (=), which assigns the value of its right operand to its left operand. That is, x = y assigns the value of y to x.

following some examples of the assignment operators:

|Name|Shorthand operator|Meaning|
|:---|:----------------:|:-----:|
|Assignment| 	x = y| 	x = y|
|Addition assignment| 	x += y |	x = x + y|
|Subtraction assignment |	x -= y| 	x = x - y|
|Multiplication assignment| 	x *= y |	x = x * y|


### Comparison operators

A comparison operator compares its operands and returns a logical value based on whether the comparison is true. The operands can be numerical, string, logical, or object values. Strings are compared based on standard lexicographical ordering, using Unicode values. In most cases, if the two operands are not of the same type, JavaScript attempts to convert them to an appropriate type for the comparison. This behavior generally results in comparing the operands numerically. The sole exceptions to type conversion within comparisons involve the === and !== operators, which perform strict equality and inequality comparisons. These operators do not attempt to convert the operands to compatible types before checking equality. The following table describes the comparison operators in terms of this sample code:


|Operator| 	Description| 	Examples returning true|
|:---|:----------------:|:-----:|
|Equal (==)| 	Returns true if the operands are equal.| 	3 == var1 "3" == var1 3 == '3'|
|Not equal (!=)| 	Returns true if the operands are not equal. |	var1 != 4 var2 != "3"|
|Strict equal (===) |	Returns true if the operands are equal and of the same type. See also Object.is and sameness in JS.| 	3 === var1|
|Strict not equal (!==) |	Returns true if the operands are of the same type but not equal, or are of different type. |	var1 !== "3" 3 !== '3'|

