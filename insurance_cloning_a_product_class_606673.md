---
title: "Clone a Product Class"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_cloning_a_product_class_606673.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Clone a Product Class

Clone a Product Class[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Clone a Product Class

If you plan to create multiple product classes with many similar details, child specs, rules, or attributes, save time by cloning the first one you create. Then edit the cloned product classes as needed.

1.  From the Product list view, open the product class you want to clone.
2.  Click Deep Clone in Batch.
    
    Depending on your UI, you may need to click the carat at the top right of the Product detail page, then choose Deep Clone in Batch.
    
    Note
    
    Because this cloning process copies all parts of a product class, which can include dozens of coverages and lots of rules in large product classes, it's run as a batch job.
    
3.  On the **Deep Clone in Batch** window that appears, click **Continue**.
4.  When the message appears telling you that the job has started, click the X to close the window.
5.  Go back to the Product list view. When the clone job is finished, a new product named `OriginalProductClassName - Cloned` appears.
6.  Open the cloned product class. On the **Details** tab, click **Edit**.
7.  Change the **Product Name** to a new product class name.
8.  Change the **Product Code** to a new product class code.
9.  Make any other changes to the details of the product class.
10.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo