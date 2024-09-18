# Documentation Strings

Documentation strings, or docstrings, are strings enclosed in triple double quotation marks (`"""`) or triple single 
quotation marks (''') that appear on the first line of any function, class, method, or module:

If the implementation is straightforward, then you can use a one-line docstring, where you can keep the whole docstring 
on the same line:

```python
def hello() -> None:
    """Prints a greeting."""
    print('Hello!')
```

For more complex functions, classes, or modules, you can use a multi-line docstring. The first line should be a **short
description** of the object, followed by a blank line, and then a more **detailed description**. The detailed description can
include information about the object's purpose, behavior, and usage.

You can use [Markdown](https://www.markdownguide.org/) syntax in docstrings to format text, add links, and include code snippets.

You should also use **[type hints](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html)** to document types for parameters, attributes, and return value, and **[Sphinx-style tags](https://sphinx-rtd-tutorial.readthedocs.io/en/latest/docstrings.html)** (e.g., `:param X:`, `:returns:`) to describe parameters, attributes, return value, and exceptions. Example:

```python
def divide(a: float, b: float) -> float:
    """
	Divide the dividend by the divisor.

	Uses the builtin Python division operator to divide the dividend by the
	divisor. It works for both positive and negative numbers.
	
	:param a: Dividend, i.e., the number to be divided.
	:param b: Divisor, i.e., the number to divide by.
	:return: The result of the division.
	:raises ZeroDivisionError: If the divisor is zero.
	"""
	if b == 0:
		raise ZeroDivisionError()
    return a / b
```

The main takeaway is that docstrings are a structured approach to documenting your Python code. You should write them 
for **all public modules, functions, classes, and methods**.

In a class, attributes should be declared together with their types, and a brief description of their purpose. Example:

```python
class Person:
	"""Represent a person in the system."""

	given_name: str
	"""The person's given name, i.e., first name."""
	surname: str
	"""The person's surname, i.e., last name."""
```

## Full example

Here is a full example of a Python module with a function and a class, along with
docstrings, type hints, and Sphinx-style tags:

```python
"""
This script simulates a bank account and is used as an example
for coding style and documentation.
"""


class BankAccount:
    """
    A bank account with withdrawal and balance inquiry
    functionalities.

    This class enforces minimum balance restrictions and provides
    methods to manage account funds.
    """

    balance: float
    """Current balance in the account."""

    minimum_balance: float
    """Minimum balance required to maintain the account."""

    def __init__(self, balance: float = 0, min_balance: float = 0) -> None:
        """
        Initializes the bank account with the specified balance and
        minimum balance.
        """
        self.balance = balance
        self.minimum_balance = min_balance

    def withdraw(self, amount: float) -> str:
        """
        Withdraws the specified amount from the account, 
        subject to minimum balance requirements.
        
        Example:

            account = BankAccount(150.00, 25.00)
            account.withdraw(20.00)  # No errors, balance becomes 130.00
            account.withdraw(150.00)  # Raises ValueError (insufficient funds)

        :param amount: The amount to withdraw (must be positive).
        :return: Message confirming the withdrawal.
        :raises ValueError: If the withdrawal amount is non-positive.
        :raises ValueError: If the withdrawal would cause the balance to
                fall below the minimum balance.
        """
        if amount <= 0:
            raise ValueError("Withdrawal amount must be positive.")

        if self.balance - amount < self.minimum_balance:
            raise ValueError("Insufficient funds to withdraw.")
        self.balance -= amount
        return f"Resulting balance is: ${self.balance}"

    def add(self, amount: float) -> str:
        """
        Adds the specified amount from the account,
        subject to minimum balance requirements.

        Example:

            account = BankAccount(150.00, 25.00)
            account.add(20.00)  # No errors, balance becomes 170.00

        :param amount: The amount value to add (must be positive).
        :return: Message confirming the deposit amount value.
        :raises ValueError: If the amount is non-positive.
        """
        if amount <= 0:
            raise ValueError("Add amount must be positive.")

        self.balance += amount
        return f"Resulting balance is: ${self.balance}"


def main():
    """
    Main function to demonstrate the BankAccount class.
    """
    account = BankAccount(150.00, 25.00)
    print(account.withdraw(20.00))
    print(account.withdraw(150.00))


if __name__ == "__main__":
    main()
```