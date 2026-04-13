---
title: "Create Extended Attributes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_extended_attributes.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create Extended Attributes

Create Extended Attributes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Extended Attributes

Use extended attributes to centralize data and reduce duplication errors by dynamically pulling information from existing records, such as Contact or Account objects. For example, when adding a driver to a policy, extended attributes can automatically populate the driver’s contact information from a linked Contact record.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create extended attributes: | Manage Product Catalog |

To create an extended attribute, select a reference object and a field on that object. You can then associate the extended attributes with specific products.

-   **[Modify the Product Classification Attribute Reference Object Picklist](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_attribute_reference_object_picklist.htm&language=en_US&type=5)**  
    For each object you want to make available for extended attributes, add the API name to the Product Classification Attribute object.
-   **[Configure Product Classification Attributes to Be Extended Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_extend_attributes.htm&language=en_US&type=5)**  
    To make an extended attribute available across products in the same classification, update the product classification. For example, you can add the member first name and last name as extended attributes for all the products inheriting the product classification “Driver.”
-   **[Create the ID Extended Attribute](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_create_id_extended_attribute.htm&language=en_US&type=5)**  
    Whenever you configure an extended attribute from a field on a reference object, create an extended attribute for that object’s ID field on the same product or product classification.
-   **[Update Existing Extended Attribute Definitions](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_update_extended_attributes.htm&language=en_US&type=5)**  
    Prior to the Summer '25 release, AttributeNameOverride was used to look for an object in the record picker. If you have extended attribute definitions created prior to that release, check them to be sure the Code field of the attribute definition is set to the object's API name.

#### See Also

-   [Dynamic Attributes](https://help.salesforce.com/s/articleView?id=ind.product_catalog_dynamic_attributes.htm&language=en_US&type=5)
-   [Create Product Attributes](https://help.salesforce.com/s/articleView?id=ind.product_catalog_dyn_create_attributes.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo