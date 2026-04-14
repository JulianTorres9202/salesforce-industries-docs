---
title: "Create Attribute Definition for Insurance Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_define_product_attributes.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Attribute Definition for Insurance Products

Create Attribute Definition for Insurance Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Attribute Definition for Insurance Products

Once you have picklists, define attributes to capture the characteristics of your insurance products. Attributes represent the details you evaluate during quoting and configuration. For example, Deductible and Limit are attributes of a coverage, while Age and Gender are attributes of a member.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

1.  From the App Launcher, find and select **Attribute Definitions**.
2.  In the Attribute Definitions list view, click **New**.
3.  In the New Attribute Definition window, enter these field values:
    
    -   Label: Deductible
    -   Source System ID: Deductible\_001
    -   Data Type: Picklist
    -   Picklist: Deductible
    -   Required: Selected
    -   Active: Selected
    -   Description: Deductible amount for coverage
    -   Help Text: Select deductible from standard values
    
4.  Save your changes.

Repeat the same procedure to define definitions for the following attributes:

| Data type | attribute definitions |
| --- | --- |
| Currency | 
-   Annual Out-of-Pocket Limit
-   Out-Network Annual Out-of-Pocket Limit

 |
| Number | 

-   Age
-   Contact Number
-   Part Time Member Count
-   Full Time Member Count
-   Member Without Dependent Count
-   Member With Spouse Count
-   Member With One Child Count
-   Member With More Than Two Children Count
-   Member With More Than One Child Count
-   Member With Dependent Count
-   Total Members
-   Total Dependents
-   Number of Primary Members

 |
| Text | 

-   First Name
-   Last Name
-   E-mail
-   State
-   City
-   Room Rent
-   Limit
-   ICU Fees
-   Out-Network Room Rent limit
-   Out-Network ICU Fees

 |
| Percent | 

-   Doctor visit copay
-   Diagnostic/ lab test copay
-   Out-Network Diagnostic/ lab test copay
-   Out-Network Doctor visit copay

 |

We also need to create attribute definition of datatype picklist and map the corresponding picklist for the attribute definitions.

| Picklist | Attribute Definition |
| --- | --- |
| Limit | 
-   In-Network Coverage Limit
-   Out-Network Coverage Limit

 |
| Deductible | 

-   In-Network Coverage Deductible
-   Out-Network Coverage Deductible

 |
| Copay | 

-   In-Network Coverage Copay
-   Out-Network Coverage Copay

 |
| Coinsurance | 

-   In-Network Coverage Coinsurance
-   Out-Network Coverage Coinsurance

 |
| Number of Days Coverage | 

-   In-Network Coverage Number of Days
-   Out-Network Coverage Number of Days

 |
| Gender | 

-   Gender

 |
| Marital Status | 

-   Marital Status

 |
| Smoker Status | 

-   Smoker Status

 |
| Association With Primary Member | 

-   Association With Primary Member

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo