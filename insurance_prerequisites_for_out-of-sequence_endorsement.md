---
title: "Prerequisites for Out-of-Sequence Endorsement"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_prerequisites_for_out-of-sequence_endorsement.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Prerequisites for Out-of-Sequence Endorsement

Prerequisites for Out-of-Sequence Endorsement[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Prerequisites for Out-of-Sequence Endorsement

Review these prerequisites and considerations to set up and create an out-of-sequence endorsement.

-   Enable the field-level security for Reference Policy Number.
    
-   Enable the field-level security for Policy Edit Locked.
    
-   Permission sets must be updated to include access to these custom objects:
    
    -   `InsuranceAsyncBulkRequest`
        
    -   `InsuranceAsyncBulkRequestDetail`
        
        Also, enable the field-level security for these objects.
        
-   To support out-of-sequence endorsement for multiple policy terms, the Reference Policy Number must be the same for all versions of a policy across terms. You must populate the Reference Policy Number for all existing policies.
    
    Note
    
    For new policies, `InsPolicyService:createPolicyVersion` generates the Reference Policy Reference, and `InsPolicyService:createReinstatementPolicy` and `InsPolicyService:createOutOfSequencePolicyVersion` copies it over from version to version. Customers can override the generated number and use their own policy numbering pattern for the Reference Policy Number.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo