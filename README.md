ATM machine
As owners of AwesomeSuperPuperBank, we want to have a simple prototype of our new ATM machine that allows our customers to:

view their account balance
withdraw money
Our bank already has two clients: Volodymyr and Iryna. We saved their account information in our system (see config.yml). The bank also has liquid assets (i.e. cash) in the amount of ₴337 (in different banknotes) which our ATM machine can operate with.

Use case:
The information about the banknotes in the ATM and all the accounts in the bank is stored in a configuration file:

# config.yml
banknotes:
  500: 0
  200: 0
  100: 2
  50: 1
  20: 2
  10: 4
  5: 1
  2: 0
  1: 2
accounts:
  3321:
    name: 'Volodymyr'
    password: 'mypass'
    balance: 422
  5922:
    name: 'Iryna'
    password: 'ho#ll_§1'
    balance: 5301
We run the app by passing the location of this configuration file as an argument to the program

  ruby atm.rb config.yml
Here’s one of possible application flows:

Please Enter Your Account Number:
> 3321
Enter Your Password:
> mypass

Hello, Volodymyr!

Please Choose From the Following Options:
 1. Display Balance
 2. Withdraw
 3. Log Out

> 1

Your Current Balance is ₴422

Please Choose From the Following Options:
 1. Display Balance
 2. Withdraw
 3. Log Out

> 2

Enter Amount You Wish to Withdraw:
> 100000

ERROR: INSUFFICIENT FUNDS!! PLEASE ENTER A DIFFERENT AMOUNT:
> 420

ERROR: THE MAXIMUM AMOUNT AVAILABLE IN THIS ATM IS ₴337. PLEASE ENTER A DIFFERENT AMOUNT:
> 329

ERROR: THE AMOUNT YOU REQUESTED CANNOT BE COMPOSED FROM BILLS AVAILABLE IN THIS ATM. PLEASE ENTER A DIFFERENT AMOUNT:
> 320

Your New Balance is ₴102

Please Choose From the Following Options:
 1. Display Balance
 2. Withdraw
 3. Log Out

> 1

Your Current Balance is ₴102

Please Choose From the Following Options:
 1. Display Balance
 2. Withdraw
 3. Log Out

> 3

Volodymyr, Thank You For Using Our ATM. Good-Bye!

Please Enter Your Account Number:
> 5922
Enter Your Password:
> 1234567

ERROR: ACCOUNT NUMBER AND PASSWORD DON'T MATCH

Please Enter Your Account Number:
> 5922
Enter Your Password:
> ho#ll_§1

Hello, Iryna!
...
