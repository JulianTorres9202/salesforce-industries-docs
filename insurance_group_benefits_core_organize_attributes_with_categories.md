---
title: "Organize Insurance Attributes with Categories"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_organize_attributes_with_categories.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Organize Insurance Attributes with Categories

Organize Insurance Attributes with Categories[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Organize Insurance Attributes with Categories

Attribute categories are optional, but they help organize large sets of attributes into meaningful groups. For example, you can group First Name, Last Name, Age, Gender, and Marital Status under a category called Personal Information. This makes it easier to manage and assign attributes to product classifications.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

1.  From the App Launcher, find and select **Attribute Categories**.
2.  In the list view, click **New**.
3.  In the New Attribute Category window, enter these field values:
    
    -   Name: Personal Information
    -   Code: PersonalInfo
    -   Description: Demographic details for members
    
4.  Save your changes.
5.  Navigate to the Related tab.
6.  In the Attributes section, click **Assign**.
7.  Search for and select attributes such as First Name, Last Name, Age, Gender, Marital Status, Smoker Status, and click **Assign**.

Repeat the same procedure for other attribute categories.

| Attribute Category | Attributes |
| --- | --- |
| Contact Information | 
-   E-Mail
-   State
-   City
-   Contact Number

 |
| In-Network Coverage Terms | 

-   Room Rent Limit
-   ICU Fees
-   In-Network Limit
-   In-Network Deductible
-   In-Network Copay
-   In-Network Coinsurance

 |
| Out-Network Coverage Terms | 

-   Out-Network Room Rent Limit
-   Out-Network ICU Fees
-   Out-Network Limit
-   Out-Network Deductible
-   Out-Network Copay
-   Out-Network Coinsurance

 |
| Summary Reference Record | 

-   Group Census Group Class Summary Name

 |
| Summary Information | 

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

Did this article solve your issue?

Let us know so we can improve!

YesNo