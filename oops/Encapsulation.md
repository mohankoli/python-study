# Encapsulation — BankAccount Example
Encapsulation means wrapping data and methods together inside a class and restricting direct access to the data.

## Problem

Create a `BankAccount` class that:

- Stores the account balance.
- Provides a `deposit()` method to add money.
- Provides a `get_balance()` method to return the current balance.
- Create an account with an initial balance of `10000`.
- Deposit `5000` and print the updated balance.

## Solution

```python
class BankAccount:
    def __init__(self, balance):
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount

    def get_balance(self):
        return self.balance


account = BankAccount(10000)
account.deposit(5000)

print(account.get_balance())
```

## Output

```text
15000
```

## Key Point

In this example, `balance` is directly accessible:

```python
print(account.balance)
```

So this is **not complete data hiding**.

For encapsulation/data hiding, use a private attribute:

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance

    def deposit(self, amount):
        self.__balance += amount

    def get_balance(self):
        return self.__balance
```

Here, `__balance` is private through Python's **name mangling** mechanism.
