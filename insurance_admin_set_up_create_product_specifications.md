---
title: "Create Product Specifications in Revenue Cloud"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_create_product_specifications.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create Product Specifications in Revenue Cloud

Create Product Specifications in Revenue Cloud

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Create Product Specifications in Revenue Cloud

With Product Catalog Management, you can define a specification type for the products that are unique to your industry. A product specification type is associated with a product specification record type.

[](https://help.salesforce.com/s?language=en_US)

## Create Record Types

Create Insured Party, Insured Item, Coverage, and Product record types on the Product2 object.

1.  From Setup, in the Quick Find box, find and select **Object Manager**.
2.  In Object Manager, select **Product**.
3.  In the side panel, select **Record Types**.
4.  Create a new product record type.
    1.  Click **New**.
    2.  In Existing Record Type, select **Master**.
    3.  In Record Type Label, enter the name of the record type. For example, Insured Party and Insured Item.
        
        [](https://help.salesforce.com/s?language=en_US)Note
        
        If you have both Digital Insurance and Insurance (Managed Package) installed on your org, don't use Product as the Record Type Label.
        
    4.  Set the record type as active to make it available to all profiles, and click **Next**.
    5.  Assign Product Layout to all profiles, and then save your changes.

[](https://help.salesforce.com/s?language=en_US)

## Create Product Specification Type

Create InsuredParty, InsuredItem, Product, and Coverage product specification types.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Revenue Cloud</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create product specification type: | Manage Product Catalog |

Important Only Salesforce Admins can set up specification types.

1.  From Setup, in the Quick Find box, find and select **Product Specification Type**.
2.  Create a new product specification type.
    1.  Click **New Product Specification Type**.
    2.  In Name, enter the name of the product specification type. For example, InsuredParty and InsuredItem.
    3.  Save your changes.

[](https://help.salesforce.com/s?language=en_US)

## Create Product Specification Record Type

Create InsuredParty, InsuredItem, Product, and Coverage product specification record types.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Revenue Cloud</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create product specification record type: | Manage Product Catalog |

1.  From Setup, in the Quick Find box, find and select **Product Specification Record Type**.
2.  Create a new product specification record type.
    1.  Click **New Product Specification Record Type**.
    2.  In Label, enter the name of the product specification record type. For example, InsuredParty and InsuredItem.
    3.  Select the corresponding record type and product specification type.
    4.  Set IsCommercial Flag to True.
    5.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo