---
title: "Insurance Account Quote List Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_quote_list_component_644983.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Account Quote List Component

Insurance Account Quote List Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Account Quote List Component

On this component, brokers see a list of all the quotes attached to a specific account.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: **insAccountQuoteList**
    
-   LWC: **cfInsAccountQuoteList**
    
-   Label: **Insurance Account Quote List**
    

This component is optimized for both mobile and desktop.

[](https://help.salesforce.com/s?language=en_US)

This component uses the Lightning design system. Newport isn't supported.

Here's what the Account Quote List component looks like when it's rendered in the Broker site:

The Insurance Account Quote List component is the part inside the yellow rectangle.

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Icon for the quote
    
2.  Quote name link
    
    A user can click this link to go to the Details page for this quote
    
3.  Quote number
    
4.  Total premium amount
    
5.  Effective date
    
    The starting date for the quoted policy (if the customer buys the policy)
    
6.  Expiration date
    
    The date the quoted policy will expire (if the customer buys the policy)
    
    Note
    
    This is not the expiration date of the quote itself.
    
7.  Link to additional information about this quote
    
8.  Quote status
    

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

-   Click the name of the quote to go to the quote details page
    
-   Click the **View Details** link to see details about the premium calculations for this quote
    

[](https://help.salesforce.com/s?language=en_US)

## What this Component Does

This component pulls information about all the quotes connected to the specified account and displays each quote with supporting data in a list.

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This card has two states:

1.  Active: Quotes present for the specified account
    
    When there's more than one quote attached to an account, an instance of this FlexCard structure is populated for each quote and displayed in a list.
    
2.  Inactive: No quotes present for the specified account
    

[](https://help.salesforce.com/s?language=en_US)To learn more about how to work with FlexCard states, read [FlexCard States](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcard_states.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

You can add, remove, and change any of these elements based on what you want your users to see. To learn how see [Add Elements to a FlexCard](https://help.salesforce.com/s/articleView?id=xcloud.os_add_elements_to_a_flexcard.htm&language=en_US&type=5). Other good topics to read to learn about how this FlexCard works include [FlexCards Display Elements Reference](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_display_elements_reference.htm&language=en_US&type=5), [FlexCards Menu Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_menu_properties.htm&language=en_US&type=5), and [FlexCards Action Properties](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcards_action_properties.htm&language=en_US&type=5).

Many of the elements of this card contain Custom CSS styles. You can make changes to these styles to create a different look and feel. To learn how to work with Custom CSS in FlexCards, see [Apply Custom CSS to a FlexCard Element](https://help.salesforce.com/s/articleView?id=xcloud.os_apply_custom_css_to_a_flexcard_element.htm&language=en_US&type=5) .

[](https://help.salesforce.com/s?language=en_US)

## Data Sources Called by this Component

This component calls an Omnistudio Data Mapper named InsGetAccountQuoteList.

This Data Mapper pulls information from each quote attached to the specified account. Elements in the FlexCard include keys that get replaced by the values in the Data Mapper and displayed to the user.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo