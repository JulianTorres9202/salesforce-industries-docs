---
title: "InsPolicyBillingService:generateBillingAccountStatements"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicybillingservice__generatebillingaccountstatements.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyBillingService:generateBillingAccountStatements

InsPolicyBillingService:generateBillingAccountStatements[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyBillingService:generateBillingAccountStatements

Use this service to generate statements for accounts that contain policies with billing accounts that have Due Date = today.

We don't recommend that you invoke this service directly. It was created to be invoked by the Generate Billing Account Statements Vlocity Scheduled Job.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Important

This service doesn't work with the FSC Insurance Policy object model.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsPolicyBillingService`

Method: `generateBillingAccountStatements`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes in a list of billing accounts from a Vlocity Scheduled Job.
    
2.  Groups billing accounts by accounts.
    
3.  Retrieves policies associated with the Billing Accounts.
    
4.  Creates a statement for each account:
    
    1.  Sets `RecordType__c` to `Statement`.
        
    2.  Sets `AccountId__c` to the Id of the account.
        
    3.  Sets `DueDate__c` to the value of `BillDueDate__c` of the first billing account in the group.
        
    4.  Sets `StatementDate__c` to the value of `BillDueDate__c`.
        
    5.  Sets `StatementEndDate__c` to the value of `BillDueDate__c`.
        
    6.  Sets `StatementStartDate__c` to the furthest date back specified by the `BillingFrequency__c` values in the billing accounts.
        
    7.  Sets `BalanceDue__c` to the sum of the `AutomaticPaymentAmounts__c` values on the policies associated with the billing accounts.
        
    8.  Sets `PreviousBalance__c` to the sum of the PastDue\_\_c values on the policies associated with the billing accounts.
        
5.  For all policies associated with a specific statement, retrieves all transactions associated with the specified policies that have a `TransactionDate__c` within the statement period start and end date.
    
    If the transaction does not have a value for the `StatementId__c`, set the `StatementId__c` to the Id of the specified Statement.
    
6.  For each billing account:
    
    1.  Sets `AutomaticPaymentAmount__c` to the sum of the `NextPaymentAmountDue__c` values on the policies associated with the billing account.
        
    2.  Sets the new `BillDueDate__c` based on the current `BillDueDate__c` and `BillingFrequency__c`.
        
7.  For each policy associated with a specific billing account:
    
    1.  Sets the `AutomaticPaymentAmountDue__c` to the `NextPaymentAmountDue__c`.
        
    2.  Sets `BillDueDate__c` to the billing account’s updated `BillDueDate__c`.
        

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

This service doesn't take any remote options.

[](https://help.salesforce.com/s?language=en_US)

## Calculating StatementStartDate\_\_c

An account can have multiple policies with direct billing. Each policy may have a different billing frequency (annual, quarterly, monthly, or semi-monthly). `StatementStartDate__c` is determined using the policy’s bill due date and billing frequency to calculate the start date for each policy. then choosing the start date that' furthest back in time.

For example, if an Account has two policies, both with a bill due date of ‘2018-03-31’. Policy 1 has a billing frequency of ‘Monthly’ and Policy 2 has a billing frequency of ‘Quarterly’. Using the bill due date and billing frequency, the start date of Policy 1 would be ‘2018-02-28’ and the start date of Policy 2 would be ‘2018-01-01’. Since the start date of Policy 2 is further back in time, the StatementStartDate\_\_c is set to ‘2018-01-01’.

[](https://help.salesforce.com/s?language=en_US)

## Calculating the new BillDueDate\_\_c

A new BillDueDate\_\_c is calculated based on the current BillDueDate\_\_c and the BillingFrequency\_\_c. Here are the billing frequencies and calculations for the new BillDueDate\_\_c:

-   Annually
    
    Current `BillDueDate__c` plus 1 year
    
-   Quarterly
    
    `BillDueDate__c` can only be 1 of 4 dates: March 31st, June 30th, September 30th, or December 31st. Set `BillDueDate__c` to the next date in the sequence. For example, if it is currently set to currently March 31st, set it to June 30th.
    
-   Monthly
    
    Current `BillDueDate__c` plus 1 month
    
-   Semi-Monthly
    
    -   If current `BillDueDate__c` is the end of the month, set it to the middle of the next month (14th if February, 15th if any other month)
        
    -   If current `BillDueDate__c` is the middle of the month, set it to the end of the month
        

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service expects an input JSON generated by a Vlocity Scheduled Job. This scheduled job will include the following key and their values:

-   `records`: A list of billing accounts selected by the scheduled job
    

```
{
	"records": [{
			"Id": "a3h5A000000Xz7l",
			"AccountId": "0015A000025MuenQAC",
			"BillDueDate__c": "2018-03-31",
			"BillingFrequency__c": "Monthly"
		},
		{
			"Id": "a3h5A000000Xz7m",
			"AccountId": "0015A000025MuenQAC"
			"BillDueDate__c": "2018-03-31",
			"BillingFrequency__c": "Quarterly"
		}
	]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service doesn't return any output JSON.

Did this article solve your issue?

Let us know so we can improve!

YesNo