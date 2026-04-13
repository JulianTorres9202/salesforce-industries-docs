---
title: "Create and Add Benefit Product to the Product Component Group"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_benefit_product_create_add_pcg.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create and Add Benefit Product to the Product Component Group

Create and Add Benefit Product to the Product Component Group[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create and Add Benefit Product to the Product Component Group

Create the benefit products for each product classification and then add them to the product component group. For example, create Annual Deductible/ Individual and Annual Deductible/ Family benefit products under Annual Deductible product classification and then add them to the General Plan Information Product Component Group.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Expereince</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled.</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To build a product model: | [Product Catalog Management](https://help.salesforce.com/s/articleView?id=ind.product_catalog_user_permissions_for_product_catalog_management.htm&language=en_US&type=5) |

Use the same procedure to create all benefit products and add them to the product component group. For example, to create a Preventive Care benefit product and add it to the Outpatient Services product component group.

1.  Create benefit products for Annual Deductible/Individual and Annual Deductible/ Family benefit product:
    1.  Click **New** on the Products page, select Benefit, and then click Next.
    2.  Enter the benefit product information for Annual Deductible/Individual product and save your changes.
2.  Add all benefit products to the product component group:[](https://help.salesforce.com/s?language=en_US)
    1.  Open the Medical product record page and click **General Plan Information** in the Product Component Group related list.
    2.  Click **Add Products** in the Child Components related list.
    3.  Select **Annual Deductible/ Individual** and **Annual Deductible/ Family** and click **Next**.
    4.  Enter the sequence for both products and save your changes. For Annual Deductible/ Family to appear on top under General Plan Information, select 1.

In the Structure tab of the Medical product, you’ll see a structure like this at this stage.[](https://help.salesforce.com/s?language=en_US)

Did this article solve your issue?

Let us know so we can improve!

YesNo