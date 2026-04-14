---
title: "Mobile Insurance Recent Activity Child Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_mobile_insurance_recent_activity_child_component_649346.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Mobile Insurance Recent Activity Child Component

Mobile Insurance Recent Activity Child Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Mobile Insurance Recent Activity Child Component

Show your mobile Policyholder site users a snapshot of their recent activity with the Mobile Insurance Recent Activity Child component. It's a child component that sits inside of the Mobile Insurance Recent Activity container component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insRecentActivityChildMobile\_nds
    
-   LWC: cfInsRecentActivityChildMobile\_nds
    

This component is designed for mobile. Looking for the Recent Activity Child component designed for desktop? Read Insurance Recent Activity Child Component.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Mobile Insurance Recent Activity Child component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  The title of the activity.
    
    The title is an action that links the user to the activity record.
    
2.  The subtitle description.
    
3.  The activity status.
    
4.  The date the activity occurred.
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard has two state elements:

1.  Active: the state that displays when records are available
    
2.  Open: the state that displays when there are no records available
    

[](https://help.salesforce.com/s?language=en_US)

To learn more about how to work with FlexCard states, read [FlexCard States](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcard_states.htm&language=en_US&type=5) .

This FlexCard contains lots of elements, including:

-   Field elements with output selected from available fields returned from the data source
    
-   Text element that has a condition set to hide and show the element in the FlexCard based on information from the data source
    
-   Action element that links the user to the activity record
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Source Called by this Component

The Mobile Recent Activity Child component gathers data with the InsAccount\_GetStories Integration Procedure.

This Integration Procedure pulls information from the account record. Fields in the FlexCard reflect the information gathered by the Integration Procedure.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo