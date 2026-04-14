---
title: "InsProviderNetworkService:getProviders"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__getproviders.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProviderNetworkService:getProviders

InsProviderNetworkService:getProviders[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProviderNetworkService:getProviders

Use this service to get a list of Providers and Provider Networks, based on the contact name, postal code, or profile attributes.

Results are sorted only if the two new remote options, `contactLongitudeSort` , and `contactLatitudeSort`, are not empty and have valid values.

Results are sorted nearest to farthest, based on the contact's mailing address relative to the given coordinates (i.e., `contactLongitudeSort` and `contactLatitudeSort`).

Providers found from contacts without a mailing address are placed last in the sort.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsProviderNetworkService`

Method: `getProviders`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service searches Providers (Contacts) using the `contactFilter` (first name, last name, mailing postal code).
    
2.  Uses returned contacts as the `objectId` (where objectId\_\_c = contactId) to search the attributeAssignment table.
    
3.  Applies the `attributeFilter` (if used).
    
4.  Uses the `contactIds` to get `ProviderNetworks` from `ProviderNetworkMembers`.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`contactFilter`

 | 

Required.

Contact fields: FirstName, LastName, MailingPostalCode.

 |
| 

`attributeFilter`

 | 

Optional.

Profile attributes: `categoryname` and `attributename`.

 |
| 

`contactLongitudeSort`

 | 

Optional.

Longitude value of contact address as per `MailingLongitude`.

 |
| 

`contactLatitudeSort`

 | 

Optional.

Latitude value of contact address as per `MailingLatitude`.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo