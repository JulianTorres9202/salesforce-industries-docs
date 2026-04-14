---
title: "When to Harmonize"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_when_to_harmonize.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# When to Harmonize

When to Harmonize[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# When to Harmonize

It's your choice to harmonize or not to harmonize, and when to do it. We have different recommendations based on whether you're a new or existing customer.

-   New customer
    
    Use the Salesforce data model from the start. You don't have any existing data to harmonize.
    
-   Insurance implementation in progress (but not on production yet)
    
    Consider harmonizing your data and using the Salesforce data model even if it means pivoting your implementation. This way you can benefit from new features as they become available in future releases.
    
-   Vlocity Insurance in production
    
    Not planning to change anything touching this model anytime soon? Hold off harmonizing for now.
    
    To benefit from new features in future releases, start planning your transition to the Salesforce data model.
    

Use the useVlocityPolicyModel custom setting to control whether your org uses the Salesforce data model. See [Enable or Disable the Insurance Industries Extension Data Model](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_the_pre_existing_insurance_industries_extension_data_model_598317.htm&language=en_US&type=5 "When you install or upgrade to the Insurance managed package and the Insurance Industries Extension package, the Insurance Policy core object model is automatically enabled. But if you're upgrading and you're not prepared to use the Insurance Policy core object model yet, use a custom setting to disable the use of the core object model until you're ready to make the switch.").

Did this article solve your issue?

Let us know so we can improve!

YesNo