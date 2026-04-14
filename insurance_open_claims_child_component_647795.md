---
title: "Open Claims Child Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_open_claims_child_component_647795.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Open Claims Child Component

Open Claims Child Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Open Claims Child Component

Use the Insurance Open Claims Child component to show your Policyholder site users a snapshot of their open claims, and link them to additional information about the claims. It's a child component that sits inside of the Insurance Open Claims container component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insAccountClaimsChild\_nds
    
-   LWC: cfInsAccountClaimsChild\_nds
    

This component is designed for desktop. Looking for the Open Claims Child component designed for mobile? Read [Mobile Insurance Open Claims Child Component](https://help.salesforce.com/s/articleView?id=ind.insurance_mobile_insurance_open_claims_child_component_647961.htm&language=en_US&type=5 "Use the Mobile Insurance Open Claims Child component to show your Policyholder site users a snapshot of their open claims, and link them to additional information about the claims. It's a child component that sits inside of the Mobile Insurance Open Claims container component.").

This component uses the Newport Design System.

Here's what the Open Claims Child component looks like when it's rendered in the Policyholder site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  An icon to denote the type of claim
    
2.  The claim name
    
    Users can click the name to go to the claim details record.
    
3.  The date the loss was reported
    
4.  The claim
    
5.  The status of the claim
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

Policyholder Experience users can click the name of the claim to go to the claim details page.

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard has two state elements:

1.  Active: the state that displays when records are available
    
2.  Open: the state that displays when there are no records available
    

[](https://help.salesforce.com/s?language=en_US)

To learn more about how to work with FlexCard states, read [FlexCard States](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcard_states.htm&language=en_US&type=5) .

This FlexCard contains lots of elements, including:

-   Icon elements that have conditions to determine which icon is shown based on the type of claim
    
-   Text elements that display labels we typed in directly
    
-   Text elements that have conditions to hide if no data is returned from the data source
    
-   Actions elements that link the user to other pages in the Policyholder site
    
-   Field elements whose Output is selected from available fields returned from the data source.
    

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Source Called by this Component

This component calls an Omnistudio Data Mapper named **InsReadAccountPolicyClaims**.

This Data Mapper fetches information from recent claims associated with the user's account. Fields in the FlexCard reflect the information gathered by the Data Mapper.

[](https://help.salesforce.com/s?language=en_US)Important To display the amount of the claim, you need to update the Data Mapper mapping. Change the output for `InsPolicyClaim:ApprovedAmount` in the Data Mapper from TotalAmount to TotalPrice.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo