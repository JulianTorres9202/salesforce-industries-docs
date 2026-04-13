---
title: "Set Up Insurance Surcharges"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_surcharges.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Set Up Insurance Surcharges

Set Up Insurance Surcharges

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Set Up Insurance Surcharges

Calculate applicable taxes and fees for Insurance quotes and policies by using surcharges.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform where DigitalInsuranceProductAdministrationAddOn is enabled.</td></tr></tbody></table>

[](https://help.salesforce.com/s?language=en_US)

## Create an Insurance Surcharge

To add a tax, fee, or discount to products, create a surcharge. You can apply surcharges to specific products, customers, or time periods and set them based on a percentage or a fixed amount.

### Required Editions

| User Permissions Needed |
| --- |
| To create surcharges: | Manage Revenue Cloud |

1.  From the App Launcher, find and select **Surcharges**.
2.  Click **New**.
3.  Enter a name, calculation type (Amount, Rate, or Expression Set), and effective dates.
4.  Depending on the calculation type selected, enter data in the appropriate field. For example, if you selected Amount in the calculation type field, input info in the Amount field.
5.  Save the new surcharge.

[](https://help.salesforce.com/s?language=en_US)

## Assign and Configure a Surcharge for a Product

To associate a specific surcharge to a product, assign it. Then, create rules to determine how and when the surcharge is applied.

### Required Editions

| User Permissions Needed |
| --- |
| To assign surcharges: | Manage Revenue Cloud |

1.  From the App Launcher, find and select **Products**.
2.  Select the product you want to add the surcharge to.
3.  On the product record page, open the Product Surcharge tab and then click **Add Product Surcharge**.
4.  Select the surcharge from the list of available surcharges, and then save your work.
5.  Select **Configure** from the dropdown menu for the surcharge.
6.  On the Create New Rule screen, click **Add Attribute** in the Conditions section.
7.  Add details about the attribute value to apply the surcharge to.
8.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo