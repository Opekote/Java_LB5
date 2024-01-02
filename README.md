# Bank System Simulation

This project implements a reliable and error-resistant program simulating a simplified banking system. The system includes functionalities such as creating accounts, financial operations, and account aggregation. The primary goal is to ensure the program elegantly handles various types of errors without breaking.

## Project Structure

### 1. Bank Class

The `Bank` class represents the main banking system and includes a collection of `BankAccount` objects. It provides methods for creating accounts, finding accounts by number, and transferring money between accounts.

#### Methods:

- `createAccount(String accountName, double initialDeposit)`: Creates a new bank account with the given account name and initial deposit. Throws `NegativeAmountException` if the initial deposit is negative.

- `findAccount(int accountNumber)`: Finds and returns a bank account based on the account number. Throws `AccountNotFoundException` if the account is not found.

- `transferMoney(int fromAccountNumber, int toAccountNumber, double amount)`: Transfers money from one account to another. Throws `AccountNotFoundException` if either account is not found, `InsufficientFundsException` if there are insufficient funds, and `NegativeAmountException` if the transfer amount is negative.

### 2. BankAccount Class

The `BankAccount` class represents an individual bank account with attributes such as account number, account name, and balance. It provides methods for depositing, withdrawing, and getting the account summary.

#### Methods:

- `deposit(double amount)`: Deposits the specified amount into the account. Throws `NegativeAmountException` if the deposit amount is negative.

- `withdraw(double amount)`: Withdraws the specified amount from the account. Throws `InsufficientFundsException` if there are insufficient funds, and `NegativeAmountException` if the withdrawal amount is negative.

- `getAccountSummary()`: Returns a string containing the account details.

### 3. Custom Exception Classes

The project includes custom exception classes to handle specialized error scenarios:

- `AccountNotFoundException`: Thrown when attempting to find an account that does not exist.
- `InsufficientFundsException`: Thrown when a financial operation encounters insufficient funds.
- `NegativeAmountException`: Thrown when attempting to perform an operation with a negative amount.

## Testing

The project includes JUnit test classes to simulate various scenarios and validate the handling of exception cases. Each test class focuses on specific exception types:

- `TestAccountNotFoundException`: Tests scenarios related to the `AccountNotFoundException`.
- `TestInsufficientFundsException`: Tests scenarios related to the `InsufficientFundsException`.
- `TestNegativeAmountException`: Tests scenarios related to the `NegativeAmountException`.

Feel free to run these tests to ensure the robustness and correctness of the implemented error-handling mechanisms.

## How to Use

1. Create an instance of the `Bank` class.
2. Use the `createAccount` method to create bank accounts.
3. Use the `findAccount` method to retrieve accounts based on account numbers.
4. Perform financial operations using the `transferMoney`, `deposit`, and `withdraw` methods.
