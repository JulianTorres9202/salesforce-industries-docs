---
title: "Create Bundled Products"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_create_prd_bundles.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Bundled Products

Create Bundled Products[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Bundled Products

Bundled products are a group of products that are sold together as one unit.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

For configurable products, you can add or remove child products, alter product quantities, and configure product attributes at run time.

1.  From the Product Catalog Management app's home page, click **Products**.
2.  From the product list view page, click **New**.
3.  Select a record type. The record type options appear only if your product designer has set up product specification types and product specification record types. The specification type field in the product takes the value of the product specification type associated with the record type. For example, Claim.
4.  In the New Product window, specify the following values:
    1.  Enter a name and description for the product. For example, Auto Claim Root
    2.  Enter a product code.
    3.  To assign product attributes, select a product classification using the **Based On** field. For example, Auto Claim Root Class. It can be entered by using Type ahead).
    4.  Select **Bundle** under Product Type. This is what makes the product a bundled product.
    5.  To make the product available for purchase, select **Active**.
    6.  To create a configurable product bundle, select **Allowed** under Configure During Sale.
5.  Select **Is Assetizable** if the product instance must persist and become a customer asset after the customer purchases it. The default value is true.
    
    The value of Is Assetizable on the root product of a product bundle applies to all child products in the bundle. For example, if Is Assetizable is selected on the root product, then every child product in the bundle is assetizable irrespective of the Is Assetizable value on the child product.
    
6.  Save your changes.
7.  Repeat Steps 2 through 6 to create products for Damaged Property and Involved Injury by using the details below.
    
    | product name | product code | based on | specification type | configure during sale | active | is assetizable |
    | --- | --- | --- | --- | --- | --- | --- |
    | Involved Injury | InvolvedInjury | Involved Injury Class | Claim Injury | Allowed | Yes | Yes |
    | Damaged Property | DamagedProperty | Damaged Property Class | Damage Property | Allowed | Yes | Yes |
    

After you create a product, you can assign it to catalog categories and subcategories. You can also configure product attributes. You can also add components to the bundle structure.

Did this article solve your issue?

Let us know so we can improve!

YesNo