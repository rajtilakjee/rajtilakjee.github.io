# Python Foundations Tutorial

A comprehensive guide to Python fundamentals covering variables, data structures, control flow, functions, OOP, and more.

---

## 1. Variables and Types

### Understanding Variables

Variables are containers for storing data values. In Python, you don't need to explicitly declare a variable type—Python infers it based on the value you assign.

```python
# Simple variable assignment
name = "Alice"
age = 25
height = 5.8

# Python determines the type automatically
print(type(name))      # <class 'str'>
print(type(age))       # <class 'int'>
print(type(height))    # <class 'float'>
```

### Dynamic Typing

Python is dynamically typed, meaning a variable's type can change:

```python
x = 10          # x is an int
print(type(x))  # <class 'int'>

x = "hello"     # now x is a str
print(type(x))  # <class 'str'>
```

### Naming Conventions

- Use `snake_case` for variable names: `user_name`, `max_value`
- Start with a letter or underscore, not a number
- Be descriptive: `age` is better than `a`
- Avoid Python keywords: `class`, `def`, `if`, `return`, etc.

```python
# Good naming
total_price = 99.99
is_valid = True
_private_var = 42

# Avoid this
x = 99.99
a = True
classVar = 42  # Should be class_var
```

### Type Conversion

You can explicitly convert between types:

```python
# String to integer
num_str = "42"
num = int(num_str)

# Integer to string
count = 5
count_str = str(count)

# Float conversions
value = float("3.14")
value_int = int(3.99)  # Truncates to 3

# Boolean conversions
bool(1)        # True
bool(0)        # False
bool("")       # False
bool("hello")  # True
```

---

## 2. Strings in Depth

### String Basics

Strings are sequences of characters enclosed in single, double, or triple quotes:

```python
single = 'Hello'
double = "World"
triple = '''This is a
multi-line string'''

# Escaping characters
escaped = "He said \"Hi\""
newline = "Line 1\nLine 2"
tab = "Column 1\tColumn 2"
```

### String Concatenation and Multiplication

```python
# Concatenation
greeting = "Hello" + " " + "World"

# Multiplication
stars = "*" * 10  # "**********"

# String indexing (0-based)
text = "Python"
print(text[0])    # 'P'
print(text[-1])   # 'n' (last character)
```

### String Slicing

Slices use the syntax `[start:end:step]` where `end` is exclusive:

```python
text = "Hello World"

print(text[0:5])    # "Hello"
print(text[6:])     # "World"
print(text[:5])     # "Hello"
print(text[::2])    # "HloWrd" (every 2nd character)
print(text[::-1])   # "dlroW olleH" (reversed)
```

### String Methods

```python
text = "  Hello World  "

# Case conversion
print(text.upper())           # "  HELLO WORLD  "
print(text.lower())           # "  hello world  "
print(text.title())           # "  Hello World  "

# Whitespace handling
print(text.strip())           # "Hello World"
print(text.lstrip())          # "Hello World  "
print(text.rstrip())          # "  Hello World"

# Searching and replacing
print("Hello World".find("World"))        # 6
print("Hello World".replace("World", "Python"))  # "Hello Python"
print("Hello World".startswith("Hello"))  # True
print("Hello World".endswith("ld"))       # True

# Splitting and joining
words = "apple,banana,cherry".split(",")  # ['apple', 'banana', 'cherry']
joined = "-".join(words)                   # "apple-banana-cherry"

# Checking content
print("hello123".isalpha())     # False
print("hello".isalpha())        # True
print("123".isdigit())          # True
```

### String Formatting

```python
# Old-style formatting
name = "Alice"
age = 30
print("My name is %s and I'm %d years old" % (name, age))

# .format() method
print("My name is {} and I'm {} years old".format(name, age))
print("My name is {name} and I'm {age} years old".format(name=name, age=age))

# f-strings (Python 3.6+) - preferred
print(f"My name is {name} and I'm {age} years old")
print(f"Calculation: {10 * 5}")
print(f"Rounded: {3.14159:.2f}")
```

---

## 3. Numbers and Arithmetic

### Integer and Float Types

```python
# Integers
x = 10
y = -5
z = 0

# Floats (decimal numbers)
a = 3.14
b = -2.5
c = 1.0

# Scientific notation
large = 1.23e6   # 1,230,000
small = 1.5e-3   # 0.0015

# Type checking
print(type(10))     # <class 'int'>
print(type(10.0))   # <class 'float'>
```

### Arithmetic Operations

```python
# Basic operations
print(10 + 3)       # 13 (addition)
print(10 - 3)       # 7 (subtraction)
print(10 * 3)       # 30 (multiplication)
print(10 / 3)       # 3.333... (division, returns float)
print(10 // 3)      # 3 (floor division)
print(10 % 3)       # 1 (modulo/remainder)
print(2 ** 3)       # 8 (exponentiation)
```

### Order of Operations (PEMDAS)

```python
# Exponentiation first
result = 2 + 3 * 2 ** 2  # 2 + 3 * 4 = 2 + 12 = 14

# Use parentheses for clarity
result = (2 + 3) * (2 ** 2)  # 5 * 4 = 20
```

### Compound Assignment Operators

```python
x = 10
x += 5      # x = x + 5 → 15
x -= 3      # x = x - 3 → 12
x *= 2      # x = x * 2 → 24
x /= 4      # x = x / 4 → 6.0
x //= 2     # x = x // 2 → 3.0
x **= 2     # x = x ** 2 → 9.0
```

### Math Functions and Module

```python
import math

# Built-in functions
print(abs(-10))         # 10 (absolute value)
print(round(3.7))       # 4 (rounding)
print(round(3.14159, 2)) # 3.14 (round to 2 decimals)
print(min(3, 1, 4, 1, 5))  # 1
print(max(3, 1, 4, 1, 5))  # 5
print(sum([1, 2, 3, 4]))   # 10

# Math module
print(math.sqrt(16))    # 4.0
print(math.ceil(3.2))   # 4 (round up)
print(math.floor(3.9))  # 3 (round down)
print(math.pi)          # 3.14159...
print(math.e)           # 2.71828...
```

---

## 4. Booleans and Truthiness

### Boolean Values

```python
# The two boolean values
is_active = True
is_empty = False

print(type(True))   # <class 'bool'>
```

### Comparison Operators

```python
x = 10
y = 5

print(x == y)       # False (equal to)
print(x != y)       # True (not equal to)
print(x > y)        # True (greater than)
print(x < y)        # False (less than)
print(x >= y)       # True (greater than or equal)
print(x <= y)       # False (less than or equal)

# String comparison (alphabetical)
print("apple" < "banana")   # True
print("apple" == "apple")   # True
```

### Logical Operators

```python
x = 10

# and (both must be True)
print(x > 5 and x < 15)     # True
print(x > 5 and x < 8)      # False

# or (at least one must be True)
print(x > 15 or x < 15)     # True
print(x > 15 or x > 20)     # False

# not (inverts the boolean)
print(not x > 15)           # True
print(not True)             # False
```

### Truthiness

In Python, values have inherent "truthiness":

```python
# Truthy values (evaluate to True in boolean context)
if "hello":         # Non-empty strings are truthy
    print("Truthy")

if [1, 2, 3]:       # Non-empty lists are truthy
    print("Truthy")

if 42:              # Non-zero numbers are truthy
    print("Truthy")

# Falsy values (evaluate to False)
if 0:               # Zero is falsy
    print("Won't print")

if "":              # Empty strings are falsy
    print("Won't print")

if []:              # Empty lists are falsy
    print("Won't print")

if None:            # None is always falsy
    print("Won't print")

# Using truthiness
username = "alice"
if username:        # Equivalent to: if username != ""
    print(f"Welcome {username}")
```

### Identity Operators

```python
x = [1, 2, 3]
y = [1, 2, 3]
z = x

print(x == y)       # True (same contents)
print(x is y)       # False (different objects)
print(x is z)       # True (same object)

# Checking for None (always use 'is')
value = None
if value is None:
    print("Value is None")
```

---

## 5. if, elif, and else

### Basic if Statements

```python
age = 18

if age >= 18:
    print("You are an adult")
```

### if-else Statements

```python
age = 16

if age >= 18:
    print("You are an adult")
else:
    print("You are a minor")
```

### if-elif-else Statements

```python
score = 75

if score >= 90:
    grade = 'A'
elif score >= 80:
    grade = 'B'
elif score >= 70:
    grade = 'C'
elif score >= 60:
    grade = 'D'
else:
    grade = 'F'

print(f"Grade: {grade}")  # Grade: C
```

### Nested if Statements

```python
age = 25
has_license = True

if age >= 18:
    if has_license:
        print("You can drive")
    else:
        print("You need a license")
else:
    print("You are too young")
```

### Conditional Expressions (Ternary Operator)

```python
age = 20
status = "adult" if age >= 18 else "minor"
print(status)  # "adult"

# More complex example
score = 75
result = "Pass" if score >= 60 else "Fail"
message = f"You {result}!"  # "You Pass!"
```

---

## 6. for Loops and range()

### Basic for Loop

```python
# Iterate over a sequence
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(f"I like {fruit}")

# Using enumerate to get index and value
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")
```

### The range() Function

`range()` generates a sequence of numbers:

```python
# range(stop)
for i in range(5):
    print(i)  # 0, 1, 2, 3, 4

# range(start, stop)
for i in range(1, 5):
    print(i)  # 1, 2, 3, 4

# range(start, stop, step)
for i in range(0, 10, 2):
    print(i)  # 0, 2, 4, 6, 8

# Countdown
for i in range(5, 0, -1):
    print(i)  # 5, 4, 3, 2, 1
```

### Iterating with range() Length

```python
items = ["a", "b", "c", "d"]

# Method 1: Direct iteration
for item in items:
    print(item)

# Method 2: Using range with indices
for i in range(len(items)):
    print(f"Index {i}: {items[i]}")

# Method 3: Using enumerate (preferred)
for i, item in enumerate(items):
    print(f"Index {i}: {item}")
```

### Loop Control: break and continue

```python
# break - exits the loop
for i in range(10):
    if i == 5:
        break
    print(i)  # 0, 1, 2, 3, 4

# continue - skips to the next iteration
for i in range(5):
    if i == 2:
        continue
    print(i)  # 0, 1, 3, 4
```

### Nested Loops

```python
# Multiplication table
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i} × {j} = {i*j}")
```

### Loop-else (Optional but Useful)

```python
# The else block runs if the loop completes normally (no break)
for i in range(5):
    print(i)
else:
    print("Loop completed successfully")

# The else block is skipped if break is used
for i in range(10):
    if i == 5:
        break
    print(i)
# else: (this won't execute due to break)
```

---

## 7. while Loops

### Basic while Loop

```python
count = 0

while count < 5:
    print(f"Count: {count}")
    count += 1
```

### Infinite Loops and Exit Conditions

```python
# Infinite loop with break
while True:
    user_input = input("Enter 'quit' to exit: ")
    if user_input == "quit":
        break
    print(f"You entered: {user_input}")
```

### while with else

```python
# else runs if loop exits normally (without break)
count = 0

while count < 3:
    print(count)
    count += 1
else:
    print("While loop completed")  # This prints
```

### Practical Examples

```python
# Password validation
password = ""
attempts = 0

while attempts < 3:
    password = input("Enter password: ")
    if password == "secret123":
        print("Access granted")
        break
    attempts += 1
else:
    print("Too many attempts")

# Summing numbers
total = 0
num = 1

while num <= 100:
    total += num
    num += 1

print(f"Sum of 1-100: {total}")  # 5050
```

---

## 8. Functions

### Defining and Calling Functions

```python
# Simple function
def greet():
    print("Hello!")

greet()  # Call the function

# Function with parameters
def greet_person(name):
    print(f"Hello, {name}!")

greet_person("Alice")  # Hello, Alice!
```

### Return Values

```python
def add(a, b):
    return a + b

result = add(5, 3)
print(result)  # 8

# Multiple returns
def min_max(a, b):
    if a < b:
        return a, b
    else:
        return b, a

small, large = min_max(10, 5)
print(small, large)  # 5 10
```

### Default Arguments

```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("Alice"))           # Hello, Alice!
print(greet("Bob", "Hi"))       # Hi, Bob!
```

### Keyword Arguments

```python
def describe_person(name, age, city):
    return f"{name}, {age} years old, from {city}"

# Positional arguments
print(describe_person("Alice", 30, "NYC"))

# Keyword arguments
print(describe_person(name="Bob", age=25, city="LA"))

# Mixed
print(describe_person("Charlie", city="Boston", age=35))
```

### Variable-Length Arguments

```python
# *args - variable number of positional arguments (as a tuple)
def sum_all(*numbers):
    total = 0
    for num in numbers:
        total += num
    return total

print(sum_all(1, 2, 3))        # 6
print(sum_all(1, 2, 3, 4, 5))  # 15

# **kwargs - variable number of keyword arguments (as a dictionary)
def print_info(**info):
    for key, value in info.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=30, city="NYC")

# Combining all
def flexible_function(a, b, *args, **kwargs):
    print(f"a={a}, b={b}")
    print(f"args={args}")
    print(f"kwargs={kwargs}")

flexible_function(1, 2, 3, 4, name="Alice", age=30)
```

### Docstrings and Documentation

```python
def calculate_area(radius):
    """
    Calculate the area of a circle given its radius.
    
    Args:
        radius (float): The radius of the circle
        
    Returns:
        float: The area of the circle
    """
    import math
    return math.pi * radius ** 2

print(calculate_area(5))  # 78.53981633974483
help(calculate_area)      # Prints the docstring
```

### Scope: Local vs Global

```python
global_var = "I'm global"

def my_function():
    local_var = "I'm local"
    print(global_var)  # Can access global variables
    print(local_var)   # Can access local variables

my_function()
print(global_var)      # Works
# print(local_var)     # Error: local_var is not defined here
```

---

## 9. Lists

### Creating and Accessing Lists

```python
# Creating lists
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]
empty = []

# Indexing (0-based)
print(numbers[0])      # 1
print(numbers[-1])     # 5 (last element)

# Slicing
print(numbers[1:4])    # [2, 3, 4]
print(numbers[:3])     # [1, 2, 3]
print(numbers[2:])     # [3, 4, 5]
print(numbers[::2])    # [1, 3, 5]
print(numbers[::-1])   # [5, 4, 3, 2, 1] (reversed)
```

### Modifying Lists

```python
numbers = [1, 2, 3, 4, 5]

# Changing elements
numbers[0] = 10
print(numbers)  # [10, 2, 3, 4, 5]

# Adding elements
numbers.append(6)          # [10, 2, 3, 4, 5, 6]
numbers.insert(1, 20)      # [10, 20, 2, 3, 4, 5, 6]
numbers.extend([7, 8])     # [10, 20, 2, 3, 4, 5, 6, 7, 8]

# Removing elements
numbers.remove(20)         # Removes first occurrence of 20
popped = numbers.pop()     # Removes and returns last element
popped_index = numbers.pop(0)  # Remove and return first element
numbers.clear()            # Removes all elements
```

### List Methods

```python
numbers = [3, 1, 4, 1, 5, 9, 2, 6]

print(len(numbers))        # 8
print(numbers.count(1))    # 2 (how many 1's)
print(numbers.index(4))    # 2 (position of first 4)

# Sorting
numbers_sorted = sorted(numbers)  # Returns new sorted list
numbers.sort()             # Sorts in-place

# Reversing
numbers.reverse()          # Reverses in-place
reversed_list = list(reversed(numbers))  # Returns reversed copy
```

### Iteration

```python
fruits = ["apple", "banana", "cherry"]

# Basic iteration
for fruit in fruits:
    print(fruit)

# With index
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")

# Checking membership
if "banana" in fruits:
    print("Found banana")
```

---

## 10. Tuples and Unpacking

### Creating and Accessing Tuples

Tuples are immutable (cannot be changed after creation):

```python
# Creating tuples
coordinates = (10, 20)
colors = ("red", "green", "blue")
single = (42,)  # Note the comma for single-element tuple
empty = ()

# Accessing elements (same as lists)
print(coordinates[0])    # 10
print(colors[-1])        # "blue"
print(coordinates[0:2])  # (10, 20)
```

### Immutability

```python
numbers = (1, 2, 3)

print(len(numbers))      # 3
print(1 in numbers)      # True
print(numbers.count(1))  # 1
print(numbers.index(2))  # 1

# This will raise an error:
# numbers[0] = 10  # TypeError: 'tuple' object does not support item assignment
```

### Tuple Unpacking

```python
# Simple unpacking
coordinates = (10, 20)
x, y = coordinates
print(x, y)  # 10 20

# Unpacking in a loop
pairs = [(1, 2), (3, 4), (5, 6)]
for a, b in pairs:
    print(f"Sum: {a + b}")  # Sum: 3, Sum: 7, Sum: 11

# Swapping variables
a, b = 1, 2
a, b = b, a  # Swap
print(a, b)  # 2 1

# Ignoring values with underscore
name, _, city = ("Alice", 30, "NYC")
print(name, city)  # Alice NYC

# Extended unpacking
first, *middle, last = [1, 2, 3, 4, 5]
print(first, middle, last)  # 1 [2, 3, 4] 5
```

### When to Use Tuples

```python
# Use tuples as dictionary keys (lists cannot be keys)
location_data = {
    (10, 20): "Point A",
    (30, 40): "Point B"
}

# Return multiple values
def get_user():
    return ("Alice", 30, "alice@email.com")

name, age, email = get_user()

# Ensure data isn't accidentally modified
def process_coordinates(coords):
    # coords is a tuple, so we know the values won't be changed internally
    pass
```

---

## 11. Dictionaries

### Creating and Accessing Dictionaries

Dictionaries store key-value pairs:

```python
# Creating dictionaries
person = {
    "name": "Alice",
    "age": 30,
    "city": "NYC"
}

# Accessing values
print(person["name"])      # Alice
print(person.get("age"))   # 30
print(person.get("job"))   # None (safe, doesn't error)
print(person.get("job", "Unknown"))  # Unknown (with default)
```

### Modifying Dictionaries

```python
person = {"name": "Alice", "age": 30}

# Adding/updating
person["city"] = "NYC"
person["age"] = 31

# Multiple updates
person.update({"job": "Engineer", "country": "USA"})

# Removing
del person["age"]
removed_value = person.pop("job")  # Remove and return value
person.popitem()  # Remove and return arbitrary item
```

### Dictionary Methods

```python
person = {"name": "Alice", "age": 30, "city": "NYC"}

# Keys, values, items
print(person.keys())      # dict_keys(['name', 'age', 'city'])
print(person.values())    # dict_values(['Alice', 30, 'NYC'])
print(person.items())     # dict_items([('name', 'Alice'), ('age', 30), ('city', 'NYC')])

# Iteration
for key in person:
    print(key)

for key, value in person.items():
    print(f"{key}: {value}")

# Membership
print("name" in person)   # True
print("email" in person)  # False

# Copying
person_copy = person.copy()  # Shallow copy
```

### Nested Dictionaries

```python
company = {
    "name": "TechCorp",
    "employees": {
        "alice": {"title": "Engineer", "salary": 100000},
        "bob": {"title": "Designer", "salary": 80000}
    }
}

print(company["employees"]["alice"]["title"])  # Engineer
```

### Dictionary Comprehensions

```python
# Create a dictionary from a range
squares = {x: x**2 for x in range(1, 6)}
print(squares)  # {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}

# Conditional
even_squares = {x: x**2 for x in range(1, 10) if x % 2 == 0}
print(even_squares)  # {2: 4, 4: 16, 6: 36, 8: 64}
```

---

## 12. Sets

### Creating and Basic Operations

Sets are unordered collections of unique elements:

```python
# Creating sets
colors = {"red", "green", "blue"}
numbers = set([1, 2, 3, 2, 1])  # Duplicates removed
empty_set = set()  # Use set(), not {}

# Checking membership
print("red" in colors)  # True
print("yellow" in colors)  # False

# Length and iteration
print(len(colors))  # 3
for color in colors:
    print(color)
```

### Set Operations

```python
set_a = {1, 2, 3, 4}
set_b = {3, 4, 5, 6}

# Union (all elements)
print(set_a | set_b)              # {1, 2, 3, 4, 5, 6}
print(set_a.union(set_b))

# Intersection (common elements)
print(set_a & set_b)              # {3, 4}
print(set_a.intersection(set_b))

# Difference (in set_a but not set_b)
print(set_a - set_b)              # {1, 2}
print(set_a.difference(set_b))

# Symmetric difference (in either but not both)
print(set_a ^ set_b)              # {1, 2, 5, 6}
print(set_a.symmetric_difference(set_b))
```

### Modifying Sets

```python
colors = {"red", "green"}

# Adding elements
colors.add("blue")
colors.update(["yellow", "purple"])  # Add multiple

# Removing elements
colors.discard("red")  # No error if not present
colors.remove("green")  # Error if not present
popped = colors.pop()  # Remove and return arbitrary element

# Clearing
colors.clear()
```

### Set Comprehensions

```python
# Create a set from a range
squares = {x**2 for x in range(1, 6)}
print(squares)  # {1, 4, 9, 16, 25}

# Conditional
evens = {x for x in range(10) if x % 2 == 0}
print(evens)  # {0, 2, 4, 6, 8}
```

### Practical Uses

```python
# Remove duplicates from a list
numbers = [1, 2, 2, 3, 3, 3, 4]
unique = list(set(numbers))

# Check for common elements
list_a = [1, 2, 3, 4]
list_b = [3, 4, 5, 6]
common = set(list_a) & set(list_b)  # {3, 4}

# Check if subset
required_permissions = {"read", "write"}
user_permissions = {"read", "write", "admin"}
print(required_permissions.issubset(user_permissions))  # True
```

---

## 13. Comprehensions

### List Comprehensions

List comprehensions provide a concise way to create lists:

```python
# Basic syntax: [expression for item in iterable]
squares = [x**2 for x in range(1, 6)]
print(squares)  # [1, 4, 9, 16, 25]

# With condition
evens = [x for x in range(10) if x % 2 == 0]
print(evens)  # [0, 2, 4, 6, 8]

# With transformation
words = ["apple", "banana", "cherry"]
uppercase = [word.upper() for word in words]
print(uppercase)  # ['APPLE', 'BANANA', 'CHERRY']

# Nested comprehension
matrix = [[j for j in range(3)] for i in range(3)]
print(matrix)
# [[0, 1, 2], [0, 1, 2], [0, 1, 2]]

# Multiple conditions
numbers = [x for x in range(20) if x % 2 == 0 if x % 3 == 0]
print(numbers)  # [0, 6, 12, 18]
```

### Dictionary Comprehensions

```python
# Basic syntax: {key: value for item in iterable}
squares = {x: x**2 for x in range(1, 6)}
print(squares)  # {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}

# From two lists
keys = ["a", "b", "c"]
values = [1, 2, 3]
mapping = {k: v for k, v in zip(keys, values)}
print(mapping)  # {'a': 1, 'b': 2, 'c': 3}

# With condition
even_squares = {x: x**2 for x in range(1, 10) if x % 2 == 0}
print(even_squares)  # {2: 4, 4: 16, 6: 36, 8: 64}

# Invert keys and values
original = {"a": 1, "b": 2, "c": 3}
inverted = {v: k for k, v in original.items()}
print(inverted)  # {1: 'a', 2: 'b', 3: 'c'}
```

### Set Comprehensions

```python
# Basic syntax: {expression for item in iterable}
unique_lengths = {len(word) for word in ["apple", "pie", "banana", "cat"]}
print(unique_lengths)  # {3, 4, 6}

# With condition
large_squares = {x**2 for x in range(1, 10) if x > 5}
print(large_squares)  # {36, 49, 64, 81}
```

### Generator Expressions

Generator expressions are like list comprehensions but return generators (memory-efficient):

```python
# Syntax: (expression for item in iterable)
squares = (x**2 for x in range(1, 6))
print(type(squares))  # <class 'generator'>

# Convert to list to see values
print(list(squares))  # [1, 4, 9, 16, 25]

# Use in a loop
for square in (x**2 for x in range(1, 6)):
    print(square)

# Memory-efficient sum
total = sum(x**2 for x in range(1000000))
```

---

## 14. Scope and Closures

### Variable Scope

Python has four scope levels (LEGB rule):

```python
# Global scope
global_var = "I'm global"

def outer():
    # Enclosing scope
    enclosing_var = "I'm enclosing"
    
    def inner():
        # Local scope
        local_var = "I'm local"
        
        # Can access all scopes
        print(local_var)       # From local
        print(enclosing_var)   # From enclosing
        print(global_var)      # From global
    
    inner()

outer()

# Built-in scope (always available)
print(len([1, 2, 3]))  # len is built-in
```

### Local vs Global Variables

```python
x = "global"

def function():
    # This creates a new local variable, doesn't modify global
    x = "local"
    print(x)  # local

print(x)  # global

# To modify a global variable inside a function:
x = "global"

def modify_global():
    global x
    x = "modified"

modify_global()
print(x)  # modified
```

### Nonlocal Variables

The `nonlocal` keyword allows modifying variables in enclosing scopes:

```python
def outer():
    x = "outer value"
    
    def inner():
        nonlocal x  # Reference the variable from enclosing scope
        x = "modified in inner"
    
    print(x)  # outer value
    inner()
    print(x)  # modified in inner

outer()
```

### Closures

A closure is a function that captures variables from its enclosing scope:

```python
def make_multiplier(factor):
    # factor is captured in the closure
    def multiplier(x):
        return x * factor
    return multiplier

times_three = make_multiplier(3)
print(times_three(4))   # 12
print(times_three(10))  # 30

times_five = make_multiplier(5)
print(times_five(4))    # 20

# Each closure maintains its own captured variables
print(times_three(4))   # Still 12
```

### Practical Closure Example

```python
def create_counter():
    count = 0
    
    def increment():
        nonlocal count
        count += 1
        return count
    
    return increment

counter = create_counter()
print(counter())  # 1
print(counter())  # 2
print(counter())  # 3

# Each counter is independent
counter2 = create_counter()
print(counter2())  # 1
print(counter())   # Still 4
```

### Understanding `__closure__`

```python
def outer(x):
    def inner():
        return x * 2
    return inner

func = outer(10)
print(func())  # 20

# Inspect the closure
print(func.__closure__)  # Shows the captured variables
print(func.__closure__[0].cell_contents)  # 10
```

---

## 15. Classes and OOP

### Defining a Simple Class

```python
class Dog:
    # Class attribute (shared by all instances)
    species = "Canis familiaris"
    
    # Constructor
    def __init__(self, name, age):
        # Instance attributes
        self.name = name
        self.age = age
    
    # Instance method
    def bark(self):
        return f"{self.name} says: Woof!"
    
    # Another method
    def describe(self):
        return f"{self.name} is {self.age} years old"

# Creating instances
dog1 = Dog("Buddy", 3)
dog2 = Dog("Max", 5)

print(dog1.name)         # Buddy
print(dog1.bark())       # Buddy says: Woof!
print(dog1.describe())   # Buddy is 3 years old

print(Dog.species)       # Canis familiaris
print(dog1.species)      # Canis familiaris (accessed through instance)
```

### String Representation

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    # String representation for developers
    def __repr__(self):
        return f"Dog(name='{self.name}', age={self.age})"
    
    # String representation for users
    def __str__(self):
        return f"{self.name} ({self.age} years old)"

dog = Dog("Buddy", 3)
print(repr(dog))   # Dog(name='Buddy', age=3)
print(str(dog))    # Buddy (3 years old)
print(dog)         # Buddy (3 years old)
```

### Inheritance

```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def make_sound(self):
        return "Some sound"

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)  # Call parent constructor
        self.breed = breed
    
    def make_sound(self):  # Override parent method
        return f"{self.name} barks"

class Cat(Animal):
    def make_sound(self):
        return f"{self.name} meows"

dog = Dog("Buddy", "Golden Retriever")
cat = Cat("Whiskers")

print(dog.make_sound())  # Buddy barks
print(cat.make_sound())  # Whiskers meows
print(dog.breed)         # Golden Retriever
```

### Polymorphism

```python
class Shape:
    def area(self):
        raise NotImplementedError

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    
    def area(self):
        import math
        return math.pi * self.radius ** 2

# Polymorphism in action
shapes = [Rectangle(5, 4), Circle(3)]
for shape in shapes:
    print(f"Area: {shape.area()}")
```

### Private and Protected Attributes

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance  # Private (name mangling)
        self._pin = "1234"        # Protected (convention)
    
    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
    
    def get_balance(self):
        return self.__balance

account = BankAccount(1000)
account.deposit(500)
print(account.get_balance())  # 1500

# Can't access __balance directly (it's private)
# print(account.__balance)  # Error
# But Python does allow access through name mangling:
print(account._BankAccount__balance)  # 1500
```

### Class Methods and Static Methods

```python
class MathUtils:
    pi = 3.14159
    
    @staticmethod
    def add(a, b):
        """Static method - doesn't need self or cls"""
        return a + b
    
    @classmethod
    def create_from_angle(cls, angle_deg):
        """Class method - receives the class as first argument"""
        angle_rad = angle_deg * cls.pi / 180
        return angle_rad

# Using static method
print(MathUtils.add(5, 3))  # 8

# Using class method
result = MathUtils.create_from_angle(180)
print(result)  # ~3.14159
```

---

## 16. Iterators and Generators

### Understanding Iterators

An iterator is an object that can be iterated over using a loop:

```python
# Lists are iterators
my_list = [1, 2, 3]
iterator = iter(my_list)

print(next(iterator))  # 1
print(next(iterator))  # 2
print(next(iterator))  # 3
# print(next(iterator))  # StopIteration error

# Custom iterator class
class CountUp:
    def __init__(self, max):
        self.max = max
        self.current = 0
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.current < self.max:
            self.current += 1
            return self.current
        else:
            raise StopIteration

for num in CountUp(3):
    print(num)  # 1, 2, 3
```

### Generator Functions

Generators are functions that yield values one at a time:

```python
def countdown(n):
    while n > 0:
        yield n
        n -= 1

# The function returns a generator object
gen = countdown(3)
print(type(gen))  # <class 'generator'>

# Using next()
print(next(gen))   # 3
print(next(gen))   # 2
print(next(gen))   # 1

# Or use in a loop
for num in countdown(3):
    print(num)  # 3, 2, 1
```

### yield vs return

```python
# Regular function
def regular_countdown(n):
    while n > 0:
        print(f"Computing {n}")
        n -= 1
    return "Done"

# Calling immediately executes
result = regular_countdown(3)
print(result)

# Generator function
def lazy_countdown(n):
    while n > 0:
        print(f"Computing {n}")
        yield n
        n -= 1

# Calling creates a generator, doesn't execute yet
gen = lazy_countdown(3)

# Execution happens as you iterate
print(next(gen))  # Prints "Computing 3", yields 3
print(next(gen))  # Prints "Computing 2", yields 2
```

### Generator Expressions

```python
# Memory efficient: doesn't create a list
gen = (x**2 for x in range(1000000))

# Only computes squares as needed
print(next(gen))  # 0
print(next(gen))  # 1
print(next(gen))  # 4

# Compare with list comprehension (creates entire list in memory)
big_list = [x**2 for x in range(1000000)]
```

### Practical Generator Examples

```python
# Reading a large file line by line
def read_large_file(file_path):
    with open(file_path) as f:
        for line in f:
            yield line.strip()

# for line in read_large_file("huge_file.txt"):
#     process(line)

# Fibonacci sequence
def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

print(list(fibonacci(5)))  # [0, 1, 1, 2, 3]

# Infinite sequence
def infinite_counter(start=0):
    count = start
    while True:
        yield count
        count += 1

counter = infinite_counter()
print(next(counter))  # 0
print(next(counter))  # 1
print(next(counter))  # 2
```

### Generator with send()

```python
def receiver():
    print("Ready to receive")
    value = yield
    print(f"Received: {value}")

gen = receiver()
next(gen)           # Start the generator
gen.send("Hello")   # Send a value

# More practical example
def echo_back():
    value = None
    while True:
        value = yield value

gen = echo_back()
next(gen)           # Prime the generator
print(gen.send(5))  # 5
print(gen.send(10)) # 10
```
