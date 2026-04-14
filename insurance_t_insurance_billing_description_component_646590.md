---
title: "Insurance Billing Description Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_description_component_646590.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Billing Description Component

Insurance Billing Description Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Billing Description Component

Show your Policyholder site users an overview of their billing information with the Insurance Billing Description component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insBillingDescription\_nds
    
-   LWC: cfInsBillingDescription\_nds
    
-   Label: **Insurance Billing Description Newport**
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Billing Description component looks like when it's rendered in the Policyholder site:

The parts of this component are:

1.  Text label:
    
    **What's Due**
    
2.  Billing description displayed in a child component.
    
    Read about the Billing Description Child component [hereInsurance Billing Description Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_description_child_component_646670.htm&language=en_US&type=5 "Use the Insurance Billing Description Child component to show your Policyholder site users an overview of their billing information, and link them to additional information about their billing account. The Insurance Billing Description Child component sits inside of the Insurance Billing Description component container.").
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

Once you have configured the placeholder links in the child component to your specifications, you Policyholder site users can:

-   Click the **Make Payment** button to make a payment
    
-   Click the **View Statement** button to view the account statement
    
-   Click the **Manage Payment Method** button to update their payment details
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains:

-   A text element that displays the label we chose:
    
    **What's Due**
    
-   Child FlexCard: **insBillingDescriptionChild\_nds**
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

-   **[Insurance Billing Description Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_description_child_component_646670.htm&language=en_US&type=5)**  
    Use the Insurance Billing Description Child component to show your Policyholder site users an overview of their billing information, and link them to additional information about their billing account. The Insurance Billing Description Child component sits inside of the Insurance Billing Description component container.

Did this article solve your issue?

Let us know so we can improve!

YesNo