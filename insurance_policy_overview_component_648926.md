---
title: "Insurance Policy Overview Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_overview_component_648926.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Overview Component

Insurance Policy Overview Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Overview Component

Show your Policyholder site users key information about their policy with the Insurance Policy Overview Component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insPolicyOverview\_nds
    
-   LWC: cfInsPolicyOverview\_nds
    
-   Label: **Insurance Policy Overview Newport**
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Policy Overview component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Policy owner name
    
2.  Policy renewal date
    
3.  Policy mailing address
    
4.  Total policy premium
    
5.  Payment plan number
    
6.  **View more details** button
    
    More details display in the Insurance Policy List Flyout Component.
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains many elements, including:

-   Text elements that display labels we typed in.
    
-   Field elements whose output is selected from available fields returned from the data source.
    
-   Flyout action element that contains the insPolicyListFlyout\_nds child card.
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Sources Called by this Component

This component calls an Omnistudio Data Mapper named insGetPolicyDetails.

This Data Mapper fetches information from the user's policy record. Elements in the FlexCard reflect information gathered by the Data Mapper.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo