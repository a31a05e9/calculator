# Simple Python GUI Calculator
This project is a simple calculator application built using Python's Tkinter library. It provides a basic GUI interface to perform arithmetic operations including addition, subtraction, multiplication, and division.
Features :
Basic arithmetic operations: addition, subtraction, multiplication, division
Clear button to reset the current expression
Decimal point support
Error handling for invalid expressions
How It Works
Expression Entry: The entry box at the top of the GUI displays the current arithmetic expression.
Buttons: Number buttons (0-9) and operator buttons (+, -, *, /) allow the user to input the expression.
Decimal Button: Adds a decimal point to the expression.
Equal Button: Evaluates the expression and displays the result.
Clear Button: Clears the current expression.
Code Explanation
Import Statements:
from tkinter import *
Global Variable:
expression stores the current arithmetic expression.
Functions:
press(num): Updates the expression based on the button pressed.
equalpress(): Evaluates the expression and displays the result, handling errors.
clear(): Clears the entry box and resets the expression.
GUI Setup:
The GUI is created using Tkinter, with buttons for numbers, operators, and functionalities.
The grid layout is used to position the buttons in a calculator-like arrangement.

