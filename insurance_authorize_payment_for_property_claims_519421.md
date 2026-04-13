---
title: "Authorize Payment for Property Claims"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_authorize_payment_for_property_claims_519421.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Authorize Payment for Property Claims

Authorize Payment for Property Claims[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Authorize Payment for Property Claims

Claim approvers, claim handlers, and claim adjusters are all assigned a maximum limit that they can authorize a claim payment for. If the claim amount is over the authorized limit for a particular role, the claim needs to be approved by a claim manager before it can be paid.

The claim recovery workflow runs using the claim coverage Integration Procedure. You can find this Integration Procedure in OmniStudio Integration Procedures under:

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

A guided OmniScript flow simplifies this approval process.

1.  Navigate to the **Financials** tab of the claim record.
2.  You can now create either a new loss item or a new expense item. For this example, we're creating a new loss item. Click **New Loss Item**.
3.  Select the coverages for the item.
4.  Enter details for the coverage and click **Add**.
    
    The Adjusted Amount here is automatically calculated by the workflow.
    
5.  To individually pay an item, click **Pay** on the loss item.
6.  To pay multiple items at once, select them and choose Pay from the drop-down.
7.  Any amount that exceeds the user's authority is sent for approval and the status is changed to Pending Authority.
8.  The approver receives an email with a link to approve this claim item. They are navigated to a page that lets them approve, deny, or reassign the request.
9.  After approval the status changes to Authority Approved. Now click **Pay**.
10.  The status changes to paid.

Did this article solve your issue?

Let us know so we can improve!

YesNo