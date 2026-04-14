---
title: "Data Model Updates for Insurance FSC Spring '21"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_data_model_updates_for_insurance_fsc_spring21_7131.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Insurance FSC Spring '21

Data Model Updates for Insurance FSC Spring '21[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Insurance FSC Spring '21

These are the data model updates for this release.

[](https://help.salesforce.com/s?language=en_US)

## New Data Model Objects

We added these objects to the data model for this release:

| 
New Object

 | 

Description

 |
| --- | --- |
| 

Insurance Policy Surcharge

 | 

This object represents the charges calculated for an insurance policy and its related assets, coverages, and participants in a region.

This object includes the following fields:

-   Adjustment Type: Type of associated product tax and fee.
    
-   Refundable: Indicates if tax or fee is refundable.
    
-   Tax/Fee Id: Product tax and fee used to calculate the amount.
    
-   Tax/Fee Name: Name of product tax and fee used to calculate the amount.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Enhanced Data Model Objects

We added fields and made other enhancements to the following objects for this release:

| 
Enhanced Object

 | 

Description

 |
| --- | --- |
| 

Insurance Policy Payment Schedule Entry

 | 

This object represents scheduled payments including premiums, taxes, and fees for a policy record across the term of the policy.

This object includes the following field:

-   Insurance Policy Transaction: Insurance policy transaction associated with the payment schedule entry.
    

 |
| 

Insurance Policy Revenue Schedule Entry

 | 

This object represents calculated earned revenue from insurance premiums or other revenue sources.

[](https://help.salesforce.com/s?language=en_US)This object includes the following field:

-   Insurance Policy Transaction: Insurance policy transaction associated with the revenue schedule entry.
    

 |
| 

Insurance Policy

 | 

[](https://help.salesforce.com/s?language=en_US)This object includes the following field:

-   Plan: Identifies the plan in which the employee is enrolled.
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo