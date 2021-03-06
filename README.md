# Banking_System
 create a Banking System

 create the following Schemas

// add timestamps for everything

- User
    - firstName (required)
    - middleName (optional)
    - lastName (required)
    - age (required)
    - email (required )
    - address ( required )
    - gender ( optional and should default to Female )
    - type (optional and it can take value of customer or employee and if not provided then default to customer )


 - BranchDetail
    - name (required)
    - address (required)
    - IFSC (required and string)
    - MICR (required and number )


 - MasterAccount
    - balance (required) This is the total balance that the person has in the bank
  

- SavingsAccount
    - account_number ( required and should be unique)
    - balance ( required )
    - interestRate ( required )
  

- FixedAccount
    - account_number ( required and should be unique)
    - balance ( required )
    - interestRate ( required )
    - startDate ( required )
    - maturityDate (required )


Now you need to connect the below account and put the necessary foreign key fields in the Schemas

1) User & MasterAccount ( Hint :- we will assume that 1 user can have only 1 master account )
2) User & MasterAccount ( Hint :- every account will also be assigned a manager/employee)
3) BranchDetail & MasterAccount ( Hint :- 1 masteraccount can only be in 1 branch )
4) MasterAccount & SavingsAccount ( Hint :- a User can have multiple SavingsAccount in the bank 
5) MasterAccount & FixedAccount ( Hint :- a User can have multiple FixedAccount 


After completing the above database design you need to perform the following tasks

1) GET API to get all the details of the master account ( here you will get the complete detail of the master account collection along with the full user detail )

2) POST API for the user to create a SavingsAccount

3) POST API for the user to create a FixedAccount

NOTE :- for 2 and 3 you also need to update balance in master account so don't forget that

4) GET API that takes the master account id and returns a list of all the accounts that the user has but only the account_number and balance 

5) DELETE API for fixed account and here the user is closing the account before maturityDate so in that case there will be a 2% interest penalty on the time till maturity and then the remaining money will be refunded ( for e.g :- User created an FD of Rs.1000 on Jan 1 and if he decides to close his account on Sep 15 so you will first calculate the interest earned from Jan 1 to Sep 15  lets say that is Rs.40 and then there will be a 2% interest penalty on the time from Sep 15 to Dec 31 lets say that is Rs.3 and then the total interest payment due is Rs. 37 and the deposit of Rs.1000 so the user will get Rs.1037)

6) POST API that will on maturity transfer the balance of FixedAccount to the SavingsAccount
