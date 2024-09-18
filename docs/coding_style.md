# Best Practices to Code in Python - User Guide

## Coding Style convention

#### This documment aims to guide the use with best practices to write a Python code within _PEP8 (Python Enhancement Proposal 8)_ compliance.

## Writing Python code according to PEP8

* Use 4 spaces to indentation
* Limit the lines with 79 characters of length
* Use blank spaces  around of operators
* Name variables and functions using `snake_case` and `CamelCase` for class names

## Naming Styles

The table below outlines some of the common naming styles in Python code and when you should use them.
But in order to write readable code, you still have to be careful with your choice of letters and words.

| *Type*   | *Naming Convention*                                                                                                           | *Examples*                                            |
|----------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| function | Use a lowercase word or words. Separate words by underscores to improve readability.                                          | `function`, `python_function`                         |
| Variable | Use a lowercase single letter, word, or words. Separate words with underscores to improve readability.                        | `x`, `var`, `python_variable`                         |
| Class    | Start each word with a capital letter. Don’t separate words with underscores. This style is called camel case or Pascal case. | `Model`, `PythonClass`                                |
| Method   | Use a lowercase word or words. Separate words with underscores to improve readability.                                        | `class_method`, `method`                              |
| Constant | Use an uppercase single letter, word, or words. Separate words with underscores to improve readability.                       | `CONSTANT`, `PYTHON_CONSTANT`, `PYTHON_LONG_CONSTANT` |
| Module   | Use a short, lowercase word or words. Separate words with underscores to improve readability.                                 | `module.py`, `python_module.py`                       |
| Package  | Use a short, lowercase word or words. Don’t separate words with underscores.                                                  | `package`, `pythonpackage`                            |


### How Choose the Names

When naming variables, you may be tempted to choose simple, single-letter lowercase names, like `x`. But unless you’re 
using `x` as the argument of a mathematical function, it’s not clear what `x` represents. The best way to name your objects 
in Python is to use descriptive names to make it clear what the object represents.

### Examples

**_Example 1:_**

_Instead of doing this:_
```python
x = "Jander Junior"
y, z = x.split()
print(f"{z}, {y}")
'Junior, Jander'
```

This will work, but you’ll have to keep track of what `x`, `y`, and `z` represent. It may also be confusing for collaborators. 
A much clearer choice of names would be something like this:

```python
name = "Jander Junior"
first_name, last_name = name.split()
print(f"{last_name}, {first_name}")
'Junior, Jander'
```

**_Example 2:_**

_Instead of doing this:_
```python
def db(x):
    return x * 2
```

The name `db()` could be an abbreviation for double. But imagine coming back to this code in a few days. You
may have forgotten what you were trying to achieve with this function, and that would make guessing how you
abbreviated it difficult.

The following example is much clearer. If you come back to this code a couple of days after writing it,
you’ll still be able to read and understand the purpose of this function:

```python
def multiply_by_two(x):
    return x * 2
```

## Blank Lines

Vertical whitespace, or blank lines, can greatly improve the readability of your code. But many blank lines in your code 
makes it look very sparse, and the reader might need to scroll more than necessary. Below are three key guidelines on 
how to use vertical whitespace.

### Surround top-level functions and classes with two blank lines.

```python
class FirstClass:
    pass


class SecondClass:
    pass


def top_level_function():
    return None
```

### Surround method definitions inside classes with a single blank line.

```python
class ClassWithMethods:
    def first_method(self):
        return None

    def second_method(self):
        return None
```

### Use blank lines sparingly inside functions to show clear steps.

```python
def calculate_variance(numbers):
    sum_numbers = 0
    for number in numbers:
        sum_numbers = sum_numbers + number
    mean = sum_numbers / len(numbers)

    sum_squares = 0
    for number in numbers:
        sum_squares = sum_squares + number**2
    mean_squares = sum_squares / len(numbers)

    return mean_squares - mean**2
```

## Block Comments

**_PEP 8 provides the following rules for writing block comments:_**

* Indent block comments to the same level as the code that they describe.
* Start each line with a `#` followed by a single space.
* Separate paragraphs by a line containing a single `#`.


Here’s a block comment explaining the function of a `for` loop. Note that the sentence wraps to a new line to preserve the 
79-character line limit:

```python
for number in range(0, 10):
    # Loop over `number` ten times and print out the value of `number`
    # followed by a newline character.
    print(number, "\n")
```
