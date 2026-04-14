---
title: "Insurance and Financial Services Data Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance and Financial Services Data Model

Insurance and Financial Services Data Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance and Financial Services Data Model

The Insurance and Financial Services data model is a comprehensive data model designed to address the complexities and challenges faced by cloud-based insurance and financial services systems across insurance markets.

The model covers concepts including customer management, producer management, insurance product management, policy rating and quoting, policy issuance and administration, claims management, and much more. The Insurance and Financial Services data model is a 100% additive extension of the standard Salesforce data model and is designed to work with Salesforce Financial Services Cloud. Each ERD page in this section illustrates the important entities, relationships, and extensions to the Salesforce object model. For a list of the data, system, and integration objects for the Insurance and Financial Services data model, see the object list below. To understand the notation used in these diagrams, see the [About Entity Relationship Diagram Notation](https://help.salesforce.com/s/articleView?id=ind.v_data_models_about_vlocity_entity_relationship_diagram_notation_666736.htm&language=en_US&type=5).

Different ERDs apply depending on whether you use a harmonized org. (If harmonization is a new concept for you, see [Plan Your Switch to the Salesforce Data Model](https://help.salesforce.com/s/articleView?id=ind.insurance_harmonize_your_vlocity_insurance_org_598191.htm&language=en_US&type=5 "Switching to the Salesforce data model ensures you get new and enhanced features for the Digital Insurance Platform in the future. But it's up to you whether to harmonize, and when. It's a large undertaking that requires an analysis of your org, and potentially updates to custom components.").

| 
Vlocity Insurance Data Model

 | 

Harmonized FSC Insurance Policy Object Model

 |
| --- | --- |
| 

-   [Billing and Payments ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_4df0b4ee93a8be50d21b08e947f26431)
    
-   [Policy Management ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_7d3114aac9d80dc78787caf8e8f09b05)
    
-   [Insurance Quoting and Applications ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_4b3cb46b25aef374a65083d0c6255886)
    
-   [Insurance Claim Management ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_68e82128646e37cc8b8f2c697fdcf57a)
    
-   [Insurance Customer Model ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_c90b3b7df683a016b84d5d47c948b12f)
    
-   [Vlocity Insurance and Financial Services Object List](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__insurance_and_financial_services_object_list)
    

 | [](https://help.salesforce.com/s?language=en_US)

-   [Billing and Payments ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_4df0b4ee93a8be50d21b08e947f26431)
    
-   [Policy Management with FSC Insurance ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_6b6103598537c7ec807b0595291b8499)
    
-   [Insurance Quoting and Applications ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_4b3cb46b25aef374a65083d0c6255886)
    
-   [Insurance Claim Management with FSC Insurance ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_bf963ef124029b1dbbc6fd6fe7427718)
    
-   [Insurance Customer Model ERD](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__section_c90b3b7df683a016b84d5d47c948b12f)
    
-   [Vlocity Insurance and Financial Services Object List](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_and_financial_services_data_model_651683.htm&language=en_US&type=5#insurance_vlocity_insurance_and_financial_services_data_model_651683__insurance_and_financial_services_object_list)
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Billing and Payments ERD

_Last updated as of September 2020_

[](https://help.salesforce.com/s?language=en_US)

## Policy Management ERD

_Last updated as of September 2020_

[](https://help.salesforce.com/s?language=en_US)

## Policy Management with FSC Insurance ERD

_Last updated as of March 2021_

[](https://help.salesforce.com/s?language=en_US)

## Insurance Quoting and Applications ERD

_Last updated as of September 2020_

[](https://help.salesforce.com/s?language=en_US)

## Insurance Claim Management ERD

_Last updated as of September 2020_

[](https://help.salesforce.com/s?language=en_US)

## Insurance Claim Management with FSC Insurance ERD

_Last updated as of March 2021_

[](https://help.salesforce.com/s?language=en_US)

## Insurance Customer Model ERD

_Last updated as of September 2020_

[](https://help.salesforce.com/s?language=en_US)

## Vlocity Insurance and Financial Services Object List

For details about Vlocity Insurance and Financial Services objects, see the [Insurance Object List](https://volt.my.salesforce.com/sfc/p/#o0000000ikm8/a/3m000000nxup/nfawj2wseajgmzm8.jzxvxhqyii4wlslrt9e1c5wcfk).

Did this article solve your issue?

Let us know so we can improve!

YesNo