# py-apps
# +100 Python Mini-Projects for Beginners

## Basic Projects

### Hello World CLI
This is the classic "Hello, World!" program implemented as a Command-Line Interface (CLI) using Python. It demonstrates how to accept user input from the terminal and display a personalized greeting.
```python
def main():
    name = input("Enter your name: ")
    print(f"Hello, {name}! Welcome to the Python CLI World 🚀")

if __name__ == "__main__":
    main()

# Enter your name: Hernando
# Hello, Hernando! Welcome to the Python CLI World
```

### Basic Calculator

A simple Python CLI calculator that performs basic arithmetic operations like addition, subtraction, multiplication, and division. It takes user input for two numbers and the operation to perform.
```python
def calculator():
    print("Welcome to the Basic Calculator 🧮")
    num1 = float(input("Enter first number: "))
    operator = input("Enter operator (+, -, *, /): ")
    num2 = float(input("Enter second number: "))

    if operator == '+':
        result = num1 + num2
    elif operator == '-':
        result = num1 - num2
    elif operator == '*':
        result = num1 * num2
    elif operator == '/':
        if num2 == 0:
            print("Error: Cannot divide by zero.")
            return
        result = num1 / num2
    else:
        print("Invalid operator.")
        return

    print(f"Result: {result}")

if __name__ == "__main__":
    calculator()

"""
Welcome to the Basic Calculator 🧮
Enter first number: 10
Enter operator (+, -, *, /): *
Enter second number: 5
Result: 50.0
"""
```

## Leap Year Checker
A simple Python CLI tool to check whether a given year is a leap year or not. It uses basic conditional logic to evaluate leap year rules (divisible by 4, not divisible by 100 unless also divisible by 400).
```python
def is_leap_year(year):
    return (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0)

def main():
    print("Leap Year Checker")
    year = int(input("Enter a year: "))

    if is_leap_year(year):
        print(f" {year} is a leap year.")
    else:
        print(f" {year} is not a leap year.")

if __name__ == "__main__":
    main()
"""
Leap Year Checker
Enter a year: 2024
✅ 2024 is a leap year.
""".
```



Number Guessing Game
Tip Calculator
Temperature Converter
Age Calculator
Countdown Timer
BMI Calculator
Dice Roller
String & Text Projects
Palindrome Checker
Word Frequency Counter
Anagram Detector
Text Reverser
Pig Latin Converter
Morse Code Translator
Random Story Generator
Typing Speed Test
Password Strength Checker
Vowel Counter
