---
title: "Transaction Reversals"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_transaction_reversals_622031.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Transaction Reversals

Transaction Reversals[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Transaction Reversals

You can reverse transactions you make on insurance policies. Vlocity Insurance calculates the reversal and generates the transaction required to amend the policy.

Here's what Vlocity Insurance does to reverse a transaction on a policy:

[](https://help.salesforce.com/s?language=en_US)

1.  Looks for a policy snapshot. (When eligible transactions are created on a policy, the system creates this snapshot.)
    
2.  Creates a new policy version based on the policy snapshot.
    
3.  Sets the previous policy version's status to Reversed.
    

The transaction that's created to amend the policy includes the calculation for any applicable refund of premium, taxes, fees, and commissions.

Note

This feature works with the FSC Insurance Policy object model only.

The transactions you can reverse are:

-   Sold policy
    
-   Long-term endorsements
    
-   Cancel policy
    

Note

You can't reverse short-term policy endorsements.

[](https://help.salesforce.com/s?language=en_US)

## Implement Transaction Reversals for Users

You can make it possible for your users to reverse transactions as follows;

-   Add steps (and buttons or other controls to access those steps) to Modify Policy and Cancel policy OmniScripts
    
-   Create specific OmniScripts to let users reverse sold policy, modify policy (endorsement), and cancel policy transactions
    

[](https://help.salesforce.com/s?language=en_US)

## Services that Work with Transaction Reversals

The `InsPolicyService` class services that create transactions store a snapshot of the state of the policy as an attachment. These services are:

-   `InsPolicyService:createUpdatePolicy`
    
-   `InsPolicyService:createPolicyVersion`
    
-   `InsPolicyService:cancelPolicy`
    
-   `InsPolicyService:createTransaction`
    

Did this article solve your issue?

Let us know so we can improve!

YesNo