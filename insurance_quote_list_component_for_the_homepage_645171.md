---
title: "Insurance Quote List Component for the Homepage"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_quote_list_component_for_the_homepage_645171.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Quote List Component for the Homepage

Insurance Quote List Component for the Homepage[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Quote List Component for the Homepage

Your brokers need to see the quotes they're working on in list form. This component displays that list.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: **insQuoteListCard**
-   LWC: **cfInsQuoteListCard**
-   Master label: **Insurance Quote List**

This component is optimized for desktop only.

[](https://help.salesforce.com/s?language=en_US)

This component uses the Lightning design system. Newport isn't supported.

Here's what the Quote List component looks like when it's rendered in the Broker site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Buttons that let your users sort the quotes.
2.  Menu that lets users filter the quotes.
3.  Line item for each quote.
4.  Quote name link.

[](https://help.salesforce.com/s?language=en_US)

## What Your Users Can Do on this Component

Users can do a bunch of things on this component:

-   Sort the quotes in the list
-   Filter the quotes in the list
-   Click the quote name or icon to see a few key details about the quote
-   Click the link below the quote name to open the quote's page

[](https://help.salesforce.com/s?language=en_US)

## What this Component Does

This component calls an Omnistudio Data Mapper to populate a list of quotes created by the broker who's logged in to the site.

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

Here's what the FlexCard for this component looks like:

1.  **insRecordListTable**
    
    This LWC displays the list of quotes and related controls in this component.
    

[](https://help.salesforce.com/s?language=en_US)

## Data Sources Called by this Component

This component calls the **InsGetQuoteByProducer** Data Mapper.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo