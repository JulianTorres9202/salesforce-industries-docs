---
title: "Insurance Articles Child Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_articles_child_component_646525.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Articles Child Component

Insurance Articles Child Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Articles Child Component

Show your Policyholder site users articles that they might find helpful and interesting with the Insurance Articles Child component. It's a child component that sits inside of the Insurance Articles container component.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: insArticlesChild\_nds
    
-   LWC: cfInsArticlesChild\_nds
    

[](https://help.salesforce.com/s?language=en_US)

This component is designed for desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component is styled with the Newport Design System.

Here's what the Insurance Articles Child component looks like when it's rendered in the Policyholder site:

The parts of this component are:

1.  Article image
    
2.  Article title
    
3.  Article description
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

This FlexCard has two state elements:

1.  Active: the state that displays when records exist
    
2.  Open: the state that displays when no records exist
    

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)To learn more about how to work with FlexCard states, read [FlexCard States](https://help.salesforce.com/s/articleView?id=xcloud.os_flexcard_states.htm&language=en_US&type=5) .

This FlexCard contains field elements with output selected from available fields returned from the data source.

[](https://help.salesforce.com/s?language=en_US)

## Data Sources Called by this Component

The Articles Child component uses Apex Remote calls (the `getNBARecommendations` method for `EinsteinStrategyService`) to find articles that may interest your Policyholder Experience user.

Note

To configure this component, you need to create an [Einstein Strategy Service](https://help.salesforce.com/s/articleView?id=sf.https%3A%2F%2Fhelp.salesforce.com%2Fs%2F.htm&language=en_US&type=5) and name it getNBARecommendations.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo