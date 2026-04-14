---
title: "Insurance Account Asset Record Header Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_insurance_account_asset_record_header_component_645367.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Account Asset Record Header Component

Insurance Account Asset Record Header Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Account Asset Record Header Component

This component shows brokers a snapshot of data about the asset-based policy they're looking at.

[](https://help.salesforce.com/s?language=en_US)

This component is composed of a FlexCard and the LWC compiled from the FlexCard:

-   FlexCard: **insAccountAssetHeader**
    
-   LWC: **cfInsAccountAssetHeader**
    
-   Master Label: **Insurance Account Asset Record Header**
    

[](https://help.salesforce.com/s?language=en_US)

This component is optimized for both desktop and mobile.

[](https://help.salesforce.com/s?language=en_US)

This component uses the Lightning design system. Newport isn't supported.

Here's what the Policy (Asset) Record Header component looks like when it's rendered in the Broker site:

[](https://help.salesforce.com/s?language=en_US)

The parts of this component are:

[](https://help.salesforce.com/s?language=en_US)

1.  Policy icon.
    
2.  The name of this policy.
    
3.  The account name attached to this policy.
    
4.  The effective date of this policy.
    
5.  The type of policy.
    
6.  The total premium for this policy.
    
7.  Weather information at the policyholder's location.
    
8.  Status of this policy.
    
9.  Map showing this policyholder's location.
    

[](https://help.salesforce.com/s?language=en_US)

## FlexCard Structure

[](https://help.salesforce.com/s?language=en_US)

1.  **insRecordHeader** Custom LWC
    
    This LWC structures data pulled from the record by the data source and adds the weather component from Google.
    

[](https://help.salesforce.com/s?language=en_US)

## Data Sources Called by this Component

This component calls an Integration Procedure named **InsRecordHeaderAsset\_getDetails** as its data source.

If you want to change what data is pulled into the Policy Record Header, you can open and make changes to this Integration Procedure.

[](https://help.salesforce.com/s?language=en_US)The JSON output of this Integration Procedure looks like this:

[](https://help.salesforce.com/s?language=en_US)`{     "recordImage": "https://url.to/companylogo.jpg",     "recordName": "Edge Communications",     "fallbackIcon": "standard:account",     "backgroundImage": "https://maps.googleapis.com/maps/api/staticmap?center=Salesforce%20Tower&size=400x300&key=API_KEY",     "fields": {         "Address": "123 Front St. San Francisco, CA 94040",         "Lead Agent": "Aaron Smith",         "Client Phone": "(512) 757-6000",         "Total Premium": "$3,100.00",         "Total Commission": "$425.00"     },      "weather": {         "icon": "http://openweathermap.org/img/wn/10d.png",         "description": "Sunny",         "temperature": 75     },      "status": {         "value": "Active",         "fontColor": "#0070d2",         "backgroundColor": "#b0c4df"     } }`

[](https://help.salesforce.com/s?language=en_US)

## Customize this Component

To learn about how to customize this kind of component, see the Digital Experience Site Component Customization Overview

-   **[Change the API Keys for Google Map](https://help.salesforce.com/s/articleView?id=ind.insurance_change_the_api_keys_for_google_map_2.htm&language=en_US&type=5)**  
    You'll probably need to change the API key for the Google Map and weather objects on this component. You do this in the Integration Procedure.

Did this article solve your issue?

Let us know so we can improve!

YesNo