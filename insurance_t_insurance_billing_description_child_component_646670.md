---
title: "Insurance Billing Description Child Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_description_child_component_646670.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Billing Description Child Component

Insurance Billing Description Child Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Billing Description Child Component

Use the Insurance Billing Description Child component to show your Policyholder site users an overview of their billing information, and link them to additional information about their billing account. The Insurance Billing Description Child component sits inside of the Insurance Billing Description component container.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insBillingDescriptionChild\_nds
    
-   LWC: cfInsBillingDescriptionChild\_nds
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Billing Description Child component looks like when it's rendered in the Policyholder site:

The parts of this component are:

1.  Total amount due
    
2.  The due date
    
3.  Child FlexCard: **insPolicyBillingChild\_nds**
    
    Displays the policy name and amount due for each policy the user has.
    
4.  **Make Payment** button that opens the payment window
    
5.  **View Statement** button that serves as a placeholder to configure an action that launches an account statement window.
    
6.  Account billing information including:
    
    -   Billing Account Number
        
    -   Card Type
        
    -   Payment Method
        
7.  **Manage Payment Details** button that serves as a placeholder to configure an action that launches an account statement window.
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

Once you have configured the placeholder links to your specifications, your Policyholder site users can:

-   Click the **Make Payment** button to make a payment
    
-   Click the **View Statement** button to view the account statement
    
-   Click the **Manage Payment Method** button to update their payment details
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard has two state elements:

1.  Active: the state that displays when records exist
    
2.  Open: the state that displays when no records exist
    

[](https://help.salesforce.com/s?language=en_US)

To learn more about how to work with FlexCard states, read [FlexCard States](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcard_states.htm&language=en_US&type=5) .

This FlexCard contains lots of elements, including:

-   Text elements that display labels we typed in
    
-   Text elements that have conditions to hide or show the element based on returned data from the data source
    
-   Field elements with output selected from available fields returned from the data source
    
-   Action elements with placeholder links
    
-   Child FlexCards: **insPolicyBillingChild\_nds** and **InsBillingStrategyChild\_nds**.
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Source Called by this Component

This component calls an Omnistudio Data Mapper named **InsExtractAccountBilingDetails**.

This Data Mapper extracts the billing information from the user's account. Fields in the FlexCard reflect the information gathered by the Data Mapper.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

-   **[Insurance Policy Billing Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_policy_billing_child_component_646789.htm&language=en_US&type=5)**  
    Show your Policyholder Experience site users an overview of the amount due for their policies with the Insurance Policy Billing Child component. The Insurance Policy Billing Child component sits inside of the Insurance Billing Description Child component container.
-   **[Insurance Billing Strategy Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_billing_strategy_child_component_646852.htm&language=en_US&type=5)**  
    Provide your Policyholder site users with billing option strategies the help them manage their accounts with the Insurance Billing Strategy Child component. The Insurance Billing Strategy Child component sits inside of the Insurance Billing Description component.

Did this article solve your issue?

Let us know so we can improve!

YesNo