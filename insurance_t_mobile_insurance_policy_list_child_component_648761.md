---
title: "Mobile Insurance Policy List Child Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_policy_list_child_component_648761.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Mobile Insurance Policy List Child Component

Mobile Insurance Policy List Child Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Mobile Insurance Policy List Child Component

Display a list of insurance policies your mobile Policyholder site users have with the Mobile Insurance Policy List Child component. It's a child component that sits inside of the Mobile Insurance Policy List component container and displays information about policies the user has.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insPolicyListChildMobile\_nds
    
-   LWC: cfIinsPolicyListChildMobile\_nds
    

This component is designed for mobile. Looking for the Insurance Policy List Child component designed for desktop? Read Insurance Policy List Child Component.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

[](https://help.salesforce.com/s?language=en_US)

Here's what the Mobile Insurance Policy List component looks like when it's rendered in the Policyholder site:

Here's what the Mobile Insurance Policy List Child Component Looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Policy name link
    
    A user can click this link to go to the Details page for this policy.
    
2.  Policy status
    
3.  Policy number
    
4.  Total premium amount
    
5.  Policy term
    
    The effective date - expiration date of the policy
    
6.  Policyholder name
    
7.  An action that launches the Insurance Policy List Flyout Component.
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

-   Click the name of the policy to go to the policy details page
    
-   Click the View Details link to see details about the premium and surcharges for this policy
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard has two state elements:

1.  Active: the state that displays when records are available
    
2.  Open: the state that displays when there are no records available
    

[](https://help.salesforce.com/s?language=en_US)

To learn more about how to work with FlexCard states, read [FlexCard States](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcard_states.htm&language=en_US&type=5) .

This FlexCard contains lots of elements, including:

-   Text elements that display labels we typed in
    
-   Text elements that have conditions set to hide and show the element in the FlexCard based on information from the data source
    
-   Text elements that hold links to other pages in the Policyholder site
    
-   Field elements with output selected from available fields returned from the data source
    
-   Action element that calls the child card **insPolicyListFlyout**
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Source Called by this Component

This component calls an Omnistudio Data Mapper named **InsReadAccountPolicies**.

This Data Mapper fetches information from policies the user has. Fields in the FlexCard reflect the information gathered by the Data Mapper.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo