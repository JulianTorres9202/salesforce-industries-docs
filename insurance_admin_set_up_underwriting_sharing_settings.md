---
title: "Configure Sharing Rules for Customer Community Users"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_set_up_underwriting_sharing_settings.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Configure Sharing Rules for Customer Community Users

Configure Sharing Rules for Customer Community Users[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Sharing Rules for Customer Community Users

Sharing rules give customer community users access to records that are relevant for using underwriting rules.

1.  From Setup, in the Quick Find box, find and select **Sharing Settings**.
2.  Click **Edit**.
3.  Now set these object values for the default internal access and default external access:
    
    | object | default internal access | default external access |
    | --- | --- | --- |
    | Stage Transition Underwriting Evaluation | Public Read & Write | Public Read & Write |
    | Underwriting Rule Group | Public Read Only | Public Read Only |
    
4.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo