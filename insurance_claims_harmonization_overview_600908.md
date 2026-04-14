---
title: "Claims Harmonization Overview"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claims_harmonization_overview_600908.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Claims Harmonization Overview

Claims Harmonization Overview[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Claims Harmonization Overview

Claims harmonization involves moving claims data from custom objects in the Vlocity managed package object model to standard objects in the Salesforce object model. The Vlocity model supports the Asset → InsuranceClaim relationship between policies and claims. The Salesforce model supports the InsurancePolicy → Claim relationship between policies and claims. Services and LWCs are updated to work with claims data in the Salesforce data model.

In an org harmonized for claims:

-   There are no references to the Vlocity Party model. ClaimParticipant replaces InsuranceClaimPartyRelationship and directly uses ContactId, AccountId, and InsurancePolicyParticipantId instead of using PartyId.
    
-   The `InsuranceClaimInvolvedInjury__c` and `InsuranceClaimInvolvedProperty__c` custom objects are consolidated into the `ClaimItem` object. The `ClaimItem.Category` field designates the Claim Item as Involved Injury or Damaged Property.
    
-   The `ClaimLineItem__c` object is split into these three objects to allow for specificity in object design:
    
    -   `ClaimCoveragePaymentDetail`
        
    -   `ClaimCoveragePaymentAdjustment`
        
    -   `ClaimCoverageReserveDetail`
        
-   [](https://help.salesforce.com/s?language=en_US)
    
    The `vlocity_ins__InsClaimReserveTransaction__c` is replaced with `ClaimCoverageReserveAdjustment`.
    

Important

Underlying services support both Vlocity and Salesforce object models. But in the context of claims, the term "Item" in service and LWC names means "Financial Item" for both models, not "damaged/involved Item."

For details on Claims harmonized objects and the field mappings for each object, see [Vlocity InsuranceClaim\_\_c to FSC Claim Harmonized Object Model Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insuranceclaimc_to_fsc_claim_harmonizedobject_model_mapping_600958.htm&language=en_US&type=5 "Learn how fields in the Vlocity managed package object model correspond to fields in the Salesforce object model. Use these field mappings when you create scripts that move claims data from one model to the other.").

This diagram shows a high-level view of Claims objects in the Salesforce data model.

[](https://help.salesforce.com/s?language=en_US)

**Insurance Claim Data Model in a Harmonized Org**

Did this article solve your issue?

Let us know so we can improve!

YesNo