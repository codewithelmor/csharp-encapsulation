# Pillars of Object-Oriented Programming (OOP) - Encapsulation

**`Encapsulation`** is one of the four fundamental Object-Oriented Programming (OOP) principles, and it involves bundling the data (attributes) and methods (functions) that operate on the data into a single unit called a class. Access to the data is controlled, and it's usually hidden from the outside world.

Here's a simple example in C#:

```csharp
using System;

class BankAccount
{
    private string accountHolder;
    private double balance;

    // Constructor
    public BankAccount(string accountHolder, double initialBalance)
    {
        this.accountHolder = accountHolder;
        this.balance = initialBalance;
    }

    // Public methods to interact with the encapsulated data
    public void Deposit(double amount)
    {
        if (amount > 0)
        {
            balance += amount;
            Console.WriteLine($"{accountHolder}, deposit: ${amount}. New balance: ${balance}");
        }
        else
        {
            Console.WriteLine("Deposit amount must be greater than zero.");
        }
    }

    public void Withdraw(double amount)
    {
        if (amount > 0 && amount <= balance)
        {
            balance -= amount;
            Console.WriteLine($"{accountHolder}, withdrawal: ${amount}. New balance: ${balance}");
        }
        else
        {
            Console.WriteLine("Invalid withdrawal amount or insufficient funds.");
        }
    }

    public double GetBalance()
    {
        return balance;
    }
}

class Program
{
    static void Main()
    {
        // Create a BankAccount object
        BankAccount account = new BankAccount("John Doe", 1000);

        // Access encapsulated data through public methods
        account.Deposit(500);
        account.Withdraw(200);

        double currentBalance = account.GetBalance();
        Console.WriteLine($"Current balance: ${currentBalance}");
    }
}
```

In this example:

* The **`BankAccount`** class encapsulates the **`accountHolder`** and **`balance`** data members, marking them as private. This means that they can only be accessed within the **`BankAccount`** class itself.
* Public methods (**`Deposit`**, **`Withdraw`**, and **`GetBalance`**) are provided to interact with the encapsulated data. These methods perform necessary validations and modifications on the data, ensuring that it is used in a controlled manner.
* The **`Main`** method in the **`Program`** class demonstrates how to create a **`BankAccount`** object and use its public methods to deposit, withdraw, and retrieve the account balance.

Encapsulation helps in hiding the internal details of the implementation, providing a clean and controlled interface for interacting with objects. It also helps in maintaining the integrity of the data by ensuring that it can only be modified through well-defined methods.
