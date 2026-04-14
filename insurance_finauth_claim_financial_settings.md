---
title: "Configure Claim Financial Settings"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_claim_financial_settings.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Claim Financial Settings

Configure Claim Financial Settings[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Claim Financial Settings

Services use Claim Financial Settings to identify which records require financial authorization. Configure them to use **Pending Authority**, **Authority Approved**, and **Authority Denied** status values.

1.  From Setup, in the Quick Find box, enter Claim Financial Settings, and then select **Claim Financial Settings**.
2.  Click **New Claim Financial Settings**.
3.  Enter status values used to indicate the financial authority status of claim coverages, claim coverage payment details, and claims.
    
    | 
    Setting
    
     | 
    
    Value
    
     |
    | --- | --- |
    | 
    
    **Claim Coverage Pending Authority Status**
    
     | 
    
    Status of a claim coverage amount that's pending approval. Pending Authority.
    
    When processing an approval request for a coverage amount, `InsClaimItemService: claimCoverageValuation` evaluates claim coverage records with this status.
    
     |
    | 
    
    **Claim Coverage Payment Detail Pending Authority Status**
    
     | 
    
    Status of a claim coverage payment detail amount that's pending approval. Pending Authority.
    
    When processing an approval request, `InsClaimItemService: claimCoverageValuation` evaluates claim coverage payment detail records with this status.
    
     |
    | 
    
    **Claim Pending Authority Status**
    
     | 
    
    Status of a claim amount that requires approval. Pending Authority,Authority Denied,Authority Approved.
    
     |
    
4.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo