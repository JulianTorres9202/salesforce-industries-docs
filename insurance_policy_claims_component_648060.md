---
title: "Insurance Policy Claims Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_claims_component_648060.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Claims Component

Insurance Policy Claims Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Claims Component

Show your Policyholder site users a snapshot of their open claims on a policy and link them to additional information about the claims with the Insurance Policy Claims component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insPolicyClaimsContainer\_nds
    
-   LWC: cfInsPolicyClaimsContainer\_nds
    
-   Label: **Insurance Policy Claims Container Newport**
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Policy Claims component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Text label:
    
    **Open Claims**
    
2.  Open claims displayed in a child component.
    
    Read about the Policy Claims child component hereInsurance Policy Claims Child Component.
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

Policyholder site users can click the name of the claim to go to the claim detail page.

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard has a text element that displays the label we chose and holds the insPolicyClaimsChild\_nds child FlexCard.

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

-   **[Insurance Policy Claims Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_claims_child_component_648123.htm&language=en_US&type=5)**  
    Use the Insurance Policy Claims Child component to show your Policyholder site users a snapshot of their open claims on a policy and link them to additional information about the claim. It's a child component that sits inside of the Insurance Policy Claims container component.

Did this article solve your issue?

Let us know so we can improve!

YesNo