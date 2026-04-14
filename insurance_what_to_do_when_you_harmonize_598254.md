---
title: "How to Harmonize"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_what_to_do_when_you_harmonize_598254.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# How to Harmonize

How to Harmonize[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How to Harmonize

Before you make the switch to the Salesforce data model, analyze and prepare your org. Recreate custom data, run migration scripts, and update reports and dashboards. These tasks bring your org into harmony with the new data model.

[](https://help.salesforce.com/s?language=en_US)

-   Inventory All Data Model Extensions
    
    Complete required tasks for any custom data model extensions on the Asset, Insurance Policy, Claim, and Group Benefits objects in your org.
    
    | 
    Data Model Extension
    
     | 
    
    Tasks
    
     |
    | --- | --- |
    | 
    
    Extension fields
    
     | 
    
    Recreate all extension fields on the Insurance Policy objects
    
     |
    | 
    
    Custom objects
    
     | 
    
    -   Recreate all custom objects that act as master details to other entities
        
    -   Replace lookup fields from existing entities with the new entities
        
    
     |
    | 
    
    Plan data migration for your production orgs
    
     | 
    
    Learn how object fields in your current data model correspond to object fields in the Salesforce data model. Use these field mappings when you create scripts that move data from one model to the other.
    
    -   Insurance Industries Extension Model Extension
        
        See [Insurance Industries Extension to Insurance Policy Object Model Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_fsc_extension_to_insurance_policy_harmonizedobject_catalog_598366.htm&language=en_US&type=5 "Learn how fields in the Insurance Industries Extension object model correspond to fields in the Insurance Policy object model. Use these field mappings when you create scripts that move insurance policy data from one model to the other.").
        
    -   Asset Object Model Extension
        
        See [Asset to Insurance Policy Object Model Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_asset_to_insurance_policy_object_model_mapping_599506.htm&language=en_US&type=5 "Learn how fields in the Asset object model correspond to fields in the Insurance Policy object model. Use these field mappings when you create scripts that move insurance policy data from one model to the other.").
        
    -   Claims Object Model Extension
        
        See [Vlocity InsuranceClaim\_\_c to FSC Claim Harmonized Object Model Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insuranceclaimc_to_fsc_claim_harmonizedobject_model_mapping_600958.htm&language=en_US&type=5 "Learn how fields in the Vlocity managed package object model correspond to fields in the Salesforce object model. Use these field mappings when you create scripts that move claims data from one model to the other.").
        
    -   Group Benefits Object Model Extension
        
        See [Vlocity Object to Group Benefits Standard Object Model Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_object_to_group_benefits_standard_object_model_mapping.htm&language=en_US&type=5 "Learn how fields in the Vlocity Group Benefits object model correspond to fields in the Salesforce object model. Use these field mappings when you create scripts that move Group Benefits data from one model to the other.").
        
    
     |
    
-   Inventory Your Omnistudio Data Mappers
    
    Identify Data Mappers that reference the old objects and fields and replace them with new Data Mappers that reference the new objects and fields.
    
-   Check Data Sources on FlexCards and Classic Cards
    
    Complete required tasks based on the data source used for each of your classic cards or FlexCards.
    
    | 
    Data Source
    
     | 
    
    Tasks
    
     |
    | --- | --- |
    | 
    
    Data Mapper
    
     | 
    
    Replace with new Data Mappers you've created that reference the new objects and fields.
    
     |
    | 
    
    Custom Apex
    
     | 
    
    Replace with new custom Apex you've developed that references the new objects and fields, or do a **Save & Fetch** if you've replaced the fields in the existing Apex code.
    
     |
    | 
    
    SOQL
    
     | 
    
    Formulate new queries that reference the new objects and fields.
    
     |
    
-   Check Custom LWCs
    
    If you're using old fields in any custom LWCs you've created, update them.
    
-   Analyze Custom Apex Code
    
    If any of your custom Apex code uses old fields, replace them with the new fields.
    
-   Reports and Dashboards
    
    Some of your reports and dashboards probably pull insurance policy data from the object model you currently use. Modify or recreate these to pull from the new object model.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo