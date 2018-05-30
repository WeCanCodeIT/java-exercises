# Bank Teller

## Objective

Design a `BankAccount` class that will perform capabilities of a single Bank Account, a `Bank` class that will house multiple accounts, and a `BankingApp` (with a `main` method) to build a user interface where your user can access your accounts and perform banking transactions.

### Tasks

Your `BankAccount` Class should have:

*   3 instance variables to handle `String accountNum`, `String type`, and `double balance`
*   Note the `accountNum` will be a **unique identifier**
*   Create a constructor
*   Pass 3 corresponding pieces of data in the order mentioned above to your constructor
*   Create accessor methods for each instance variable in `BankAccount`

Your `Bank` Class should have:

*   A `Map` called `bankAccounts`
*   A method with the signature `public Collection<BankAccount> getAccounts()` to return **all** accounts
*   A method with the signature `public void addAccount()` to add a `BankAccount`
*   A method with the signature `public BankAccount getBankAccount(String acctNum)` to get access a particular `BankAccount`
*   A method with the signature `public void closeBankAccount(String acctNum)` to close a particular `BankAccount`

Hint: This Class operates like a bank and keeps track of multiple bank accounts.

Your `BankingApp` should have:

*   A `Bank` object called `myBank`
*   A `BankAccount` object called `account1` with the following properties `("1111","Checking",500.00)`
*   A `BankAccount` object called `account2` with the following properties `("2222","Savings",2500.00)`
*   Add your `BankAccount`s to `myBank`s Map
*   Set up a UI to give the user the ability to interact with the application similar to the example below:

### Sample Output

```
Here are your accounts at our bank:
Checking 500.0
Savings 100.0

What would you like to do?
Press 1 to deposit
Press 2 to withdrawal
Press 3 to check balance
Press 4 to close an account
Press 0 to exit

1
You want to deposit.

Here are your accounts
(1111) Checking 500.0
(2222) Savings 100.0

Select the account by (acct num) to perform this transaction.

1111
You have selected 1111
Enter the amount to deposit:

2000
You deposited 2000
Your updated balance is now 2500.0

What would you like to do?
Press 1 to deposit
Press 2 to withdrawal
Press 3 to check balance
Press 4 to close an account
Press 0 to exit

4
You would like to close an account.

Here are your accounts
(1111) Checking 2500.0
(2222) Savings 100.0

Enter the account number of the account you would like to close:

2222
You are closing account # 2222
Here are your remaining accounts

(1111) Checking 2500.0

What would you like to do?
Press 1 to deposit
Press 2 to withdrawal
Press 3 to check balance
Press 4 to close an account
Press 0 to exit
...
...
...
```
