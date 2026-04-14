---
title: "Create Product Attributes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_create_prd_attr.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Product Attributes

Create Product Attributes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Product Attributes

Create attributes to capture the characteristics or properties of products. You can define details such as attribute name, label, data type while creating an attribute.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

1.  From the Product Catalog Management app's home page, click **Attributes**.
2.  From the Attribute Definitions list view, click **New**.
3.  In the New Attribute Definition window, enter these field values:
    1.  For Label, enter the attribute label that runtime systems can use as a display name for the attribute.
    2.  For Source System ID, enter a unique identifier for the attribute in an external system that stores the attribute definitions.
    3.  For Data Type, select the type of data that the attribute holds. If you select Picklist, select a picklist from the Picklist field.
    4.  If this attribute is a required attribute, select **Required**. You can override this property when you assign the attribute to a product classification, or when a product inherits the attribute.
    5.  To activate an attribute, select **Active**. You can assign only active attributes to Product Classifications and Attribute Categories.
    6.  Enter a description for the attribute.
    7.  Enter a description for the attribute value.
    8.  Enter a Default Help Text. This field can store useful information for runtime users.
4.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo