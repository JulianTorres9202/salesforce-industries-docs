---
title: "Insurance Policy Details Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_details_component_648218.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Details Component

Insurance Policy Details Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Details Component

Show your Policyholder site users details about insured items associated with their policy with the Insurance Policy Details component.

Note

Looking for the Policy Details Component designed for FSC? Read [FSC Insurance Policy Details Component](https://help.salesforce.com/s/articleView?id=ind.insurance_fsc_insurance_policy_details_component_647316.htm&language=en_US&type=5 "Show your Policyholder site users details about insured items associated with their FSC policy with the FSC Insurance Policy Details component.").

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insPolicyItemsDetail\_nds
    
-   LWC: cfInsPolicyItemsDetail\_nds
    
-   Label: **Insurance Policy Details Newport**
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Policy Details component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Text label:
    
    **My Vehicles**
    
2.  Details about the insured item displayed in a custom Lightning web component.
    
    Clicking the **View more details** link opens an extended view of the insured item details.
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

Policyholder Experience users can click the **View more details** link to see an expansive breakdown of the details relating to the insured item. Your users can also click on drivers or insured items associated with the policy in this expanded view. This opens a window containing the record details.

Note

You can also set up an action that launches an OmniScript or a web page by defining the attribute `createNewAction` in the Lightning web component properties.

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains:

-   Text element that displays a label
    
-   The insPolicyItems custom Lightning web component
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Source Called by this Component

This component uses the `getPolicyDetails` method for the `InsuranceAssetHandler` Apex remote class to bring information into the Lightning web component.

The Lightning web component displays this information to your Policyholder Experience user.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo