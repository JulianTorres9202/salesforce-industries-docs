---
title: "Group Benefits Data Harmonization"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_data_harmonization.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Benefits Data Harmonization

Group Benefits Data Harmonization[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Benefits Data Harmonization

We've updated Vlocity Health and Vlocity Insurance to let you move from the Vlocity Group Benefits object model to the Group Benefits Standard object model. From Summer '22 onwards, the shared data model is available for Financial Services Cloud and Health Cloud. Your group benefits data is stored on standard group benefits objects using standard fields.

For more details, see [Vlocity Object to Group Benefits Standard Object Model Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_object_to_group_benefits_standard_object_model_mapping.htm&language=en_US&type=5 "Learn how fields in the Vlocity Group Benefits object model correspond to fields in the Salesforce object model. Use these field mappings when you create scripts that move Group Benefits data from one model to the other.").

[](https://help.salesforce.com/s?language=en_US)**Where:** The [Harmonized Group Benefits](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_harmonization_overview.htm&language=en_US&type=5 "Group Benefits harmonization involves moving Group Benefits data from custom objects in the Vlocity managed package object model to standard objects in the Salesforce object model.") object model is available to any user who has a Salesforce FSC license.

For Health Cloud customers, we've introduced a new add on - `InsuranceGrpBenDataModelAddOn` under these SKUs:

-   Benefits Sales and Administration - Group
    
-   Benefits Sales and Administration - Individual, Family and Medicare
    

[](https://help.salesforce.com/s?language=en_US)**Why:** We're working to create one unified data model for Vlocity Health and Vlocity Insurance that's built on Salesforce Financial Cloud Services and Health Cloud. The data model on the Vlocity managed package is available for existing customers to use. However, all the future features will be built on the new standard data model of Group Benefits.

[](https://help.salesforce.com/s?language=en_US)**How:** If you haven't implemented Vlocity Health and Vlocity Insurance yet, you don't have to do anything. You can just start using the harmonized Group Benefits model when you start your implementation.

[](https://help.salesforce.com/s?language=en_US)If you already use the Vlocity Group Benefits object model, you have some decisions to make and some work to do to move to the Group Benefits standard object model:

[](https://help.salesforce.com/s?language=en_US)

1.  Decide when to migrate.
    
2.  Analyze your existing components, configurations, and code.
    
3.  Plan your data migration.
    
4.  Migrate your data.
    
5.  Make changes to existing components and configurations you identified in step 2.
    

For more information, see [When Should You Harmonize](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_harmonization_overview.htm&language=en_US&type=5 "Group Benefits harmonization involves moving Group Benefits data from custom objects in the Vlocity managed package object model to standard objects in the Salesforce object model.").ara

Did this article solve your issue?

Let us know so we can improve!

YesNo