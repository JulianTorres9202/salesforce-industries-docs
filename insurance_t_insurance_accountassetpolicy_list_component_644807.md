---
title: "Insurance Account (Asset) Policy List Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_accountassetpolicy_list_component_644807.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Account (Asset) Policy List Component

Insurance Account (Asset) Policy List Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Account (Asset) Policy List Component

On this component, brokers can see a list plus key details about each policy attached to a specific account.

[](https://help.salesforce.com/s?language=en_US)Important

This component is designed to work for Vlocity Insurance implementations that use the Asset object model for policy data.

If you're looking for a policy list component to use with policies stored on the FSC Insurance Policy object model, see [Insurance Account Insurance Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_insurance_policy_list_component_644687.htm&language=en_US&type=5 "On this component, brokers can see a list plus key details about each policy attached to a specific account.").

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: **insAccountPolicyList**
    
-   LWC: **cfInsAccountPolicyList**
    
-   Label: **Insurance Account Policy List**
    

[](https://help.salesforce.com/s?language=en_US)

This component is optimized for both desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component uses the Lightning design system. Newport isn't supported.

Here's what the Account Policy List component looks like when it's rendered in the Broker site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

[](https://help.salesforce.com/s?language=en_US)

1.  Icon for the policy
    
2.  Policy name link
    
    A user can click this link to go to the Details page for this quote
    
3.  Policy number
    
4.  Total premium
    
    The value of TotalAmountForTerm
    
5.  Policy Term
    
    The effective date - expiration date of the policy
    
6.  Term
    
    The policy term
    
7.  Link to a flyout that displays the premium breakdown, including premium, taxes, and fees
    
8.  Policy status
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

[](https://help.salesforce.com/s?language=en_US)

-   Click the name of the policy to go to the policy details page
    
-   Click the **View Details** link to see details about the premium and surcharges for this policy
    

[](https://help.salesforce.com/s?language=en_US)

## What this Component Does

This component pulls information about all the policies connected to the specified account and displays each policy with supporting data in a list.

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains lots of elements, including:

[](https://help.salesforce.com/s?language=en_US)

-   Icon elements that display Salesforce SVG elements
    
-   Text elements that display labels we typed in directly
    
-   Text elements that have conditions set to pull and display text from the data source
    
-   Field elements that have Output set to pull and display data from the data source
    
-   Action element that calls the child card **insAccountPolicyListFlyout**
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)This card has two states:

[](https://help.salesforce.com/s?language=en_US)

1.  Active: Policies present for the specified account
    
    When there's more than one policy attached to an account, an instance of this FlexCard structure is populated for each policy and the instances are displayed in a list.
    
2.  Inactive: No policy present for the specified account
    

[](https://help.salesforce.com/s?language=en_US)To learn more about how to work with FlexCard states, read [FlexCard States](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcard_states.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Sources Called by this Component

This component calls an Omnistudio Data Mapper named `InsGetAccountPolicyList`.

[](https://help.salesforce.com/s?language=en_US)This Data Mapper pulls information from each policy attached to the specified account. Elements in the FlexCard include keys that get replaced by the values in the Data Mapper and displayed to the user.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

-   **[Insurance Account Policy List Flyout](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_policy_list_flyout_644916.htm&language=en_US&type=5)**  
    Users can click a link on the Insurance Account Insurance Policy List Component or the Insurance Account (Asset) Policy List Component component to see the contents of this component, which shows additional information about the price of the policy.

Did this article solve your issue?

Let us know so we can improve!

YesNo