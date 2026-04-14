---
title: "Mobile Insurance Manage Policy Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_manage_policy_component_647648.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Mobile Insurance Manage Policy Component

Mobile Insurance Manage Policy Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Mobile Insurance Manage Policy Component

Quickly link your mobile Policyholder site users to common policy management tasks with the Mobile Insurance Manage Policy component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insManagePolicy\_nds
    
-   LWC: cfInsManagePolicy\_nds
    
-   Label: **Insurance Manage Account Mobile Newport**
    

This component is designed for mobile. Looking for the Insurance Manage Policy component designed for desktop? Read [Insurance Manage Policy Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_manage_policy_component_647566.htm&language=en_US&type=5 "Quickly provide your Policyholder site users with links to common policy management tasks with the Insurance Manage Policy component.")

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Mobile Insurance Manage Policy component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Dropdown menu label:
    
    **Manage Policy**
    
2.  Actions that launch pre-defined OmniScripts
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    The actions that are available are dependent on the type of the policy.
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

Policyholder Experience users can use the links in the Mobile Insurance Policy Actions component to update their coverages.

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains many elements, including:

-   State elements with conditions on the policy type
    
-   Menu elements with actions
    
    Each of these actions launches an OmniScript.
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Source Called by this Component

The Policy Actions component calls the InsGetPolicyDetails DataRaptor.

The DataRaptor fetches policy information for use in the Manage Policy OmniScripts.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo