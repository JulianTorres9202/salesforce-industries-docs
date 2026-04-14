---
title: "Insurance Account Policy List Flyout"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_policy_list_flyout_644916.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Account Policy List Flyout

Insurance Account Policy List Flyout[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Account Policy List Flyout

Users can click a link on the Insurance Account Insurance Policy List Component or the Insurance Account (Asset) Policy List Component component to see the contents of this component, which shows additional information about the price of the policy.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: **insAccountPolicyListFlyout**
    
-   LWC: **cfInsAccountPolicyListFlyout**
    
-   Label: **Insurance Account Policy List Flyout**
    

This component is designed for both desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component uses the Lightning design system. Newport isn't supported.

Here's what the Account Policy List Flyout component looks like when it's rendered in the Broker site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  **Premium**
    
    Total premium for this policy
    
2.  **Taxes**
    
    Total taxes on this policy
    
3.  **Fees**
    
    Total fees for this policy
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

Users can view additional information about the breakdown of the premium price for this policy.

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains several elements, including:

-   Text elements that display labels we typed in directly
    
-   Field elements that have **Output** set to pull and display data from the parent card's data source
    

[](https://help.salesforce.com/s?language=en_US)

## Data Source

This component doesn't have its own data source. Instead, because it's a child card, it pulls values from its parent card's data source.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo