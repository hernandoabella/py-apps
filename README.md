# py-apps
# +100 Python Mini-Projects for Beginners

## Basic Projects

### Hello World CLI
This is the classic "Hello, World!" program implemented as a Command-Line Interface (CLI) using Python. It demonstrates how to accept user input from the terminal and display a personalized greeting.
```python
def main():
    name = input("Enter your name: ")
    print(f"Hello, {name}! Welcome to the Python CLI World")

if __name__ == "__main__":
    main()

# Enter your name: Hernando
# Hello, Hernando! Welcome to the Python CLI World
```

### Basic Calculator

Performs basic arithmetic operations like addition, subtraction, multiplication, and division. It takes user input for two numbers and the operation to perform.
```python
def calculator():
    print("Welcome to the Basic Calculator")
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
Welcome to the Basic Calculator
Enter first number: 10
Enter operator (+, -, *, /): *
Enter second number: 5
Result: 50.0
"""
```

## Leap Year Checker
Check whether a given year is a leap year or not. It uses basic conditional logic to evaluate leap year rules (divisible by 4, not divisible by 100 unless also divisible by 400).
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
2024 is a leap year.
""".
```

### Number Guessing Game
The computer randomly picks a number between 1 and 100, and the user has to guess it. The program gives hints like "Too high" or "Too low" until the correct number is guessed.
```python
import random

def number_guessing_game():
    print("Welcome to the Number Guessing Game!")
    secret_number = random.randint(1, 100)
    attempts = 0

    while True:
        try:
            guess = int(input("Guess a number between 1 and 100: "))
            attempts += 1

            if guess < secret_number:
                print("Too low! Try again.")
            elif guess > secret_number:
                print("Too high! Try again.")
            else:
                print(f"🎉 Congratulations! You guessed it in {attempts} attempts.")
                break
        except ValueError:
            print("Please enter a valid number.")

if __name__ == "__main__":
    number_guessing_game()

"""
Welcome to the Number Guessing Game!
Guess a number between 1 and 100: 50
Too low! Try again.
Guess a number between 1 and 100: 75
Too high! Try again.
Guess a number between 1 and 100: 68
Congratulations! You guessed it in 3 attempts.
"""
```

### Tip Calculator
Helps users calculate the tip amount based on their bill and chosen tip percentage. It also provides the total amount to be paid, including the tip.
```python
def tip_calculator():
    print("Tip Calculator")
    
    try:
        bill = float(input("Enter the total bill amount: $"))
        tip_percent = float(input("Enter tip percentage (e.g., 15 for 15%): "))
        people = int(input("How many people are splitting the bill? "))

        tip_amount = bill * (tip_percent / 100)
        total_amount = bill + tip_amount
        amount_per_person = total_amount / people

        print(f"\n🧾 Tip: ${tip_amount:.2f}")
        print(f"Total Amount: ${total_amount:.2f}")
        print(f"Amount per person: ${amount_per_person:.2f}")
        
    except ValueError:
        print("Invalid input. Please enter numeric values.")

if __name__ == "__main__":
    tip_calculator()

"""
Tip Calculator
Enter the total bill amount: $100
Enter tip percentage (e.g., 15 for 15%): 20
How many people are splitting the bill? 4

Tip: $20.00
Total Amount: $120.00
Amount per person: $30.00
"""
```

### Temperature Converter
Convert temperatures between Celsius and Fahrenheit. The user chooses the conversion direction and provides the temperature to convert.
```python
def celsius_to_fahrenheit(c):
    return (c * 9/5) + 32

def fahrenheit_to_celsius(f):
    return (f - 32) * 5/9

def temperature_converter():
    print("Temperature Converter")
    print("1. Celsius to Fahrenheit")
    print("2. Fahrenheit to Celsius")

    choice = input("Choose an option (1 or 2): ")

    try:
        if choice == '1':
            c = float(input("Enter temperature in Celsius: "))
            f = celsius_to_fahrenheit(c)
            print(f"{c}°C = {f:.2f}°F")
        elif choice == '2':
            f = float(input("Enter temperature in Fahrenheit: "))
            c = fahrenheit_to_celsius(f)
            print(f"{f}°F = {c:.2f}°C")
        else:
            print("Invalid choice.")
    except ValueError:
        print("Please enter a valid number.")

if __name__ == "__main__":
    temperature_converter()

"""
Temperature Converter
1. Celsius to Fahrenheit
2. Fahrenheit to Celsius
Choose an option (1 or 2): 1
Enter temperature in Celsius: 30
30.0°C = 86.00°F
"""
```

### Age Calculator
Calculates your current age based on your birth year. It uses the current system year to do the math.
```
from datetime import datetime

def age_calculator():
    print("Age Calculator")
    
    try:
        birth_year = int(input("Enter your birth year (e.g., 1998): "))
        current_year = datetime.now().year
        age = current_year - birth_year

        if age < 0:
            print("You entered a future year. Please check again.")
        else:
            print(f"You are {age} years old in {current_year}.")
    except ValueError:
        print("Invalid input. Please enter a valid year.")

if __name__ == "__main__":
    age_calculator()

"""
Age Calculator
Enter your birth year (e.g., 1998): 2000
You are 25 years old in 2025.
"""
```

### Countdown Timer
The user inputs the number of seconds, and the timer counts down to zero with a 1-second interval, displaying the remaining time in the terminal.

```python
import time

def countdown_timer():
    print("⏳ Countdown Timer")

    try:
        seconds = int(input("Enter the countdown time in seconds: "))
        while seconds > 0:
            mins, secs = divmod(seconds, 60)
            timer = f"{mins:02d}:{secs:02d}"
            print(timer, end="\r")
            time.sleep(1)
            seconds -= 1

        print("⏰ Time's up!")
    except ValueError:
        print("❌ Please enter a valid number.")

if __name__ == "__main__":
    countdown_timer()

"""
Countdown Timer
Enter the countdown time in seconds: 5
00:05
00:04
00:03
00:02
00:01
Time's up!
"""
```

### BMI Calculator
Calculates your Body Mass Index (BMI) using your weight and height. Based on the BMI value, it categorizes your health status (Underweight, Normal, Overweight, or Obese).
```
def calculate_bmi():
    print("⚖️ BMI Calculator")

    try:
        weight = float(input("Enter your weight in kilograms (kg): "))
        height = float(input("Enter your height in meters (m): "))
        bmi = weight / (height ** 2)

        print(f"\nYour BMI is: {bmi:.2f}")

        if bmi < 18.5:
            print("🟡 Category: Underweight")
        elif 18.5 <= bmi < 25:
            print("🟢 Category: Normal weight")
        elif 25 <= bmi < 30:
            print("🟠 Category: Overweight")
        else:
            print("🔴 Category: Obese")
    except ValueError:
        print("❌ Please enter valid numbers.")

if __name__ == "__main__":
    calculate_bmi()

"""
BMI Calculator
Enter your weight in kilograms (kg): 68
Enter your height in meters (m): 1.75

Your BMI is: 22.20
Category: Normal weight
"""
```

### 🎲 Dice Roller
Simulates rolling a dice. Each time the user presses Enter, a new number between 1 and 6 is rolled, just like a real die!
```
import random

def roll_dice():
    print("🎲 Dice Roller")
    while True:
        input("Press Enter to roll the dice...")
        dice = random.randint(1, 6)
        print(f"🎯 You rolled a {dice}!")
        
        again = input("Roll again? (y/n): ").lower()
        if again != 'y':
            print("👋 Thanks for playing!")
            break

if __name__ == "__main__":
    roll_dice()

"""
🎲 Dice Roller
Press Enter to roll the dice...
You rolled a 4!
Roll again? (y/n): y
Press Enter to roll the dice...
You rolled a 6!
Roll again? (y/n): n
Thanks for playing!
"""
```

## String & Text Projects

### Palindrome Checker

### Word Frequency Counter

### Anagram Detector

### Text Reverser

### Pig Latin Converter

### Morse Code Translator

### Random Story Generator

### Typing Speed Test

### Password Strength Checker

### Vowel Counter

### File Handling & Automation

### File Renamer

### File Organizer

### Bulk File Creator

### Text File Merger

### PDF Merger

### PDF to Text Converter

### Image to PDF Converter

### CSV to Excel Converter

### Word Count Tool

### Duplicate File Finder

## Games & Fun
Rock, Paper, Scissors

Hangman

Tic Tac Toe

Snake Game

Flappy Bird Clone

Memory Game

Quiz Game

Dice Game

Number Puzzle

Simon Game

## GUI with Tkinter / PyQt
Digital Clock

Alarm Clock

To-Do List

Basic Chat Interface

Notepad Clone

BMI GUI

Calendar App

Unit Converter

Pomodoro Timer

Paint App

## Web & API Projects
Weather App (API)

Dictionary App

Web Scraper (e.g., News)

Currency Converter

URL Shortener

Reddit Scraper

Wikipedia Searcher

Stock Price Checker

Random Joke Generator

Movie Info Fetcher

## Data Projects
CSV Viewer

JSON Formatter

Expense Tracker

Budget Calculator

Pie Chart Generator

Line Graph Visualizer

Email Data Extractor

Log File Analyzer

Survey Analyzer

Markdown Table Generator

## Desktop & Utility Tools
Screen Capture Tool

Color Picker

Clipboard Manager

Desktop Notification App

Stopwatch

Screenshot Organizer

Wallpaper Changer

Folder Size Visualizer

Text Encryption Tool

File Compression Tool

## Intermediate to Advanced Projects
YouTube Video Downloader

Instagram Auto-Liker

Twitter Bot

Face Detection with OpenCV

QR Code Generator

Barcode Reader

Chatbot with NLP

Voice Recognition App

Text-to-Speech Tool

Email Automation App

## Web Apps & Flask Projects
Mini Blog (Flask)

Login Authentication App

Polling App

Notes Keeper Web App

Chat App (Sockets)

Task Manager API

URL Tracker

Book Collection Manager

Contact Form with Flask

Portfolio Website Backend

## Bonus Projects
Instagram Story Downloader

Fake Name Generator (using Faker)

Excel Automation Tool (with openpyxl)

Audio File Converter (MP3 ↔ WAV)

Grammar Checker (via LanguageTool API)

LinkedIn Profile Scraper (BeautifulSoup + Selenium)

Live Crypto Price Tracker

GIF Creator from Images

Folder Locker (Password Protected GUI)

Custom Shell / Terminal Emulator

Voice-Controlled Assistant (SpeechRecognition + pyttsx3)

PDF Invoice Generator (with ReportLab)

Text-Based Adventure Game

Currency Rate Alert System (email or SMS)

Desktop App Updater (Version Checker)

AI Story Generator (OpenAI API)

Task Scheduler with Notification

Color Palette Generator from Images

Spotify Playlist Maker (using Spotipy)

Resume Parser (using PyPDF2 + Regex)

Matrix Effect & Creative Additions
Matrix Digital Rain Effect

Auto Typer / Keyboard Simulator

ASCII Art Generator from Images

Live Weather Wallpaper (Updates based on location)

Python REPL Enhancer (custom prompt, history)

Command Line Spotify Controller (with API)

Random Meme Fetcher (via Reddit API)

Mood Detector from Text (Sentiment Analysis)

Typing Tutor (with real-time WPM feedback)

Live Typing Animation in Terminal

Tetris Clone (with Pygame)

Minesweeper Game (GUI)

Maze Solver Visualizer (DFS/BFS Algorithms)

Music Visualizer (with pyaudio + matplotlib)

Live Screen Color Detector

Custom Keyboard Layout Remapper

Text Adventure Game with Map & Inventory

Command Line Resume Builder

Daily Quote Wallpaper Generator

AI Image Caption Generator (with Transformers)
