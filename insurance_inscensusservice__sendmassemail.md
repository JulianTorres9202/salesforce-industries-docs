---
title: "InsCensusService:sendMassEmail"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__sendmassemail.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsCensusService:sendMassEmail

InsCensusService:sendMassEmail[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:sendMassEmail

Use this service to send emails to all members of a census. For example, you can use this service to send an invitation to enroll in a health insurance plan to all members of a customer's census.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `sendMassEmail`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

If both remote options are not null, the service queries the **contactId** for primary census members and sends an email to them using the email template. Note that the contact needs to be created beforehand and linked to the primary census member.

1.  Takes a `censusId` as a parameter and uses it to get `contactIds` for all census members.
    
2.  Finds the specified email template to construct the emails to be sent.
    
3.  Emails all members of the census using their `contactIds`.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`censusId`

 | 

The Id of the census to be emailed.

 |
| 

`emailTemplateName`

 | 

The name of an email template (previously loaded into Vlocity) that the service will use to construct the emails it sends.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not use an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service doesn't return data in an output JSON.

Did this article solve your issue?

Let us know so we can improve!

YesNo