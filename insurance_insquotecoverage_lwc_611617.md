---
title: "insQuoteCoverage Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquotecoverage_lwc_611617.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# insQuoteCoverage Lightning Web Component

insQuoteCoverage Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# insQuoteCoverage Lightning Web Component

This component shows users a coverage on a quote.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)This component works for desktop and is mobile responsive.

Most quotes will include many instances of this LWC, one for each coverage on an insurance product. In the following screenshot, each red box contains one instance of **insQuoteCoverage**.

The **insQuoteCoverage** LWC displays:

1.  An icon for the coverage
    
2.  Coverage name
    
3.  Premium price of the coverage
    
4.  Attribute name (one or more)
    
5.  Attribute value (one or more) (which may or may not be customizable by the user)
    
6.  **Add**/**Remove** button (optional coverages only)
    

[](https://help.salesforce.com/s?language=en_US)

## What Users Can Do on this LWC

Users working on quotes can do the following actions on this LWC:

-   Change attribute values
    
    Users can only do this on configurable attributes. These have a white background and might have a dropdown carat, radio buttons, or other controls.
    
    Non-configurable attributes have a gray background.
    
-   Add optional coverages to the quote
    
    Look for any coverage with an **Add** button
    
-   Remove optional coverages from the quote
    
    Look for any coverage with a **Remove** button
    

[](https://help.salesforce.com/s?language=en_US)

## What this LWC Does

**insQuoteCoverage** does a few things:

-   Updates the quote line item when a user changes an attribute value
    
-   Displays messages
    
-   Makes changes to the UI that's displayed to optimize for mobile users
    

[](https://help.salesforce.com/s?language=en_US)

## Services Called by this LWC

**insQuoteCoverage** doesn't call any services.

[](https://help.salesforce.com/s?language=en_US)

## Other LWCs Used by this Component

**insQuoteCoverage** includes the following LWCs inside it:

-   **pubsub**
    
-   **utility**
    
-   **insUtility**
    
-   **insCoverage**
    
-   **insAttributeCategory**
    

Did this article solve your issue?

Let us know so we can improve!

YesNo