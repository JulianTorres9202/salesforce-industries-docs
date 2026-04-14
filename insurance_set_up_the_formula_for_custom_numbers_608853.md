---
title: "Set Up the Formula for Custom Numbers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_the_formula_for_custom_numbers_608853.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up the Formula for Custom Numbers

Set Up the Formula for Custom Numbers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up the Formula for Custom Numbers

A custom numbering system can include specific information and you can establish a custom formula for that system.

1.  On the Setup page, go to Custom Metadata Types.
2.  Click **Vlocity UniqueId Generator Setting**.
3.  Look at the Custom Fields provided by Vlocity. Edit the existing custom fields or add new custom fields if you need to.
4.  Click **Manage Vlocity UniqueId Generator Settings**.
5.  Click **AssetSetting** > **Edit**.
6.  Change the label and name if needed.
7.  Choose the **Object Type** used by the product you're setting up numbers for.
    
    For example, for policy numbers, enter Asset into **Object Type**, for censuses select Census, and so forth.
    
8.  In the Format field, enter a formula for the policy number.
9.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)For example, you enter the following into the Format field: %Product2.ProductCode%+"-"+GLOBALAUTONUMBER()+"-"+YEAR(%ExpirationDate\_\_c%)

[](https://help.salesforce.com/s?language=en_US)With this formula, the policy number Vlocity generates will include the product code, the auto-generated number, and the expiration year of the policy. For example: `WHLLIFE50-VL-000028-2020`.

Did this article solve your issue?

Let us know so we can improve!

YesNo