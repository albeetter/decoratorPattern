
# CIMB Banking System - Decorator Pattern

# Problem Statement

CIMB is a digital bank that offers GSave and UpSave savings accounts. As with a typical Savings Account, it contains accountNumber, accountName, and a balance for that account.

The typical savings account offers an interest rate of 1%.
The benefits of the typical savings account is the same with the "Standard Savings Account" as compared to other banks.

The GSave account offers an interest rate of 2.5%.
Benefits include the "Standard Savings Account" plus access to "GCash transfer".

The UpSave account offers the highest interest rate of 4.0%.
Benefits include the "Standard Savings Account" plus "with Insurance".

Develop a decorator pattern approach that will implement the given UML diagram:

Cimb.java Content (Must NOT be Modified Except Package Name)
public class Cimb {

    public static void main(String[] args) {
        
        SavingsAccount account = new SavingsAccount();
        
        account.setAccountNumber(1234);
        account.setAccountName("Juan Dela Cruz");
        account.setBalance(10000.0);
        
        System.out.println(account.showInfo());
        System.out.println("Account type: " + account.showAccountType());
        System.out.println("Interest rate: " + account.getInterestRate());
        System.out.println("New balance: " + account.computeBalanceWithInterest());
        System.out.println("Benefits: " + account.showBenefits());
        
        System.out.println("----------------------");
        
        GSave gSave = new GSave(account);
        System.out.println(gSave.showInfo());
        System.out.println("Account type: " + gSave.showAccountType());
        System.out.println("Interest rate: " + gSave.getInterestRate());
        System.out.println("New balance: " + gSave.computeBalanceWithInterest());
        System.out.println("Benefits: " + gSave.showBenefits());
        
        System.out.println("----------------------");
        
        UpSave upSave = new UpSave(account);
        System.out.println(upSave.showInfo());
        System.out.println("Account type: " + upSave.showAccountType());
        System.out.println("Interest rate: " + upSave.getInterestRate());
        System.out.println("New balance: " + upSave.computeBalanceWithInterest());
        System.out.println("Benefits: " + upSave.showBenefits());
    }
}

# Expected Output Requirements
<img src="https://github.com/albeetter/decoratorPattern/blob/master/ExpectedOutput.png" alt="expectedoutput">

# Description of the following methods
showAccountType()

Returns "Savings Account", "GSave" or "UpSave"

getInterestRate()

Returns 1% for Savings Account

Returns 2.5% for GSave

Returns 4.0% for UpSave

getBalance()

Returns the balance of the account set.

showBenefits()

"Standard Savings Account" for Savings Account

benefits offered by savings account + "GSave Transfer"

benefits offered by savings account + "With Insurance"

computeBalanceWithInterest()

Returns new balance by computing the balance plus the interest depending on the interest rate.

showInfo()

Returns details of account number, account name, and balance.

# UML Diagram
<img src="https://github.com/albeetter/decoratorPattern/blob/master/DecoratorDiagram.png" alt="classdiagram">
