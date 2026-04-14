---
title: "Insurance Policy Transaction Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_transaction_component_649008.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Policy Transaction Component

Insurance Policy Transaction Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Policy Transaction Component

Show your Policyholder site users recent transactions on their policy with the Insurance Policy Transaction component. It's a container component that displays a label and a list of transactions in the child component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insPolicyTransactionsContainer\_nds
    
-   LWC: cfInsPolicyTransactionsContainer\_nds
    
-   Label: **Insurance Policy Transactions Container Newport**
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Policy Transaction component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  A text label:
    
    **Transactions**
    
2.  Transactions displayed in a child component.
    
    Read about the Policy Transactions Child component hereInsurance Policy Transaction Child Component.
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains:

1.  Text element that displays the label we type in
    
2.  Child Flexcard: **insPolicyTransactionsChild\_nds**
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn how to customize this kind of component, see [Digital Experience Site Component Customization Overview](https://help.salesforce.com/s/articleView?id=ind.insurance_digital_experience_site_component_customization_overview_649514.htm&language=en_US&type=5 "We've provided out-of-the-box components for Insurance Experience sites, but we know you'll probably want to brand them with your logos, icons, colors, and fonts for your customers to see. You can also customize the data that's displayed.").

-   **[Insurance Policy Transaction Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_transaction_child_component_649070.htm&language=en_US&type=5)**  
    Display a list of recent transactions on a policy to your Policyholder site users with the Insurance Policy Transaction Child component. It's a child component that sits inside of the Insurance Policy Transactions container component.

Did this article solve your issue?

Let us know so we can improve!

YesNo