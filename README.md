# Python Concepts and Examples

This README file provides an overview of various Python concepts and examples to help you prepare for your day 2 prep and beyond.

## String Manipulation

- **Reverse a String**: Reverse a string without using any built-in method.
    ```python
    str1 = 'Rahul'
    str2 = ''
    for i in str1:
        str2 = i + str2

    print('str1 is', str1)
    print('str2 is', str2)
    ```

- **Split and Join a String**: Split a string by spaces and join it back.
    ```python
    str1 = 'Rahul'
    result = str1.split(' ')
    res = ''.join(result)
    print(res)
    print(result)
    ```

## List Operations

- **Sort a List**: Sort a list of numbers.
    ```python
    lst = [1, 5, 0, 7, 6, 3, 2]
    lst.sort()
    print(lst)
    ```

- **Clear a List**: Clear all elements from a list.
    ```python
    lst = [1, 5, 0, 7, 6, 3, 2]
    lst.clear()
    print(lst)
    ```

- **Reverse a List**: Reverse a list using slicing.
    ```python
    lst = [1, 5, 0, 7, 6, 3, 2]
    rev = lst[::-1]
    print(rev)
    ```

- **Concatenate Two Lists**: Combine two lists element-wise.
    ```python
    lst1 = ['W', 'a', 'w', 'b']
    lst2 = ['e', ' ', 'riting', 'log']
    result = [x + y for x, y in zip(lst1, lst2)]
    print(result)
    ```

- **Square Each Element in a List**: Square each element in a list using different methods.
    - Method 1:
        ```python
        lst = [1, 5, 0, 7, 6, 3, 2]
        result = map(lambda x: x * x, lst)
        print(list(result))
        ```

    - Method 2:
        ```python
        lst = [1, 5, 0, 7, 6, 3, 2]
        print([i * i for i in lst])
        ```

- **Find Odd Numbers Using List Comprehension**: Identify odd numbers in a list using list comprehension.
    ```python
    x = [1, 5, 4, 3, 2]
    print([i for i in x if i % 2 != 0])
    ```

- **Minimum Value in a List Using Lambda Function**: Find the minimum value in a list using a lambda function.
    ```python
    x = [1, 5, 4, 3, 2]
    print(min(x, key=lambda x: x))
    ```

- **Convert List of Characters to a String of Characters**: Convert a list of characters into a single string.
    ```python
    lst = ['My', 'name', 'is', 'Rahul', 'Kumar']
    print(','.join(lst))
    ```

## Dictionary and Data Types

- **Dictionary vs. Ordered Dictionary**:
    - Regular dictionary: Order of elements is maintained by the hash value of keys.
    - OrderedDict: Uses a doubly linked list to maintain the order of elements.

- **Set vs. Frozenset**:
    - Set is a mutable object.
    - Frozenset is an immutable object.

- **Tuple Type Checker**:
    ```python
    i = 1, 2, 4, 5, 8
    k = (1, 2, 4, 5, 8)
    print(type(k))
    ```

## Functions and Keywords

- **Factorial Using Recursion**:
    ```python
    def fact(n):
        if n == 1:
            return n
        else:
            return n * fact(n - 1)

    print(fact(6))
    ```

- **Use of Continue Keyword**: Skip even numbers and print odd numbers.
    ```python
    lst = [1, 5, 0, 7, 6, 3, 2]
    for i in lst:
        if i % 2 == 0:
            continue
        print(f'odd number {i}')
    ```

- **Use of Assignment Expressions (:=) in Python**: Example of using the "walrus operator".
    ```python
    names = ["Jacob", "Joe", "Jim"]

    if (name := input("Enter a name: ")) in names:
        print(f"Hello, {name}!")
    else:
        print("Name not found.")
    ```

## Python File Types

- **.py vs. .pyc**:
    - `.py`: Contains source code.
    - `.pyc`: Contains bytecode.
    - Process:
        - Python program is executed.
        - Python interpreter checks for compiled files.
        - If `.pyc` file is found, Python virtual machine executes it.
        - If not found, checks for `.py` file, compiles it into `.pyc`, and then executes it.

## Stateful vs. Stateless

- **Stateful**:
    - Stores authorization information on the server side.

- **Stateless**:
    - Stores authorization information on the client side along with a signature in the form of a token.

## Day 2 Prep

### Compiler vs. Interpreter

- **Compiler**:
    - Translates source code into machine code.

- **Interpreter**:
    - In Python, source code (`.py`) is compiled into bytecode (`.pyc`), stored in the directory named `__pycache__`.
    - Python interpreter (also known as Python virtual machine) reads bytecode and translates it into machine code.
    - Python is an interpreted language.

### What is Garbage Collector in Python?

- **Garbage Collector**:
    - Removes unused memory from Python's private heap space, freeing up memory for heap space.
    - Has two components:
        - **Reference Count**:
            - When objects are assigned to a variable, the reference count increases.
            - When references or objects are deleted, the reference count decreases.
            - When the reference count equals zero, the memory is released immediately.
        - **Cyclic Garbage Collection**:
            - Handles memory cleanup for circular references.

### Module vs. Package

- **Module**:
    - A file containing Python code and executable code (`.py`).
    - Modules can be imported using `import`.

- **Package**:
    - A collection of modules.
    - If a directory contains an `__init__.py` file, it is considered a Python package.

### Built-In Data Types in Python

- **Numeric Types**:
    - `int`: Integer values (both positive and negative).
    - `float`: Floating-point numbers (decimal numbers).
    - `complex`: Complex numbers (real and imaginary parts).

- **Sequence Types**:
    - `str`: Strings (sequences of characters).
    - `list`: Lists (ordered sequences of elements).
    - `tuple`: Tuples (ordered, immutable sequences of elements).

- **Mapping Type**:
    - `dict`: Dictionaries (collections of key-value pairs).

- **Set Types**:
    - `set`: Sets (unordered collections of unique elements).
    - `frozenset`: Immutable sets (unordered collections of unique elements).

- **Boolean Type**:
    - `bool`: Boolean values (True or False).

- **Binary Types**:
    - `bytes`: Sequences of bytes (immutable).
    - `bytearray`: Sequences of bytes (mutable).
    - `memoryview`: Views of an array's data in memory.

- **None Type**:
    - `None`: Represents a null or absent value.

### Sort List Without Using Built-In Method

- **Bubble Sort**:
    ```python
    def bubble_sort(arr):
        n = len(arr)
        for i in range(n):
            swapped = False
            for j in range(0, n - i - 1):
                if arr[j] > arr[j + 1]:
                    # Swap the elements if they are in the wrong order
                    arr[j], arr[j + 1] = arr[j + 1], arr[j]
                    swapped = True
            # If no elements were swapped, the list is already sorted
            if not swapped:
                break
        return arr

    my_list = [5, 2, 9, 1, 7]
    bubble_sort(my_list)
    print(my_list)  # Output: [1, 2, 5, 7, 9]
    ```

### Join Method in Python

- **Join Method**:
    - Converts a list or tuple into a string.
    ```python
    elements = ['Hello', 'World']
    result = ' '.join(elements)
    print(result)  # Output: "Hello World"
    ```

### Lambda Function That Takes Any Number of Arguments

- **Example**:
    ```python
    lam = lambda *args: ''.join(args)
    print(lam("Hello", " ", "World"))  # Output: "Hello World!"
    ```

