---
title: "Insurance Billing Strategy Child Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_strategy_child_component_646852.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Billing Strategy Child Component

Insurance Billing Strategy Child Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Billing Strategy Child Component

Provide your Policyholder site users with billing option strategies the help them manage their accounts with the Insurance Billing Strategy Child component. The Insurance Billing Strategy Child component sits inside of the Insurance Billing Description component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: InsBillingStrategyChild\_nds
    
-   LWC: cfInsBillingStrategyChild\_nds
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains elements, including text elements that display text from the data source.

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Source Called by this Component

The Billing Strategy Child component uses Apex Remote calls (the `getNBARecommendations` method for `EinsteinStrategyService`) to find billing strategies that may help your Policyholder site user.

Note

To configure this component you need to create an [Einstein Strategy Service](https://help.salesforce.com/s/articleView?id=sf.https%3A%2F%2Fhelp.salesforce.com%2Fs%2F.htm&language=en_US&type=5) and name it getNBARecommendations.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo