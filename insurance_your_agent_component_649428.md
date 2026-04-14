---
title: "Your Agent Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_your_agent_component_649428.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Your Agent Component

Your Agent Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Your Agent Component

Your Policyholder site users can view details and contact their agent from the Your Agent component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insYourAgent\_nds
    
-   LWC: cfInsYourAgent\_nds
    
-   Label: **Insurance Your Agent Newport**
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Your Agent component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Text label:
    
    **Your Agent**
    
2.  Agent icon pulled from the source data.
    
    Note
    
    An agent picture can also display next to the icon.
    
3.  Agent name and address
    
4.  Email button
    
    Opens an email modal with the agent's email address pre-filled.
    
5.  Website button
    
    Launches the agent's website in a new window.
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard contains several elements, including:

-   Text element that displays the label we typed in
    
-   Field elements with output selected from available fields returned from the data source
    
-   Elements with conditions to hide or show the element based on data returned from the DataRaptor
    
-   Action elements that launch new windows
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Source Called by this Component

The Your Agent component calls the InsReadAccountContactDetails Omnistudio Data Mapper.

The Data Mapper fetches details about the agent associated with the user's account. Fields in the FlexCard reflect the information gathered by the Data Mapper.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo