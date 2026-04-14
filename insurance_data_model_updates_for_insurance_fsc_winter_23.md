---
title: "Data Model Updates for Insurance FSC Winter '23"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_data_model_updates_for_insurance_fsc_winter_23.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Insurance FSC Winter '23

Data Model Updates for Insurance FSC Winter '23[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Insurance FSC Winter '23

Explore new and enhanced data model objects for this release.

[](https://help.salesforce.com/s?language=en_US)

## New Data Model Object

We added these new objects to the data model for this release:

| 
New Data Model Object

 | 

Description

 |
| --- | --- |
| 

ContractGroupPlan

 | 

Represents a set of plans as part of the contract between the insurance carrier and the group. This set of plans corresponds to the plans included in the quote (as Quote Line Items). Child object of Contract.

This object includes these new fields:

-   Attribute Selected Values: Selected values of the Product attribute.
    
-   Product: The product associated with the contract group plan.
    
-   Product Child Item: The product child item associated with the contract group plan.
    

 |
| GroupCensus | 

Represents a snapshot of statistics about eligible members (employees or members) of a group (employer or association) and their legal dependents. Use this entity in quoting, rating, and the subsequent enrollment process. Child object of employer or group Account.

This object includes these new fields:

-   Attribute Selected Values: Selected values of the Product attribute.
    
-   Product: The product associated with the group census.
    

 |
| GroupCensusMember | 

Represents personal information about a member, for example employee or association member, or their dependents. This object helps estimate the insurance plan cost for the group. GroupCensusMember is also used in the enrollment process to retrieve the member and dependent details. Child object of GroupCensus.

This object includes these new fields:

-   Attribute Selected Values: Selected values of the Product attribute.
    
-   Product: The product associated with the group census member.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Enhanced Data Model Objects

We added fields and made other enhancements to the following objects for this release:

| 
Enhanced Data Model Objects

 | 

Description

 |
| --- | --- |
| 

Quote

 | 

This object includes the following new field:

-   Group Census: A snapshot of statistics about eligible Members (Employees/Members) of a group (Employer/Association) and their legal dependents.
    

 |
| 

InsurancePolicyPaymentScheduleEntry\_\_c

 | 

This object includes the following new field:

[](https://help.salesforce.com/s?language=en_US)

-   Is Paid: Payment status for the payment schedule entry.
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo