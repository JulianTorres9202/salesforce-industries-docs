---
title: "Data Model Updates for Insurance FSC Summer '21"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_data_model_updates_for_insurance_fsc_summer21_4045.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Insurance FSC Summer '21

Data Model Updates for Insurance FSC Summer '21[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Insurance FSC Summer '21

The data model updates for this release:

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

Claim

 | 

This object includes the following fields:

-   Attribute Selected Values
    
-   Product
    

 |
| 

Claim Item

 | 

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Attribute Selected Values
    
-   Product
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    Product Image
    

 |
| 

Claim Coverage

 | 

No custom fields were added.

 |
| 

Claim Coverage Payment Detail

 | 

No custom fields were added.

 |
| 

Claim Coverage Reserve Adjustment

 | 

No custom fields were added.

 |
| 

Claim Participant

 | 

No custom fields were added.

 |
| 

Insurance Policy Terms

 | 

This object represents the financial policy terms, such as limits and deductibles, for the policy and policy coverages. It’s the master-detail child object of Insurance Policy (InsurancePolicy).

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Applicable Item
    
-   Attribute Class
    
-   Attribute Code
    
-   Attribute
    
-   Attribute Scope
    
-   Benefit Type
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    ClaimLineItemClaimedAmount
    
-   Duration Type
    
-   Effective Year
    
-   Initial Amount
    
-   Initial Value
    
-   Insurance Policy Coverage
    
-   Policy Version
    
-   Insured Party
    
-   Insured Policy Asset
    
-   Is Active
    
-   PaymentAttempted
    
-   ReserveAdjustmentAttempted
    
-   Original Policy
    
-   Reference Policy Number
    

 |
| 

Insurance Policy Terms Tracking Entry

 | 

This object represents credits and debits made against a Policy Financial Term. The entry is typically updated when you make Claim Payments against a specific Policy Financial Term, such as limits and deductibles. Use this object in determining the current standing of a given Policy Financial Term at a given point in time. This object is a master-detail child object of the Policy Terms.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Calculated Initial Amount
    
-   Calculated Initial Value
    
-   Claim
    
-   Claim Coverage
    
-   Claim Coverage Payment Detail
    
-   Claim Item
    
-   Initial Amount
    
-   Initial Value
    
-   Insurance Policy Participant
    
-   Insured Policy Asset
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    Numerical Order
    
-   Policy Term
    
-   Posted Amount
    
-   Posted Value
    
-   Remaining Amount
    
-   Remaining Value
    

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

Insurance Policy

 | 

[](https://help.salesforce.com/s?language=en_US)We added the following field:

-   Production Code: The production code of the producer.
    

 |
| 

Vlocity Tracking Entry

 | 

We added the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   [](https://help.salesforce.com/s?language=en_US)
    
    Claim
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    Claim Coverage
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo