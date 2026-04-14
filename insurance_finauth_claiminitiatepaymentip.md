---
title: "Check Financial Authority in Claim Payment Processes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_claiminitiatepaymentip.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Check Financial Authority in Claim Payment Processes

Check Financial Authority in Claim Payment Processes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Check Financial Authority in Claim Payment Processes

As part of your financial authorization workflow, configure the Integration Procedure that's specified for the **ClaimInitiatePaymentIP** Insurance Configuration Setup custom setting. This is the same Integration Procedure that's kicked off by `InsClaimItemService: invokeInitiatePaymentIP`.

1.  Add a new Remote Action called FinancialAuthorityCheck or something similar.
    
    Have it call `InsClaimItemService: claimCoverageValuation` to verify a user's financial authority.
    
    | 
    Remote Class
    
     | 
    
    Remote Method
    
     |
    | --- | --- |
    | 
    
    InsClaimItemService
    
     | 
    
    claimCoverageValuation
    
     |
    
    Add remote options to set the Status of claims, claim coverages, and payment details to **Pending Authority** if a user doesn't have the authority to pay or approve an amount. Add another remote option to tell the service to skip the user financial authority evaluation for claim coverage payment detail records with a Status of **Authority Approved**.
    
    | 
    Key
    
     | 
    
    Value
    
     |
    | --- | --- |
    | 
    
    AuthorityFailClaimStatus
    
     | 
    
    Pending Authority
    
     |
    | 
    
    AuthorityFailClaimCoverageStatus
    
     | 
    
    Pending Authority
    
     |
    | 
    
    AuthorityFailClaimCoveragePaymentDetailStatus
    
     | 
    
    Pending Authority
    
     |
    | 
    
    ClaimCovPaymentDetailStatusBypassFinancialAuthorityValuation
    
     | 
    
    Authority Approved
    
     |
    
2.  Check the **CreatePayments** Remote Action, which calls `InsClaimItemService: createPayments` to create payments. Make sure the financial authority check comes _before_ the **CreatePayments** action. This way `InsClaimItemService: createPayments` doesn't run unless the financial authority check passes.

Did this article solve your issue?

Let us know so we can improve!

YesNo