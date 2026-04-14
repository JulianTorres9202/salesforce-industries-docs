---
title: "Build the Group Benefits Product Structure"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_model_build_product_strcuture.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Build the Group Benefits Product Structure

Build the Group Benefits Product Structure[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Build the Group Benefits Product Structure

Once products are created, build the bundle hierarchy to connect them. This defines how the Medical Platinum plan expands into group classes, members, and coverages.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create group benefits product model | Product catalog management administrator |

-   For coverage products, [create simple products](https://help.salesforce.com/s/articleView?id=ind.product_catalog_create_simple_products.htm&language=en_US&type=5).
-   For the root product, group summary, and group census member products, create a [bundled product structure](https://help.salesforce.com/s/articleView?id=ind.product_catalog_creation_of_a_bundled_product_structure.htm&language=en_US&type=5).

1.  Open the [Medical Platinum product](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_model_create_products.htm&language=en_US&type=5 "Create products for the Medical Platinum hierarchy. Root product is the top-level spec that defines an insurance product, such as a health, dental, or vision plan. It can include one or more group classes, members, and coverages.").
2.  Go to the Structure tab.
3.  Add a new product group (Product Component Group) to logically group related product options within a product bundle. Child components must be added only under Groups and not directly under the root product.
    1.  Click the plus icon under the root product and select **Product Group**.
    2.  Specify Group Summary as a group name.
    3.  Save your changes.
4.  Add the group summary product classification component under the Group Summary group.
    1.  Click the plus icon under the product group component, and select **Product Classification**.
    2.  Select **GroupSummary** and click **Next**.
    3.  Specify the association details and save your changes.
5.  Navigate to the Structure tab of the Group Summary Product and add these components to the product bundle.
    1.  Add a new product group to logically group related product options within a product bundle.
    2.  Click the plus icon under the root product and select **Product Group**.
    3.  Specify Group Census Member as a group name.
    4.  Save your changes.
6.  Add the product classification component under the group to dynamically add all products based on a product classification to a product bundle.
    1.  Click the plus icon under the product group component, and select **Product Classification**.
    2.  Select **Member** and click **Next**.
    3.  Specify the association details and save your changes.
7.  Navigate to the Structure tab of the Member-Medical Platinum product and add these components to the product bundle.
    1.  Add a new product group to logically group related product options within a product bundle.
    2.  Click the plus icon under the root product and select **Product Group**.
    3.  Enter Coverages as a group name.
    4.  Save your changes.
8.  Add the product component under the group.
    1.  Click the plus icon under the root product and select **Product**.
9.  Select one or more products with product specification type as Coverage, and click **Next**.
10.  Specify the component details and save your changes.
     1.  [Assign a product selling model to a product](https://help.salesforce.com/s/articleView?id=ind.product_catalog_product_selling_model.htm&language=en_US&type=5).
     2.  Assign a price book.
         
         1.  In the Price Books section, click **Add Standard Price**.
         2.  Ensure the root product is selected by default.
         3.  Select a price book.
         4.  Enter a list price for your product. This list price is used when the product is added to quote, however actual price is determined based on pricing procedure.
         5.  Select **One-Time** as the product selling model.
         6.  Save your changes.
         

Did this article solve your issue?

Let us know so we can improve!

YesNo