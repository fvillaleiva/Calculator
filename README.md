﻿# Calculator

A scientific calculator on the computer

## Users
Users can run the following files:
* __'UserInterface.pyw'__ for a graphical user interface
* __'Interface.py'__ for a command-line interface with memory
* __'Calc.py'__ for a command-line interface without memory

## Programmers

### To calculate the answer to a single expression
Use the __'calculate'__ function from the file __'Calc.py'__

### To create a custom user interface using my memory system
Instantiate the __'Interface'__ class in the file __'Interface.py'__ and:
* if the user wants to calculate the answer to an expression, use the __'calculate'__ method
* if the user wants to view instructions, use the __'instructions'__ attribute
* if the user wants to view memory, use the __'recent_memory'__ method
* if the user wants to clear memory, use the __'clear_memory'__ method
* if the user wants to insert a specific memory answer into their expression:
    1. get which memory item is being requested
    1. use the __'memory_item'__ method to get the original expression and answer of interest
    1. it may be best to re-calculate the answer using the original expression and the __'calculate'__ method
    1. insert the answer from memory or the re-calculated answer into the expression

NOTE: before calling the __'recent_memory'__ or __'memory_item'__ methods with a number from the user, the interface should call __'len_memory'__ to check how many items are in memory and verify the number wanted is a valid number and equal to or less than the number of items in memory. If not, display the relevant error message. If either of these methods are called with invalid parameters, they will raise __'IndexError'__.

### To create a custom user interface without my memory system
1. use the __'calculate'__ function in __'Calc.py'__ to call the calculator with an expression
1. catch any errors derived from __'CalcError'__ in __'Errors.py'__ and present the message to the user
1. add to and present to the user the instructions from the global variable __'instructions'__ in __'Calc.py'__

### To add custom operations to the calculator
1. write a function to execute the operation in __'Operations.py'__
1. import this into __'Datatypes.py'__
1. add details of the operation including the function to the __'valid_tokens'__ dictionary at the bottom of __'Datatypes.py'__
1. explain how to use it in __'Instructions.txt'__

## Instructions

Enter an expression to calculate the answer.

Operators are represented by a symbol and perform an operation on the numbers around them. Binary operators have 2 numbers (1 either side of the symbol), whereas unary operators have 1 number (either left or right of the symbol). Functions are represented by a word followed by brackets containing all operands (values needed for the function) separated by commas. Constants are a word representing a number very accurately. Simply enter the word and it will convert it to the number.

Functions and constants are always executed first and then operators are executed using BODMAS - brackets, other (exponents and unary operators), division and multiplication, addition and subtraction.

### Binary Operators
* Addition: use '+' between 2 numbers to find the first add the second.
* Subtraction: use '-' between 2 numbers to find the first subtract the second.
* Multiplication: use '*' between 2 numbers to find the first multiplied by the second.
* Division (true): use '/' between 2 numbers to find the first divided by the second.
* Division (floor): use '\\' between 2 numbers to find the first divided by the second and rounded down to the nearest whole number.
* Mod: use '%' between 2 numbers to find the remainder after the first is divided by the second.
* Exponentiation: use '^' between 2 numbers to find the first to the power of the second.
* Root: use '¬' to find the first th root of the second - '2¬a' is the square root of 'a', '3¬a' is the cube root of 'a', etc.
* Permutations: use 'P' to find the number of ways there are to organise the second number of items into the first number of places including all possible orders.
* Combinations: use 'C' to find the number of ways there are to organise the second number of items into the first number of places only counting 1 possible order.

### Unary Operators
* Positive: use '+' before a number to find the positive of it.
* Negative: use '-' before a number to find the negative of it.
* Factorial: use '!' after a positive whole number to find the product of all positive whole numbers less than or equal to it.

### Functions
* Natural log: use 'ln' with 1 operand to find the natural logarithm of it.
* Logarithm: use 'log' with 2 operands to find the logarithm of the first to the second base.
* Absolute value: use 'abs' with 1 operand to find the absolute value of it which is always positive.
* Lowest common multiple: use 'lcm' with 2 operands to find the lowest common multiple of them.
* Highest common factor: use 'hcf' with 2 operands to find the highest common factor of them.
* Random number generator: use 'rand' with 2 operands to find a random integer between them, inclusive.
* Quadratic equation solver: use 'quadp' with 3 operands (a, b and c) to find the positive square root answer to the quadratic equation 'ax^2 + bx + c = 0' or use 'quadn' to find the negative square root answer of the same equation.
* Sine: use 'sin' with 1 operand (an angle) to find the ratio between the opposite side and hypotenuse of its triangle.
* Cosine: use 'cos' with 1 operand (an angle) to find the ratio between the adjacent side and hypotenuse of its triangle.
* Tangent: use 'tan' with 1 operand (an angle) to find the radio between the opposite and adjacent sides of its triangle.
* Inverse sine: use 'arsin' with 1 operand between -1 and 1 inclusive to find the angle it makes with the opposite side and hypotenuse of its triangle.
* Inverse cosine: use 'arcos' with 1 operand between -1 and 1 inclusive to find the angle it makes with the adjacent side and hypotenuse of its triangle.
* Inverse tangent: use 'artan' with 1 operand to find the angle it makes with the opposite and adjacent sides of its triangle.
* Hyperbolic sine: use 'sinh' with 1 operand (an angle) to find the ratio between the opposite side and hypotenuse of its hyperbola.
* Hyperbolic cosine: use 'cosh' with 1 operand (an angle) to find the ratio between the adjacent side and hypotenuse of its hyperbola.
* Hyperbolic tangent: use 'tanh' with 1 operand (an angle) to find the ratio between the opposite and adjacent sides of its hyperbola.
* Inverse hyperbolic sine: use 'arsinh' with 1 operand to find the angle it makes with the opposite side and hypotenuse of its hyperbola.
* Inverse hyperbolic cosine: use 'arcosh' with 1 operand at least 1 to find the angle it makes with the adjacent side and hypotenuse of its hyperbola.
* Inverse hyperbolic tangent: use 'artanh' with 1 operand between -1 and 1 inclusive to find the angle it makes with the opposite and adjacent sides of its hyperbola.

### Constants
* pi: use 'pi' to get the ratio between a circle's circumference and its diameter. Value = 3.1415...
* tau: use 'tau' to get 2 lots of pi - the number of radians in 360 degrees. Value = 6.2831...
* e: use 'e' to get Euler's number. Value = 2.7182...
* g: use 'g' to get the acceleration due to gravity close to the Earth's surface. Value = 9.80665
* phi: use 'phi' to get the golden ratio found in many places in nature. Value = 1.6180...