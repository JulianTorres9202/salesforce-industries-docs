---
title: "Building Blocks of Your Workflow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_building_blocks.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Building Blocks of Your Workflow

Building Blocks of Your Workflow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Building Blocks of Your Workflow

Pre-configured tools in Insurance give you a head start on a financial authorization workflow. These tools drive records through the financial authorization workflow by evaluating whether users have the authority to pay or approve amounts. Based on the results of this evaluation, the tools update status values in claims, claim coverages, and claim coverage payment details.

Pre-configured tools are the building blocks of your workflow. They're configured to use **Pending Authority**, **Authority Approved**, and **Authority Denied** status values by default. If you decide to use different status values, make sure you reconfigure each building block.

| 
Workflow Building Block

 | 

Default Status Values

 |
| --- | --- |
| 

`InsClaimItemService: claimCoverageValuation`

 | 

`InsClaimItemService: claimCoverageValuation` verifies that users have the authority to pay or approve amounts in different types of financial activities.

As part of your setup, you add a Remote Action to the Integration Procedure that's specified for **ClaimInitiatePaymentIP** in the **Insurance Configuration Setup** custom setting. Configure this remote action to call `InsClaimItemService: claimCoverageValuation`. Add remote options to set the status of the claim, claim coverage, or claim coverage payment detail if a user doesn't have the authority to pay or approve the requested amount.

-   **AuthorityFailClaimStatus**: Pending Authority
    
-   **AuthorityFailClaimCoverageStatus**: Pending Authority
    
-   **AuthorityFailClaimCoveragePaymentDetailStatus**: Pending Authority
    

Add another remote option to skip the claim coverage payment detail valuation if a record's status indicates that it's already been through the approval process.

-   **ClaimCovPaymentDetailStatusBypassFinancialAuthorityValuation**: Authority Approved
    

When users click **Pay** on a loss or expense, `InsClaimItemService: invokeInitiatePaymentIP` calls the Integration Procedure that's specified for **ClaimInitiatePaymentIP**. By configuring the Integration Procedure with the claim coverage valuation service, you make a check of financial authority a standard part of your claim payment process.

 |
| 

Claim Financial Settings

 | 

Claim Financial Settings specify statuses of records that are pending or require approval.

These setting values must match the ones used for `InsClaimItemService: claimCoverageValuation` remote options in the Integration Procedure that's specified for ClaimInitiatePaymentIP.

-   Claim Coverage Pending Authority Status = Pending Authority
    
-   Claim Coverage Payment Detail Pending Authority Status = Pending Authority
    
-   Claim Pending Authority Status = Pending Authority,Authority Denied,Authority Approved
    

 |
| 

Post-Approve Flow

 | 

As part of your setup, you configure a flow that takes required actions when an approver approves a user's financial authorization request.

The Start element specifies that the flow is triggered when a Claim has a given financial authority status.

-   FinancialAuthorityStatus = **Authority Approved**
    

The Get Record element of this flow gets records with a given status.

-   ClaimCoverageSourceStatus = **Pending Authority**
    
-   ClaimCovPaymentDetailSourceStatus = **Pending Authority**
    

The Update Record element updates status values.

-   ClaimCoverageTargetStatus = **Open**
    
-   ClaimCovPaymentDetailTargetStatus = **Authority Approved**
    

 |
| 

Post-Reject Flow

 | 

You also configure a flow that takes required actions when an approver rejects a user's financial authorization request.

The Start element specifies that the flow is triggered when a Claim has a given financial authority status.

-   FinancialAuthorityStatus = **Authority Denied**
    

The Get Record element of this flow gets records with a given status.

-   ClaimCoverageSourceStatus = **Pending Authority**
    
-   ClaimCovPaymentDetailSourceStatus = **Pending Authority**
    

The Update Record element updates status values.

-   ClaimCoverageTargetStatus = **Open**
    
-   ClaimCovPaymentDetailTargetStatus = **Authority Denied**
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo