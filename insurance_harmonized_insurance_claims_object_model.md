---
title: "Harmonized Insurance Claims Object Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_harmonized_insurance_claims_object_model.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Harmonized Insurance Claims Object Model

Harmonized Insurance Claims Object Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Harmonized Insurance Claims Object Model

With the Vlocity Insurance Summer '21 release, the Salesforce Claims product now supports both the existing Vlocity object model (custom objects in managed package) and the new Salesforce object model (standard Salesforce objects). The Vlocity model supports the Asset → InsuranceClaim relationship between policies and claims. The Salesforce model supports the InsurancePolicy → Claim relationship between policies and claims.

[](https://help.salesforce.com/s?language=en_US)The harmonization includes the following:

[](https://help.salesforce.com/s?language=en_US)

-   New Salesforce standard objects in the data model (See [Vlocity InsuranceClaim\_\_c to FSC Claim Harmonized Object Model Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insuranceclaimc_to_fsc_claim_harmonizedobject_model_mapping_600958.htm&language=en_US&type=5 "Learn how fields in the Vlocity managed package object model correspond to fields in the Salesforce object model. Use these field mappings when you create scripts that move claims data from one model to the other.")).
    
-   Updating services in the InsClaimService, InsClaimItemService class, InsClaimCoverageService and InsPolicyTermsService.
    
-   Updating Claims LWCs.
    

[](https://help.salesforce.com/s?language=en_US)**Where:** Claims Management system of record functionality is now supported on Salesforce Standard Objects using the Insurance Policy object as the Policy record. This functionality is available in Summer '21 and later releases.

[](https://help.salesforce.com/s?language=en_US)**Why:** We're working to create one unified data model for Vlocity Insurance built on Salesforce FSC. While you don't have to move to this data model, going forward our new features will be built on it.

[](https://help.salesforce.com/s?language=en_US)**How:** If you haven't implemented Vlocity Insurance yet, you don't have to do anything. You can just start using the harmonized Insurance Claim model when you start your implementation.

[](https://help.salesforce.com/s?language=en_US)If you already use the Asset object model or the Vlocity Insurance FSC extension object model, you have some decisions to make and some work to do to move to the Insurance Claim model.

[](https://help.salesforce.com/s?language=en_US)

1.  Decide when to migrate.
    
2.  Analyze your existing components, configurations, and code.
    
3.  Plan your data migration.
    
4.  Migrate your data.
    
5.  Make changes to existing components and configurations you identified in step 2.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo