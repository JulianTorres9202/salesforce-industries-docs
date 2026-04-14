---
title: "Create and Set the RetainProductAttribJSON Custom Setting for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_and_set_the_retainproductattribjson_custom_setting_for_vlocity_insurance_and_vlocity_health.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create and Set the RetainProductAttribJSON Custom Setting for Insurance

Create and Set the RetainProductAttribJSON Custom Setting for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create and Set the RetainProductAttribJSON Custom Setting for Insurance

Most insurance companies use lots of attributes as part of insurance products. Unless you're planning a special setup that will not use attributes much, or you're already using information saved by `JSONAttribute` `__c`, create a custom setting called `RetainProductAttribJSON` and set it to `false`. This keeps `JSONAttribute__c` from saving attributes and speeds up your users' experience.

1.  From **Setup**, in the **Quick Find** box, enter Custom Settings.
2.  Click **Custom Settings**.
3.  Click **Manage** next to **CPQ Configuration Setup**.
4.  Click **New**.
5.  In **Name**, enter RetainProductAttribJSON.
6.  In **Setup Value**, enter:
    
    -   false: If you don't use `JSONAttribute``__c` records, choose false to keep Vlocity from saving and rendering unnecessary data.
        
    -   true: Only if you use `JSONAttribute``__c` records.
        
    
7.  Click **Save**.

Did this article solve your issue?

Let us know so we can improve!

YesNo