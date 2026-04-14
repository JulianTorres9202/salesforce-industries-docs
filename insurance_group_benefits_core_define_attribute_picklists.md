---
title: "Define Attribute Picklists for Group Benefits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_define_attribute_picklists.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Define Attribute Picklists for Group Benefits

Define Attribute Picklists for Group Benefits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Define Attribute Picklists for Group Benefits

Start by defining picklists that hold reusable sets of values. You reference these picklists later when you create attributes. For example, a Deductible attribute can pull values like $50, $100, $250. To use picklists with your attributes, define the picklists first before creating the attributes.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

1.  From the App Launcher, find and select **Attribute Picklists**.
2.  Click **New**.
3.  Enter these field values:
    
    -   Name: Limit
    -   Data Type: Currency
    -   Status: Active
    -   Description: Available limit values for coverage
    
4.  Click **Save**.
5.  On the Related tab, in Attribute Picklist Values, click **New**.
6.  Enter these field values:
    
    -   Name: TwoThousand
    -   Code: TwoThousand
    -   Status: Active
    -   Default: Selected
    -   Display Value: $2,000
    -   Value: $2,000
    
7.  Save your changes.

Repeat the same procedure for the following picklists:

| picklist | data type | values |
| --- | --- | --- |
| Limit | Currency | 2000, 3000, 5000, 10000 |
| Deductible | Currency | 50, 100, 250, 500 |
| Copay | Percentage | 0%, 10%, 25% |
| Coinsurance | Percentage | 0%, 10%, 20%, 30%, 40% |
| Number of Days Covered | Number | 3, 5, 10, 15, 30, 60, 90 |
| Gender | Text | Male, Female, Other |
| Marital Status | Text | Single, Married, Divorced, Widowed, Other |
| Smoker Status | Text | Tobacco, Non-Tobacco |
| Association with Primary Member | Text | Self, Other, Child, Spouse, Parent, Parent-in-law |

Did this article solve your issue?

Let us know so we can improve!

YesNo