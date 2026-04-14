---
title: "Configure Networks on a Root Plan Spec"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_networks_on_a_root_plan_spec.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Networks on a Root Plan Spec

Configure Networks on a Root Plan Spec[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Networks on a Root Plan Spec

You can add existing provider networks to root plan (product) specs. Based on how you've configured the coverage specs on the root plan spec, you can map each provider network to specific coverage specs.

Before You Begin

-   Configure all the provider networks you want to use.
    
    Note
    
    Make sure that all provider networks you want to use are set to Active.
    
-   Make sure that the coverage specs contain attributes with the Attribute Group Type set correctly.
    

Later, when an insurance agent or customer service rep is quoting a plan, they can see the networks that are attached to the root plan spec. The agent working on the quote can configure attributes specific to each network on each coverage in a plan.

By the time you get to mapping provider networks to plan specs, you've already completed most of this workflow:

The most common examples of Attribute Group Types are In-Network and Out of Network, often used for health plans. When you map provider networks onto root plan specs, Attribute Group Types = Tiers. For example, you can associate a configured provider network to the In-Network tier.

1.  On the root plan (product) you want to configure networks on, go to the **Network** tab.
2.  Click **Add Network**.
3.  Select a **Network**.
4.  Under **Product**, choose the coverage spec you want to attach this network to.
5.  Under **Jurisdiction**, choose the jurisdiction (location) that this network will be effective in.
    
    Note
    
    This field is mandatory because large group quotes use Jurisdiction to find applicable provider networks.
    
6.  Under **Tier**, select the tier that this network applies to.
    
    Tier = the Attribute Group Type you choose when you configure an attribute on the Attribute Designer.
    
7.  Enter a **Start Date** when this network configuration goes into effect.
8.  (Optional) Enter an **End Date** for when you want this network configuration to stop working.

Did this article solve your issue?

Let us know so we can improve!

YesNo