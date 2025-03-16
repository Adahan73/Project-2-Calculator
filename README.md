# Project-2-Calculator
This console-based calculator allows users to enter full arithmetic expressions, including functions like power(base, exponent), sqrt(number), abs(number), and round(number). It supports basic operations (+, -, *, /, %), handles parentheses, and maintains a history of past calculations.

# ***Documentation:***

## 1. Project Overview
The Java Console-Based Calculator is an interactive program that allows users to evaluate arithmetic expressions, including functions like power(base, exponent), sqrt(number), abs(number), and round(number). The calculator supports basic operations (+, -, *, /, %), parentheses, and operator precedence, while also maintaining a history of past calculations.

## 2. Design Choices
User Input Handling: The program uses a Scanner to read user input, allowing flexible expression entry.
Expression Parsing and Evaluation: Instead of relying on JavaScript engines (e.g., Nashorn), the implementation uses a custom expression parser to evaluate mathematical expressions.
Function Support: Functions like power(), sqrt(), abs(), and round() are manually parsed and computed, enabling mathematical operations beyond simple arithmetic.
Stack-Based Evaluation: The program processes expressions using stacks, ensuring correct precedence and handling of parentheses.
History Feature: The calculator maintains a list of previous calculations, allowing users to review past results.
3. Algorithms and Data Structures Used
Stack-Based Expression Evaluation

The program uses two stacks (numbers and operators) to evaluate expressions based on the Shunting-Yard Algorithm principles.
Operators are pushed onto a stack and applied based on precedence rules.
Parentheses are handled by evaluating subexpressions within them first.
Recursive Function Parsing

Functions like sqrt(), abs(), and power() are detected and evaluated recursively, ensuring correctness when nested inside other expressions.
The function extraction algorithm finds and evaluates function arguments, replacing them in the original expression.
Handling Negative Numbers

Special handling ensures expressions like -5 + 3 are parsed correctly, treating - as a sign rather than an operator when needed.

## 4. Challenges Encountered
(a) JavaScript Engine Removal Issue
Initially, we considered using ScriptEngineManager to evaluate expressions. However, Nashorn was removed in Java 15, making it unreliable for long-term use.
Solution: Implemented a custom mathematical expression parser to evaluate expressions without external dependencies.
(b) Parsing Complex Expressions with Functions
Expressions with functions like power(2,3) + sqrt(16) required custom parsing to extract arguments properly.
Solution: Used string manipulation and recursive function calls to evaluate functions before evaluating arithmetic expressions.
(c) Handling Operator Precedence and Parentheses
Ensuring correct order of operations (* and / before + and -) required a stack-based approach to evaluation.
Solution: Used two stacks (numbers and operators) to process expressions iteratively, maintaining precedence rules.

## 5. Improvements Made
Replaced JavaScript engine evaluation with a custom parser, ensuring compatibility with all Java versions.
Added full function support (power(), sqrt(), abs(), round()).
Implemented history tracking, allowing users to view past calculations.
Enhanced error handling to detect division by zero and invalid expressions.

## 6. File Handling (Input/Output)
No files are used in this implementation.
The program operates in real-time using console input and output.
If needed, a future version could save history to a file for persistence.

## 7. Additional Explanations
The program is designed to be expandable, allowing future additions like logarithmic functions (log()) or trigonometric functions (sin(), cos()).
The approach used (stack-based evaluation) is efficient and ensures proper operator precedence.

## 8. Conclusion
This Java Console-Based Calculator successfully evaluates arithmetic expressions, including custom functions, while ensuring accurate parsing, precedence handling, and error detection. The custom stack-based evaluation method ensures correctness without relying on deprecated JavaScript engines. With additional refinements, the program could be extended to support more advanced mathematical functions or GUI-based input for better user experience.


