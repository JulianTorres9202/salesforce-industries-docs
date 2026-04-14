---
title: "Add Components to a Configurable Product Bundle"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_add_components_to_bundle.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Add Components to a Configurable Product Bundle

Add Components to a Configurable Product Bundle[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Components to a Configurable Product Bundle

You can add multiple groups, multiple product components, or one product classification component under a product group in configurable bundles.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

-   Groups are mandatory components in a configurable product bundle. Child components must be added only under Groups and not directly under the root product.
-   Product groups are structured hierarchically, where a root group acts as the parent and can contain multiple child groups. While a root group can include multiple child product groups, multiple product components, or a single product classification, this hierarchy is limited to two levels; child groups can't contain further nested groups, and these elements can't be mixed at the same level within a child group. For example, a child group can't contain both product components and a product classification. A product classification can only be added once per group.
-   When you delete a group, all components under the group, such as products and product classifications, are deleted.
-   You can add simple and bundled products of type static or configurable as child components of a configurable bundle.
-   When adding a child component with a defined unit of measure to a configurable product bundle, the Quantity, Min Quantity, and Max Quantity fields automatically inherit the scaling and rounding method of the child component.

To dynamically add all products based on a product classification to a product bundle, add a product classification component under the group. Product Catalog Management dynamically makes all products based on the classification available at the time of selection at run time. We refer to adding a product classification component to a product bundle as Dynamic Options.

1.  From the Product Catalog Management app's home page, click **Products**.
2.  From the product list view page, click the bundled product. For example, Auto Claim.
3.  Navigate to the Structure tab.
4.  To add a group, click + under the root product or the parent group, and select **Product Group**.
    
    You can add a group under a parent group only when the parent group doesn't have a product classification component or product components. Product groups are mandatory in a configurable bundle hierarchy.
    
5.  Specify these details:
    1.  Enter a group name, description, and code. For example, Damaged Property Group, DamagedPropertyGroup
        
        Parent Group is the group under which you add a child group. If you're adding the group under the root product, leave the Parent Group field blank.
        
    2.  Save your changes.
6.  To add a product classification under the group, click + under a group, select **Product Classification**, and specify these details:
    1.  Select a product classification. For example, Damaged Property Class
    2.  Click **Next**.
    3.  Save your changes.
7.  Follow Steps 5 and 6 to add another product classification for Injury with values such as Injury Group, InjuryGroup, and Involved Injury Class.
8.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo