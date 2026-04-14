---
title: "Calculation Procedures"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_calculation_procedures_514679.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Calculation Procedures

Calculation Procedures[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Calculation Procedures

The Marine rating procedure calls the following calculation procedures:

-   wc2-Watercraft
    
-   wc2-WatercraftPolicyLevel
    

We expect that you'll create your own calculation procedure to rate vessels for your marine insurance products. You can use the wc2-Watercraft and wc2-WatercraftPolicyLevel calculation procedures as models, and make changes to them so you can see how calculation procedures work.

You can't make changes to an enabled calculation procedure. To disable a calculation procedure:

1.  On the version of the calculation procedure you want to change, go to the **Details** tab.
2.  Click the edit (pencil icon) next to Enabled, then uncheck the box.
3.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo