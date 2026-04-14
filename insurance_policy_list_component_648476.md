---
title: "Insurance Policy List Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_list_component_648476.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy List Component

Insurance Policy List Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy List Component

Show your Policyholder site users a list of insurance policies they have with the Insurance Policy List component. It's a container component that displays a label and a list of policies in the Insurance Policy List Child component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insPolicyList\_nds
    
-   LWC: cfInsPolicyList\_nds
    
-   Label: **Insurance Policy List Newport**
    

This component is designed for desktop. Looking for the Insurance Policy List component designed for mobile? Read [Mobile Insurance Policy List Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_policy_list_component_648702.htm&language=en_US&type=5 "Show your mobile Policyholder site users a list of insurance policies they have with the Mobile Insurance Policy List component. It's a container component that displays a label and a list of policies in the Mobile Insurance Policy List Child component.").

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Policy List component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  A text label:
    
    Your Policies
    
2.  List of policies displayed in the child component.
    
    Read about the child component hereInsurance Policy List Child Component.
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains:

1.  Text element that displays the label we typed in
    
2.  Child FlexCard: insPolicyListChild\_nds
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

-   **[Insurance Policy List Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_list_child_component_648540.htm&language=en_US&type=5)**  
    Display a list of insurance policies your Policyholder site users have with the Insurance Policy List Child component. It's a child component that sits inside of the Policy List component container and displays information about all of the policies the user has.

Did this article solve your issue?

Let us know so we can improve!

YesNo