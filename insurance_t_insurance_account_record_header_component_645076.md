---
title: "Insurance Account Record Header Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_record_header_component_645076.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Account Record Header Component

Insurance Account Record Header Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Account Record Header Component

This component shows brokers a snapshot of data about the account they're looking at. This info can help them contact the account holder and chat about the weather in their location as an icebreaker.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: **insAccountHeader**
    
-   LWC: **cfInsAccountHeader**
    
-   Label: **Insurance Account Record Header**
    

This component is optimized for either desktop or mobile.

[](https://help.salesforce.com/s?language=en_US)

This component uses the Lightning design system. Newport isn't supported.

Here's what the Account Record Header component looks like when it's rendered in the Broker site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

1.  Icon for the Account
    
2.  Account name
    
3.  Account physical address
    
4.  Contact phone number
    
5.  Revenue
    
6.  Weather at the account location
    
7.  Map that displays the location of the account
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

The FlexCard structure you can work with looks like this:

1.  **insRecordHeader** Custom LWC
    
    This LWC structures data pulled from the record by the data source and adds the weather component from Google.
    

[](https://help.salesforce.com/s?language=en_US)

## Data Sources Called by this Component

This component calls an Integration Procedure named **InsRecordHeader\_getDetails** as its data source.

[](https://help.salesforce.com/s?language=en_US)The JSON output of this Integration Procedure looks like this:

[](https://help.salesforce.com/s?language=en_US)`{     "recordImage": "https://url.to/companylogo.jpg",     "recordName": "Edge Communications",     "fallbackIcon": "standard:account",     "backgroundImage": "https://maps.googleapis.com/maps/api/staticmap?center=Salesforce%20Tower&size=400x300&key=API_KEY",     "fields": {         "Address": "123 Front St. San Francisco, CA 94040",         "Lead Agent": "Aaron Smith",         "Client Phone": "(512) 757-6000",         "Total Premium": "$3,100.00",         "Total Commission": "$425.00"     },      "weather": {         "icon": "http://openweathermap.org/img/wn/10d.png",         "description": "Sunny",         "temperature": 75     },      "status": {         "value": "Active",         "fontColor": "#0070d2",         "backgroundColor": "#b0c4df"     } }`

If you want to change what data is pulled into the Account Record Header, you can open and make changes to this Integration Procedure.

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

-   **[Change the API Keys for Google Map](https://help.salesforce.com/s/articleView?id=ind.insurance_change_the_api_keys_for_google_map.htm&language=en_US&type=5)**  
    You'll probably need to change the API key for the Google Map object on this component. You do this in the Integration Procedure.

Did this article solve your issue?

Let us know so we can improve!

YesNo