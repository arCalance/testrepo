# Code Documentation Standards

author: atul rathore; date: July 25, 2022
---
---


## What does this document contain?

This document will define precise definition of the code documentation and within that context, what is the standard to be followed. This, being a generalised document, cannot be templatized as this covers general standard, not specific to one programming platform. 

I'll list down different tools for languages we use and standard in any one of the language in the end as an example.

## What is code documentation?

Code documentation refers to code level documentation (function/class/module levels).

There are 2 parts to this:
- **Code documentation** - docstrings on the function and class/module level
- **API Documentation** - documentation on controllers which documents only the application interfaces

## Standard to be followed

1. **Inline comments:** information that the code itself cannot contain, such as why the code is there.
2. **Method and class comments:**
    - **Method documentation:**  details what arguments the method takes, what it returns, any “gotchas” or restrictions, and what exceptions it can throw or errors it can return
    - **Class / Module documentation:** gives a brief overview of what the class / file / module does and often gives a few short examples of how you might use the class / file / module

Point 1 is developer dependant, ***Point 2 is expected to be followed***.

## Language Standards

Please note that each language has a specific documentation standard already made, which is why we are not forcing you to use any one standard. Python e.g. has pep-008 standard on documentation, similar is the case with most languages.

## Tooling in supported languages

JS, TS, Python, Java, Go are our standard languages. The following lists the tools available on these languages.

- Javascript - [JSDoc](https://jsdoc.app)
- Typescript - [JSdoc, Typedoc](https://typedoc.org)
- Java - [Javadoc](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/javadoc.html)
- Python - [Sphinx, Mkdocs](https://realpython.com/python-project-documentation-with-mkdocs)
- Go - [GoDoc](https://pkg.go.dev/golang.org/x/tools/cmd/godoc)

## Standard Docstring Example (Translates to other languages)
<br>

### The bold points are to be templatized in respective lanagues.
<br>

The following example is a ***method docstring*** which lists following information:
- **params**
- **returns**
- **types** (for both)
- **description**
- **example** (**working and error** example)
- (optional) any gotchas, special cases
- (optional) error exceptions

```
def add(a, b):
    """Compute and return the sum of two numbers.

    Examples:
        >>> add(4.0, 2.0)
        6.0
        >>> add(4, 2)
        6.0

        >>> add('Hello', 'World')
        The args are not numbers

    Args:
        a (float): A number representing the first addend in the addition.
        b (float): A number representing the second addend in the addition.

    Returns:
        float: A number representing the artihmetic sum of `a` and `b`.
    """
    return float(a + b)
```

***Following is a module/Class example:***
- **Overview** of the module/ class
- **Examples** for usage
- **Public Methods available**

```
# calculator/calculations.py

"""Provide several sample math calculations.

This module allows the user to make mathematical calculations.

Examples:
    >>> from calculator import calculations
    >>> calculations.add(2, 4)
    6.0
    >>> calculations.multiply(2.0, 4.0)
    8.0
    >>> from calculator.calculations import divide
    >>> divide(4.0, 2)
    2.0

The module contains the following functions:

- `add(a, b)` - Returns the sum of two numbers.
- `subtract(a, b)` - Returns the difference of two numbers.
- `multiply(a, b)` - Returns the product of two numbers.
- `divide(a, b)` - Returns the quotient of two numbers.
"""
```
