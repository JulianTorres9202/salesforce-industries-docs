---
title: "Attribute Grouping"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_grouping_604747.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Attribute Grouping

Attribute Grouping[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Attribute Grouping

Group Types are used for attributes that become part of group insurance products.

Groups are a way to classify attributes across categories. Attribute groups exist outside of the Attribute Category: Attribute hierarchy. For example, two Group Types for health, dental, vision, and voluntary benefit plans are In-Network and Out-of-Network.

When attributes include a group tag, the JSON gets this tag where these attributes are used. Vlocity uses attribute groups to create side-by-side comparisons of attributes and values that get displayed for users to see and compare.

When you model group plans, you can map these attribute groups to configured networks. To learn how, see [Configure Networks on a Root Plan Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_networks_on_a_root_plan_spec.htm&language=en_US&type=5 "You can add existing provider networks to root plan (product) specs. Based on how you've configured the coverage specs on the root plan spec, you can map each provider network to specific coverage specs.").

If you haven't mapped the attribute groups to configured networks, the attribute group labels show up in the Large Group Quote UI.

Did this article solve your issue?

Let us know so we can improve!

YesNo