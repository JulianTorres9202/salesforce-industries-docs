---
title: "InsVlocityActionService:notifyApplicant"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insvlocityactionservice_notifyapplicant.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsVlocityActionService:notifyApplicant

InsVlocityActionService:notifyApplicant[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsVlocityActionService:notifyApplicant

Use this service to send an email notification to applicants.

This service is used in Vlocity State Model workflows when the Vlocity Actions are configured.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsVlocityActionService`

Method: `notifyApplicant`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  [](https://help.salesforce.com/s?language=en_US)Takes an `Application__c` instance Id and retrieves the email address to be used as the recipient of the email notification.
    
    [](https://help.salesforce.com/s?language=en_US)If the Primary Applicant Contact (`PrimaryContactId__c`) field has a value, the service retrieves the email address in the contact record.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    In the case of Health Provider applications, this represents the Individual Provider applicant.
    
    [](https://help.salesforce.com/s?language=en_US)If the Account (`AccountId__c`) field has a value, the service retrieves the email address in the account record.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    In the case of Health Provider applicants, this would represent an Organizational Provider applicant.
    
2.  [](https://help.salesforce.com/s?language=en_US)Email is sent with the template specified in the `emailTemplateName` value from `invokeMethodInput`. The place holder {0} can be used in the template to be used as the application's reference link.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    {0} is the only available placeholder that can be used as a reference link.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`Id`

 | 

Required.

Id of the Application instance (`Application__c`)

 |
| 

`invokeMethodInput`

 | 

Required.

The `InvokeMethodInput__c` value set in the Vlocity Action instance is passed on at runtime during the execution of the Vlocity State Model.

Set the value for the `emailTemplateName` with the name of the `EmailTemplate` instance to be used for the email notification:

```
{'emailTemplateName': 'Applicant Notification Email Template'}
```

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

Here's the format for the input JSON:

```
{ 
   "Id": <Application__c Id>,
   "invokeMethodInput": {"emailTemplateName": <Email Template Name>}
}
```

And here's what a real-life example might look like:

```
{ 
   "Id": "a046g00000FGItyAAH",
   "invokeMethodInput": {"emailTemplateName": "Applicant Notification"}
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The output is a simple true/false success message.

```
{'emailSentSuccessfully': true/false}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo