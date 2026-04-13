---
title: "InsQuoteService:createUpdateQuote"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_ins"
---# InsQuoteService:createUpdateQuote

InsQuoteService:createUpdateQuote[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsQuoteService:createUpdateQuote

Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the `quoteId` of the quote to be updated must be included in the remote options.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

Before this service runs, the system runs a guest user check.

This service can be used by guest users. A guest user who's running an OmniScript, Integration Procedure, or UI task will be able to continue; this service will run. However, the `quoteId` and `opportunityId` are encrypted in these cases, so guest users cannot see these Ids.

Important

Use the InsQuoteService:createUpdateQuote service to update the Quote and Quote Line Items, instead of using the Omnistudio Data Mapper.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsQuoteService`

[](https://help.salesforce.com/s?language=en_US)

Method: `createUpdateQuote`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service searches the input JSON for the `inputKey`. The `inputKey` node contains the information that the service needs to create or update a quote. The information this service requires includes:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   `opportunityId`
        
    -   `endDate` (optional)
        
    -   `effectiveDate`
        
    -   `productConfigurationDetail` records
        
    -   `instanceKey`
        
        Required in order to identify multiple instance of the same spec
        
    -   `insuredItems` node
        
        Inside this node, the service expects a list of insured item specs and insured party specs, using each spec's `productCode` as a key.
        
    -   `Term__c`
        
        Use to update the Term\_\_c field of the Quote.
        
2.  Uses the information from the input JSON to create the quote.
    
3.  Returns a quote Id in the output JSON.
    
4.  Creates a Quote object that includes these line items:
    
    1.  Uses the root products defined in `productConfigurationDetail` to create or update the root quote line items.
        
    2.  When updating an existing quote, records in the `productConfigurationDetail` that are not yet in the quote will be added, and those already in the quote will be updated.
        
    3.  Uses insured item specs, insured party specs, and coverage specs as quote line items: `ParentItemId__c = rootItem.Id`.
        
    4.  The primary insured item's quote line item and child insured party quote lines have a many:many relationship. These relationships are stored in the Quote Item Relationship object. If an insured item quote line has relationships to multiple insured party quote lines, the `PrimaryChildLineitemId__c` field is used to determine which of those relationships is the primary one.
        
        [](https://help.salesforce.com/s?language=en_US)For example, both Joan Smith and John Smith are drivers of Lexus 250; Joan Smith is set as the Primary driver. The Lexus 250 quote line item has `PrimaryChildLineItemId__c` pointing to Joan Smith's quote line item. All quote line items' `ParentItemId2__c` point to `rootItem.Id.` Child coverages' `SubParentItemId__c` point to the primary insured item. The insured item quote line item and insured party quote line item `ItemName__c` fields are stored with this item's `instanceKey`.
        
    5.  The primary insured item's quote line item includes the price.
        
5.  [](https://help.salesforce.com/s?language=en_US)For new quotes, if `createOpportunity` is `true` and no `opportunityId` is provided, creates an Opportunity record using the `OpportunityDetails` JSON node from the `inputKey`.
    
6.  [](https://help.salesforce.com/s?language=en_US)If `calculateCommission` is `true`, calls `InsCommissionService.processQuoteCommission`, which prepares the input for the `InsCommissionService.calculate` service. After the calculate service processes the input, it stores the calculated commission value in `Quote.CommissionAmount__c`.
    

All users that call InsQuoteService:createUpdateQuote must have the Read permission for all fields in the Quote Detail field set if the field set is added to the Quote Line Item object.

If the Quote Detail field set isn't added to the Quote Line Item object all fields, including custom fields, are readable for users.

[](https://help.salesforce.com/s?language=en_US)

## Surcharges

Here's how this service works with surcharges (taxes and fees):

[](https://help.salesforce.com/s?language=en_US)

-   If the `taxesAndFees` field is specified on a JSON record, a corresponding `QuotePricingAdjustment__c` record persists for each item in the `taxesAndFees` list.
    
-   If the `taxAmount` field is specified on a JSON record, the `TaxAmount__c` field is set to the value of the `taxAmount` field on the created `QuoteLineItem`.
    
-   If the `feeAmount` field is specified on a JSON record, the `FeeAmount__c` field is set to the value of the `feeAmount` field on the created `QuoteLineItem`.
    

[](https://help.salesforce.com/s?language=en_US)

## Adding Additional Fields to Quote Line Items

If you need additional fields written to the Quote Line Item by this service, you'll need to call the InsProductJSONService:trimOffAttributeCategory service first.

[](https://help.salesforce.com/s?language=en_US)The flow to make this work in an OmniScript or integration procedure is:

[](https://help.salesforce.com/s?language=en_US)

1.  Product configuration steps
    
2.  InsProductJSONService:trimOffAttributeCategory service call with selectedValueAsObject set to true
    
3.  DataRaptor transform that can include mapping between attributes and your additional fields in the Quote Line Item object
    
4.  InsQuoteService:createUpdateQuote service call
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`createInsuredItemsRelationships`

 | 

`true` or `false`

If this option is set to `true`, you can specify a list of `instanceKey` > `parentInstanceKey` relationships between insured items.

This option supports parent > child and parent > child > grandchild insured item relationships.

 |
| 

`inputKey`

 | 

Required.

A JSON key that this service pulls necessary information from, in order to create or update a quote.

Do not use % to surround the value of this key. This key represents a JSON node, not a variable.

Because this key represents a JSON node and not a path, do not use parent:childnode:childnode path notation.

To get to the right data path, enter it into the **Send JSON Path** field in the **Send/Response Transformation** section when you add this key/value pair to an OmniScript step.

 |
| 

`insertInstance`

 | 

`true` or `false`

When set to `true`, the service inserts additional quote line items to an existing quote. It does not update the quote header, root line item, or any parent quote line item.

Use this option to create large multi-instance quote through multiple server calls, where the new set of quote line items of the instances are inserted to the existing quote in each call.

 |
| 

`quoteId`

 | 

Optional.

The Id of an existing quote that this service updates, based on new or updated information. Used when the service needs to update an existing quote.

 |
| 

`isMultiRoot`

 | 

Optional.

A Boolean flag to indicate if the quote is a multiroot quote.

Default is `false`.

 |
| 

`minimizeQliQuerySize`

 | 

`true` or `false`

When set to `true`, the service queries only the affected quote line items. Specifically, those quote line items that reference the product in the input product JSON node or in the insured items JSON node.

 |
| 

`populateCalcResults`

 | 

`true` or `false`

When set to `false`, the service does not populate both the `rootItem.CalculatedPriceJSON_c` field and the `Quote.CalculatedPriceJSON_c` field.

 |
| 

`pricebook`

 | 

Required.

The name of the pricebook associated with the product spec.

Salesforce requires that the products used in quote line items have a pricebook entry.

 |
| 

`recalculateTaxesAndFees`

 | 

`true` or `false`

When set to `true`, the service recalculates taxes and fees.

When set to `false`, the service doesn't recalculate taxes and fees.

Note

If you set this option to false, you also need to add a line to the `ins-coverage-quote-runtime-container` UI template.

In `ins-coverage-quote-runtime-container.js`, on line 115 enter `: optionsMap.recalculateTaxesAndFees = false`







 |
| 

`createOpportunity`

 | 

[](https://help.salesforce.com/s?language=en_US)`true` or `false`

When set to `true`, if no `opportunityId` is provided, the service creates a new Opportunity record using the `OpportunityDetails` JSON node from the `inputKey`. This node maps to fields on the opportunity `sObject`.

 |
| 

`returnQuote`

 | 

[](https://help.salesforce.com/s?language=en_US)`true` or `false`

When set to `true`, the service's output includes quote details in the `quoteDetail` JSON node.

 |
| 

`calculateCommission`

 | 

`true` or `false`

When set to `true`, the service calculates commissions for the root items and saves the total amount to `Quote.CommissionAmount`.

When set to `false` (the default), the service doesn't calculate commissions.

Note

If you set this option to true, you also need to input at least one of the producer or production code values: `primaryProducerId` , `productionCodeId`, or `productionCodeName`.







 |
| 

`primaryProducerId`

 | 

Optional.

The processing producer ID, that is, the producer used to retrieve the `commissionScheduleId` and calculate the commission amount.

 |
| 

`productionCodeId`

 | 

Optional.

The production code ID.

 |
| 

`productionCodeName`

 | 

Optional.

The production code name passed to the InsCommissionService.calculate service.

If you do not input `productionCodeId`, the service uses `productionCodeName` to look up the `productionCodeId`. If you input both values but they don't match, `productionCodeId` takes precedence.

 |
| `runEligibilityRequiredDefaultSelectedRules` | 

Optional.

Default values is `true`.

Determines whether Eligibility and Default Selected rules are run.

 |
| `runRelationshipRules` | 

Optional.

Default values is `true`.

Determines whether Relationship rules are run.

 |
| `runSelectedValivationRules` | 

Optional.

Default values is `true`.

Determines whether Select Validation rules are run.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service looks for the value of the `inputKey`. Go to the API tab on the product spec to find the input JSON you need for this service.

[](https://help.salesforce.com/s?language=en_US)For this example, `inputKey` = `quotePolicyJSON`.

[](https://help.salesforce.com/s?language=en_US)`"quotepolicyJson": {   "productConfigurationDetail": {     "records": [{           "rootProductId": "01t1I000002fuBoQAI",           "rootProductCode": "AUTOROOT",           "timestamp": 1534288040769,           "hasInstanceKeys": true,           "childProductsCount": 4,           "instanceKeyChildren": 2,           "pathFromChild": "[0]",           "pathFromRoot": "[0]",           "attributeCategories": {             "records": [{                 "productAttributes": {                   "records": [{                       "parentProductId": "01t1I000002fuBoQAI",                       "parentProductCode": "AUTOROOT",                       "pathFromChild": "attributeCategories.records[0].productAttributes.records[0]",                       "pathFromRoot": "attributeCategories.records[0].productAttributes.records[0]",                       "userValues": "test",                       "values": [{                         "disabled": false,                         "readonly": false                       }]                       "totalSize": 1                     },                     "id": "a1V1I0000007xJSUAY",                     "Name": "Alan Health Attributes",                     "Code__c": "AHA",                     "displaySequence": 5                   }                 ],                 "totalSize": 1               },               "childProducts": {                 "records": [{                     "rootProductId": "a2f1I000000BI6JQAW",                     "rootProductCode": "stolenProperty",                     "customizeSectionsOpen": null,                     "numberAttributes": 1,                     "numberCategories": 1,                     "originalIndex": 0,                     "parentProductName": "Auto Root",                     "pathFromRoot": "[0].childProducts.records[0]",                     "attributeCategories": {                       "records": [{                         "productAttributes": {                           "records": [{                             "parentProductId": "a2f1I000000BI6JQAW",                             "parentProductCode": "stolenProperty",                             "originalAttributeIndex": 0,                             "originalCategoryIndex": 0,                             "originalProductIndex": 0,                             "pathFromChild": "attributeCategories.records[0].productAttributes.records[0]",                             "pathFromRoot": "childProducts.records[0].attributeCategories.records[0].productAttributes.records[0]",                             "userValues": false,                             "values": [...]                               ...                           }]                           "totalSize": 1                         },                         "id": "a1V1I0000007xJSUAY",                         "Name": "Alan Health Attributes",                         "Code__c": "AHA",                         "displaySequence": 5                       }],                       "totalSize": 1                     },                     "childProducts": {                       ...                     }                     "Price": 80,                     "productId": "01t1I000002fuBoQAI",                     "Term__c": "Semi-Annual",                     "PricingFormula__c": "SUM(AutoPremium__autoPremium + rentalTotal + medicalTotal + roadsideTotal + dedWaiverTotal + uninsuredMotoristPDTotal + uninsuredMotoristBITotal)",                     "IsConfigurable__c": true,                     "RecordTypeName__c": "Product",                     "IsRecommended__c": false,                     "ProductCode": "AUTOROOT",                     "Name": "Auto Root",                     "Id": "01t1I000002fuBoQAI",                     "RawPriceData": [{                         "aggregationResults": {},                         "calculationResults": [{                             "ID": "0",                             "comprehensiveTotal": 500,                             "rentalTotal": 40,                             "medicalTotal": 10,                             "roadsideTotal": 10,                             "dedWaiverTotal": 10,                             "uninsuredMotoristPDTotal": 0,                             "uninsuredMotoristBITotal": 100,                             "AUTO.instanceKey": "2015 Lexus LX250",                             "DRIVER.FN": "Joan",                             "DRIVER.LN": "Smith"                           },                           "ID": "1",                           "comprehensiveTotal": 500,                           "rentalTotal": 40,                           "medicalTotal": 10,                           "roadsideTotal": 10,                           "dedWaiverTotal": 10,                           "uninsuredMotoristPDTotal": 0,                           "uninsuredMotoristBITotal": 100,                           "AUTO.instanceKey": "2015 Lexus LX250",                           "DRIVER.FN": "John",                           "DRIVER.LN": "Smith"                         },                         ...                       ]                     },                     {                       "aggregationResults": {},                       "calculationResults": [{                           "ID": "4",                           "comprehensiveTotal": 500,                           "rentalTotal": 40,                           "medicalTotal": 10,                           "roadsideTotal": 10,                           "dedWaiverTotal": 10,                           "uninsuredMotoristPDTotal": 0,                           "uninsuredMotoristBITotal": 100,                           "AUTO.instanceKey": "2006 Honda Odyssey",                           "DRIVER.FN": "Joan",                           "DRIVER.LN": "Smith"                         },                         {                           "ID": "5",                           "comprehensiveTotal": 500,                           "rentalTotal": 40,                           "medicalTotal": 10,                           "roadsideTotal": 10,                           "dedWaiverTotal": 10,                           "uninsuredMotoristPDTotal": 0,                           "uninsuredMotoristBITotal": 100,                           "AUTO.instanceKey": "2006 Honda Odyssey",                           "DRIVER.FN": "John",                           "DRIVER.LN": "Smith"                         },                         ...                       ]                     }                   ],                   "CalculatedPriceData": {                     "2006 Honda Odyssey": {                       "ID": "4",                       "comprehensiveTotal": 500,                       "rentalTotal": 40,                       "medicalTotal": 10,                       "roadsideTotal": 10,                       "dedWaiverTotal": 10,                       "uninsuredMotoristPDTotal": 0,                       "uninsuredMotoristBITotal": 100,                       "AUTO.instanceKey": "2006 Honda Odyssey",                       "DRIVER.FN": "Joan",                       "DRIVER.LN": "Smith"                     },                     "2015 Lexus LX250": {                       "ID": "0",                       "comprehensiveTotal": 500,                       "rentalTotal": 40,                       "medicalTotal": 10,                       "roadsideTotal": 10,                       "dedWaiverTotal": 10,                       "uninsuredMotoristPDTotal": 0,                       "uninsuredMotoristBITotal": 100,                       "AUTO.instanceKey": "2015 Lexus LX250",                       "DRIVER.FN": "Joan",                       "DRIVER.LN": "Smith"                     }                   },                   "displaySequence": -1                 }               ]             },             "insuredItems": {               "DRIVER": [{                   "isPrimary": false,                   "instanceKey": "Joan Smith",                   "LN": "Smith",                   "AGE": 20,                   "FN": "Joan",                   "GENDER": "Female",                   "FirstName": "Joan",                   "LastName": "Smith",                   "partyId": "a0q1I000001emNeQAI"                 },                 {                   "isPrimary": false,                   "instanceKey": "John Smith",                   "LN": "Smith",                   "AGE": 30,                   "FN": "John",                   "GENDER": "Male",                   "FirstName": "John",                   "LastName": "Smith",                   "partyId": "a0q1I000001emNfQAI"                 },               ],               "AUTO": [{                   "autoLicNum": "Lexus",                   "autoModel": "LX250",                   "autoYear": 2015,                   "instanceKey": "2015 Lexus LX250",                   "BodyClass": "Sedan/Saloon",                   "VehicleType": "PASSENGER CAR",                   "isPrimary": true                 },                 {                   "autoLicNum": "Honda",                   "autoModel": "Odyssey",                   "autoYear": 2006,                   "instanceKey": "2006 Honda Odyssey",                   "BodyClass": "Minivan",                   "VehicleType": "MULTIPURPOSE PASSENGER VEHICLE (MPV)",                   "isPrimary": true                 }               ]             },             "accountId": "0011I00000QknfjQAB",             "opportunityId": "0061I00000AV8gBQAT"           }`

[](https://help.salesforce.com/s?language=en_US)The JSON inside the `inputKey` includes several key/value pairs the service needs to create or update a quote.

| 
Key

 | 

Value

 |
| --- | --- |
| 

`opportunityId`

 | 

The generated opportunity Id.

 |
| 

`accountId`

 | 

The generated account Id.

 |
| 

`endDate`

 | 

Optional.

The date that the policy expires.

 |
| 

`effectiveDate`

 | 

The date that the policy goes into effect.

 |
| 

`productConfigurationDetail`

 | 

An array of records that follow the product JSON structure model.

A root quote line item will be created or modified for each product record in the array.

To learn about the structure and contents of a product, see the Product JSON Structure Model.

 |
| 

`additionalFields`

 | 

Optional.

The `additionalFields` key applies only to key/value pairs for root quotes, not quote line items. For quote line items, add additionalFields using the `productConfigurationDetail` JSON.

 |
| 

`insuredItems`

 | 

The key/value pairs of the insured items the service uses to create the quote line items for insured items.

 |

[](https://help.salesforce.com/s?language=en_US)Whether your quote includes a single instance of an insured item or multiple insured items, format the `insuredItems` node with an array of records.

[](https://help.salesforce.com/s?language=en_US)`"insuredItems": {   "DRIVER": [{     "isPrimary": false,     "instanceKey": null,     "additionalFields": {},     "productCode": "DRIVER",     "productId": "01t1I000002fuByQAI",     "FN": null,     "GENDER": null,     "LN": null,     "partyId": null   }],   "AUTO": [{     "isPrimary": true,     "instanceKey": null,     "additionalFields": {},     "productCode": "AUTO",     "productId": "01t1I000002fuBtQAI",     "autoBrakes": false,     "est_annual_mileage": "10001-20000",     "autoLicNum": null,     "autoModel": null,     "autoStyle": null,     "autoVIN": null,     "autoYear": ""   }] }`

[](https://help.salesforce.com/s?language=en_US)For a single instance of an insured item that's directly under the root product in the product hierarchy, you can use the format in this example. The `insuredItems` records here include the insured items and the values the user selected for each one. We support this input JSON but it's from an earlier release and we don't recommend it.

[](https://help.salesforce.com/s?language=en_US)`"insuredItems": {   "smallBusiness": {     "protectionClass": 3,     "yearBuilding": 2000,     "yearWiring": 2000,     "yearRoof": 2003,     "yearPlumbing": 2000,     "yearBusiness": 2002,     "businessParkingLot": "no",     "legalForm": "sole",     "busLocation": "standalone",     "busHours": 8,     "busEmployees": 24,     "bldgSprinker": "Y",     "bldgFrame": "frame",     "bldgAlarm": "none",     "ageWiring": 18,     "ageRoof": 15,     "agePlumbing": 18,     "ageBusiness": 16,     "ageBuilding": 18,     "SIC": "5451",     "SICCategory": "Food Stores"`

For new quotes, if `createOpportunity` is `true` and no `opportunityId` is provided, the service creates a new Opportunity record using the `OpportunityDetails` JSON node from the `inputKey`. Use the input format `OpportunityDetails:FieldName`. Here's an example of an `OpportunityDetails` node.

```
"OpportunityDetails": {
      "AccountId": "0015f00000DSFgqAAH",
      "Name": "Auto Quote: Rachel Adams (2022-01-03)",
      "StageName": "Qualification",
      "CloseDate": "2022-01-03"
    },
```

Note

preTransformBundle Alternative

Alternately, you can define a DataRaptor transform that maps the data that's passed into the input JSON into the form the service needs. This DataRaptor’s output JSON is the `userInputs` JSON defined in the product view’s API tab. Set the `preTransformBundle` option to the name of the DataRaptor to have the service use the DataRaptor.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the quote ID of the newly created quote. It also returns quote details if the `returnQuote` input is `true`, and the opportunity ID if `createOpportunity` is `true` and no `opportunityId` is provided.

[](https://help.salesforce.com/s?language=en_US)`{   "quoteDetail": {     "stmpbhins04__PrimaryRootItemId__c": "0QLR00000000e3NOAQ",     "stmpbhins04__TotalPremiumforTerm__c": 2000,     "stmpbhins04__MonthlyPremium__c": 166.66666666666666,     "stmpbhins04__StandardPremium__c": 2000,     "Id": "0Q0R00000000WplKAE",     "stmpbhins04__EndDate__c": "2022-05-04",     "stmpbhins04__EffectiveDate__c": "2021-05-05",     "stmpbhins04__Term__c": "Annual",     "Name": "Auto Root",     "OpportunityId": "006R0000002xk8QIAQ",     "Pricebook2Id": "01sR0000001GULqIAO"   },   "quoteId": "0Q0R00000000WplKAE",   "opportunityId": "006R0000002xk8QIAQ",   "error": "OK" }`

Did this article solve your issue?

Let us know so we can improve!

YesNo