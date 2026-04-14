---
title: "Insurance Quote Record Header"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_quote_record_header_645467.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Quote Record Header

Insurance Quote Record Header[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Quote Record Header

This component shows brokers a snapshot of data about the quote they're looking at. This info can help them get a quick idea of the status of the quote, including the quote status and the date the quote expires.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: **insQuoteHeader**
    
-   LWC: **cfInsQuoteHeader**
    
-   Master Label: **Insurance Quote Record Header**
    

[](https://help.salesforce.com/s?language=en_US)

This component is optimized for both desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component uses the Lightning design system. Newport isn't supported.

Here's what the Quote Record Header component looks like when it's rendered in the Broker site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  A Google Map reference to the location of the account.
    
2.  The name of this quote.
    
3.  The account name attached to this quote.
    
4.  The expiration date of this quote.
    
5.  The opportunity name attached to the quote.
    
6.  The total premium quoted.
    
7.  The quote number of this quote.
    
8.  Status of this quote.
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

[](https://help.salesforce.com/s?language=en_US)

1.  **insRecordHeader** Custom LWC
    
    This LWC structures data pulled from the record by the data source and adds the weather component from Google.
    

[](https://help.salesforce.com/s?language=en_US)

## Data Sources Called by this Component

This component calls an Integration Procedure named **InsRecordHeaderQuote\_getDetails**.

If you want to change what data is pulled into the Insurance Quote Record Header, you can open and make changes to this Integration Procedure.

This Integration Procedure comes out of the box with Vlocity Insurance.

The JSON output of this Integration Procedure looks like this:

```
{
    "recordImage": "https://url.to/companylogo.jpg",
    "recordName": "Edge Communications",
    "fallbackIcon": "standard:account",
    "backgroundImage": "https://maps.googleapis.com/maps/api/staticmap?center=Salesforce%20Tower&size=400x300&key=API_KEY",
    "fields": {
        "Address": "123 Front St. San Francisco, CA 94040",
        "Lead Agent": "Aaron Smith",
        "Client Phone": "(512) 757-6000",
        "Total Premium": "$3,100.00",
        "Total Commission": "$425.00"
    },
    "status": {
        "value": "Active",
        "fontColor": "#0070d2",
        "backgroundColor": "#b0c4df"
    }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

Did this article solve your issue?

Let us know so we can improve!

YesNo