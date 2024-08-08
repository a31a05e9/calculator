# Python program to create a simple GUI calculator using Tkinter

from tkinter import *

# Globally declare the expression variable
expression = ""

# Function to update the expression in the text entry box
def press(num):
    global expression
    expression += str(num)  # Concatenate the string
    equation.set(expression)  # Update the expression

# Function to evaluate the final expression
def equalpress():
    global expression
    try:
        # Evaluate the expression and convert the result to string
        total = str(eval(expression))
        equation.set(total)
        expression = ""  # Reset the expression
    except Exception as e:
        # Handle any errors (e.g., zero division error) by displaying "error"
        equation.set(" error ")
        expression = ""

# Function to clear the contents of the text entry box
def clear():
    global expression
    expression = ""
    equation.set("")  # Clear the expression

# Driver code
if __name__ == "__main__":
    # Create a GUI window
    gui = Tk()
    gui.configure(background="light green")  # Set background color
    gui.title("Simple Calculator")  # Set window title
    gui.geometry("270x200")  # Set window size

    # Create a StringVar instance for the expression
  equation = StringVar()

    # Create the text entry box for showing the expression
  expression_field = Entry(gui, textvariable=equation)
  expression_field.grid(columnspan=4, ipadx=70)

    # Define button configurations
  button_texts = [
        ('1', 2, 0), ('2', 2, 1), ('3', 2, 2),
        ('4', 3, 0), ('5', 3, 1), ('6', 3, 2),
        ('7', 4, 0), ('8', 4, 1), ('9', 4, 2),
        ('0', 5, 0), ('.', 6, 0), ('+', 2, 3),
        ('-', 3, 3), ('*', 4, 3), ('/', 5, 3),
        ('=', 5, 2), ('Clear', 5, 1)
    ]

    # Create buttons
  for (text, row, col) in button_texts:
        if text == '=':
            Button(gui, text=text, fg='black', bg='red', command=equalpress, height=1, width=7).grid(row=row, column=col)
        elif text == 'Clear':
            Button(gui, text=text, fg='black', bg='red', command=clear, height=1, width=7).grid(row=row, column=col)
        else:
            Button(gui, text=text, fg='black', bg='red', command=lambda t=text: press(t), height=1, width=7).grid(row=row, column=col)

    # Start the GUI
  gui.mainloop()
