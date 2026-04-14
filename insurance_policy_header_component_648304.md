---
title: "Insurance Policy Header Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_header_component_648304.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Header Component

Insurance Policy Header Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Header Component

Display the policy name and key policy data for your Policyholder Experience site users with the Insurance Policy Header Component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insHeaderPolicy\_nds
    
-   LWC: cfInsHeaderPolicy\_nds
    
-   Label: **Insurance Header Home Newport**
    

This component is designed for desktop. Looking for the Insurance Policy Header component designed for mobile? Read [Mobile Insurance Policy Header Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_policy_header_component_648386.htm&language=en_US&type=5 "Display the policy name and key policy data for your mobile Policyholder site users with the Mobile Insurance Policy Header Component.").

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Policy Header component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  A link that returns the user to the Home page
    
2.  Policy name
    
3.  Policy number
    
4.  Background image
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains lots of elements, including:

-   An active state element (labeled Policy Header Desktop)
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    You can update the background image in the style panel for the active state.
    
    The `Background Image` input is a relative path to reference the image in the `InsNewportPortalImages` static resource. You can change this image path to any accessible image.
    
-   Field elements with output selected from available fields returned from the data source
    
-   An action element with a link to return the user to the Home page
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Sources Called by this Component

The Policy Header component calls the InsGetPolicyDetails Omnistudio Data Mapper.

This Data Mapper extracts information about the user's policy. Fields in the FlexCard reflect the information gathered by the Data Mapper.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo