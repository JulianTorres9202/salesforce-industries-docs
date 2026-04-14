---
title: "How Does Authorize Payment for Auto Claims Work"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_how_does_authorize_payment_for_auto_claims_work.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# How Does Authorize Payment for Auto Claims Work

How Does Authorize Payment for Auto Claims Work[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How Does Authorize Payment for Auto Claims Work

The claim recovery workflow runs using the claim covergae Integration Procedure. You can find this Integration Procedure in OmniStudio Integration Procedure under:

-   Type/Subtype: ins/ClaimCoverage
    
-   OmniScript Name: claim coverage
    

Here's a look at each component in the Integration Procedure:

| 
Component Name

 | 

Component Type

 | 

What It Does

 | 

What It Calls

 |
| --- | --- | --- | --- |
| 

CalimCoveragePaymentDetails

 | 

Loop Block

 | 

It extracts details of the claim coverages.

 | 

None

 |
| 

setTypeList

 | 

Set Values

 | 

Sets values for the Expense list, Loss list, and Status Authority Approved list.

 | 

None

 |
| 

SetVariables

 | 

Set Values

 | 

Sets values for the variables ApprovalProcessComplete, AuthorityEvaluationType, uniqueClaimCoverageIds.

 | 

None

 |
| 

distinctCoverageList

 | 

List Action

 | 

[](https://help.salesforce.com/s?language=en_US)Merges lists to create a distinct coverage list.

 | 

None

 |
| 

ApprovalProcessCompleteIP

 | 

Integration Procedure

 | 

Based on user information, it retrieves authority level and sets the limit of the amount that they user can approve. It then sends out the email to the approver. It also verifies the response by the approver and then updates the status of the claim item.

 | 

None

 |
| 

ApprovalProcessCompleteAction

 | 

Remote Action

 | 

Uses the createPayments to create a payment record for the item.

 | 

None

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo