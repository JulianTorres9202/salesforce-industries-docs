---
title: "InsPolicyBillingService:generateDirectBillingStatements"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicybillingservice__generatedirectbillingstatements.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyBillingService:generateDirectBillingStatements

InsPolicyBillingService:generateDirectBillingStatements[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyBillingService:generateDirectBillingStatements

Use this service to generate statements for accounts containing policies with direct billing whose due date is equal to today's date plus ten (10) days.

We don't recommend that you invoke this service directly. It was created to be invoked by the Generate Direct Billing Statements Vlocity Scheduled Job.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Important

This service doesn't work with the FSC Insurance Policy object model.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsPolicyBillingService`

Method: `generateDirectBillingStatements`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes in a list of policies from a Vlocity Scheduled Job.
    
2.  Groups policies by account and creates a statement for each account:
    
    1.  Sets `RecordType` to `Bill`.
        
    2.  Sets `AccountId__c` to the Id of the account.
        
    3.  Sets `DueDate__c` to the `BillDueDate__c` of the first policy in the group.
        
    4.  Sets `StatementDate__c` to the `BillDueDate__c` minus 10 days.
        
    5.  Sets `StatementEndDate__c` to the `BillDueDate__c` minus 10 days.
        
    6.  Sets `StatementStartDate__c` to the furthest date back, specified by the `BillingFrequency__c` values in the policies.
        
    7.  Sets `BalanceDue__c` as the sum of the `AutomaticPaymentAmount__c` values on the policies.
        
    8.  Sets `PreviousBalance__c` as the sum of the `PastDue__c` values on the policies
        
3.  For all policies associated with a specific statement, retrieves all transactions associated with the specified policies that have a `TransactionDate__c` within the statement period start and end date.
    
    If the transaction does not have a value for the `StatementId__c`, set the `StatementId__c` to the Id of the specified statement.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

This service doesn't take any remote options.

[](https://help.salesforce.com/s?language=en_US)

## Additional Information

Calculating `StatementStartDate__c`:

An account can have multiple policies with direct billing. Each policy may have a different billing frequency (annual, quarterly, monthly, or semi-monthly). The `StatementStartDate__c` is determined by using the policy’s bill due date and billing frequency to calculate the start date for each policy, then choosing the start date that's furthest back in time.

For example, an account has two policies, both with bill due dates of 2018-03-31. Policy 1 has a monthly billing frequency. Policy 2 has a quarterly billing frequency. Using the bill due date and billing frequency, the start date of Policy 1 is 2018-02-28. The start date of Policy 2 is 2018-01-01. Because the start date of Policy 2 is further back in time, the `StatementStartDate__c` is set to 2018-01-01.

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

The service expects an input JSON to be generated from a Vlocity Scheduled Job. This scheduled job includes the following key and its value:

-   `records`: A list of policies selected by the scheduled job
    

```
{
	"records": [{
			"Id": "02i5A000005iF1zQAE",
			"AccountId": "0015A000025MuenQAC",
			"AutomaticPaymentAmount__c": 10,
			"BillDueDate__c": "2018-03-31",
			"BillingFrequency__c": "Monthly",
			"PastDue__c": 10
		},
		{
			"Id": "02i5A000005iF20QAE",
			"AccountId": "0015A000025MuenQAC",
			"AutomaticPaymentAmount__c": 30,
			"BillDueDate__c": "2018-03-31",
			"BillingFrequency__c": "Quarterly",
			"PastDue__c": 30
		}
	]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

This service does not generate any output JSON.

Did this article solve your issue?

Let us know so we can improve!

YesNo