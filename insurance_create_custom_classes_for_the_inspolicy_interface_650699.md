---
title: "Create Custom Classes for the InsPolicy Interface"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_custom_classes_for_the_inspolicy_interface_650699.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Custom Classes for the InsPolicy Interface

Create Custom Classes for the InsPolicy Interface[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Custom Classes for the InsPolicy Interface

If the Omnistudio Data Mappers and custom classes included with the Insurance Industries Extension package don't work for your business needs, you can write your own custom classes to work with the InsPolicy interface to get or post data in the Salesforce FSC policy object.

[](https://help.salesforce.com/s?language=en_US)

## Using Your Custom Class

For our policy services to work with your custom class, the custom class must implement the `vlocity_ins.VlocityOpenInterface2` interface.

For your custom class to work with the `getDataCustomClassName` option, the class must do the following:

1.  Contain a method named `getData`, which the class uses to retrieve your data model.
    
    You can use the `Id` field in the options map to find the `Id` of the target policy.
    
2.  Inside the `getData` method, convert the data model into an InsPolicy object.
3.  Put the created InsPolicy object in the output map, using `InsPolicy` as the key.

```
public Boolean invokeMethod(String methodName,
                            Map<String, Object> inputs,
                            Map<String, Object> output,
                            Map<String, Object> options) {
    if (methodName == 'getData') {
        return getData(inputs, output, options);
    }
    return false;
}

private Boolean getData(Map<String, Object> inputs,
                        Map<String, Object> output,
                        Map<String, Object> options) {
    // Retrieve FSC data model and populate it in the output map
    InsPolicy myPolicy = getPolicy(options.get(‘Id’));
    output.put('InsPolicy', myPolicy.toMap());
    return true;
}
```

For the class to work with the `postDataCustomClassName` and `updateDataCustomClassName` options, the class must contain a method named `postData`. This method is used to convert the InsPolicy object into a concrete data model and insert or update the target records.

The InsPolicy object can be retrieved using the `InsPolicy` field in the inputs map as follows:

```
public Boolean invokeMethod(String methodName,
                            Map<String, Object> inputs,
                            Map<String, Object> output,
                            Map<String, Object> options) {
    if (methodName == 'postData') {
        return postData(inputs, output, options);
    }
    return false;
}

private Boolean postData(Map<String, Object> inputs,
                         Map<String, Object> output,
                         Map<String, Object> options) {
    // Convert InsPolicy to InsurancePolicy and insert the record
    InsurancePolicy myPolicy = convertToInsurancePolicy(inputs.get('InsPolicy'));
    insert myPolicy;
    return true;
}
```

[](https://help.salesforce.com/s?language=en_US)

## InsPolicy JSON Structure

The InsPolicy interface breaks down into JSON objects, starting with the root-level Policy JSON and then the child objects, as follows:

```
{
    // Fields
    "accountId": [String],
    "additionalInfo": [Map],
    "attributeSelectedValues": [Map],
    "createdDate": [Datetime],
    "currencyCode": [String],
    "currencySymbol": [String],
    "effectiveDate": [Datetime],
    "endDate": [Datetime],
    "financialAccountId": [String],
    "Id": [String],
    "monthlyPremium": [Decimal],
    "name": [String],
    "originalEffectiveDate": [Datetime],
    "originalEndDate": [Datetime],
    "originalVersionId": [String],
    "policyNumber": [String],
    "previousVersionId": [String],
    "productCode": [String],
    "productId": [String],
    "standardPremium": [Decimal],
    "status": [String],
    "term": [String],
    "totalAmount": [Decimal],
    "totalAmountForTerm": [Decimal],
    "totalFeeAmount": [Decimal],
    "totalFeeForTerm": [Decimal],
    "totalFeeForVersions": [Decimal],
    "totalPremiumForTerm": [Decimal],
    "totalPremiumForVersions": [Decimal],
    "totalSumInsured": [Decimal],
    "totalTaxAmount": [Decimal],
    "totalTaxFeeAmount": [Decimal],
    "totalTaxForTerm": [Decimal],
    "totalTaxForVersions": [Decimal],

    // Child Objects
    "coverages": [List<Coverage>],
    "insuredItems": [List<InsuredItem>],
    "insuredParties": [List<InsuredParty>],
    "pricingAdjustments": [List<PricingAdjustment>],
    "transactions": [List<Transaction>],
    "revenueSchedule": [List<Revenue>]
}

Coverage
{
    // Fields
    "additionalInfo": [Map],
    "attributeSelectedValues": [Map],
    "currencyCode": [String],
    "currencySymbol": [String],
    "effectiveDate": [Datetime],
    "endDate": [Datetime],
    "feeAmount": [Decimal],
    "Id": [String],
    "name": [String],
    "premium": [Decimal],
    "productChildItemId": [String],
    "productSpecCode": [String],
    "productSpecId": [String],
    "proratedFeeAmount": [Decimal],
    "proratedPremium": [Decimal],
    "proratedTaxAmount": [Decimal],
    "taxAmount": [Decimal],
    "totalAmount": [Decimal],
    "totalProratedAmount": [Decimal],
    "totalTaxFeeAmount": [Decimal],

    // Child Objects
    "pricingAdjustments": [List<PricingAdjustment>]
}

InsuredItem
{
    // Fields
    "additionalInfo": [Map],
    "attributeSelectedValues": [Map],
    "currencyCode": [String],
    "currencySymbol": [String],
    "feeAmount": [Decimal],
    "Id": [String],
    "instanceKey": [String],
    "lastModifiedDate": [Datetime],
    "name": [String],
    "premium": [Decimal],
    "productChildItemId": [String],
    "productSpecCode": [String],
    "productSpecId": [String],
    "proratedFeeAmount": [Decimal],
    "proratedPremium": [Decimal],
    "proratedTaxAmount": [Decimal],
    "taxAmount": [Decimal],
    "totalAmount": [Decimal],
    "totalProratedAmount": [Decimal],
    "totalSumInsured": [Decimal],
    "totalTaxFeeAmount": [Decimal],

    // Child Objects
    "childInsuredItems": [List<InsuredItem>],
    "coverages": [List<Coverage>]
    "insuredRels": [List<InsuredRelationship>],
    "pricingAdjustments": [List<PricingAdjustment>],
    "primaryInsuredParty": [InsuredParty]
}

InsuredParty
{
    // Fields
    "additionalInfo": [Map],
    "attributeSelectedValues": [Map],
    "currencyCode": [String],
    "currencySymbol": [String],
    "feeAmount": [Decimal],
    "Id": [String],
    "instanceKey": [String],
    "lastModifiedDate": [Datetime],
    "name": [String],
    "partyId": [String],
    "premium": [Decimal],
    "productChildItemId": [String],
    "productSpecCode": [String],
    "productSpecId": [String],
    "proratedFeeAmount": [Decimal],
    "proratedPremium": [Decimal],
    "proratedTaxAmount": [Decimal],
    "taxAmount": [Decimal],
    "totalAmount": [Decimal],
    "totalProratedAmount": [Decimal],
    "totalSumInsured": [Decimal],
    "totalTaxFeeAmount": [Decimal],

    // Child Objects
    "coverages": [List<Coverage>],
    "pricingAdjustments": [List<PricingAdjustment>]
}

InsuredRelationship
{
    // Fields
    "additionalInfo": [Map],
    "attributeSelectedValues": [Map],
    "childAttributeSelectedValues": [Map],
    "childId": [String],
    "childInstanceKey": [String],
    "childProductCode": [String],
    "parentId": [String],
    "parentInstanceKey": [String]
}

PricingAdjustment
{
    // Fields
    "adjustmentType": [String],
    "amount": [Decimal],
    "applicableItemType": [String],
    "Id": [String],
    "isRefundable": [Boolean],
    "priceListEntryId": [String],
    "priceListEntryName": [String],
    "transactionId": [String]
}

Transaction
{
    // Fields
    "additionalInfo": [Map],
    "amount": [Decimal],
    "feeAmount": [Decimal],
    "Id": [String],
    "name": [String],
    "postDate": [Datetime],
    "taxAmount": [Decimal],
    "totalAmount": [Decimal],
    "transactionDate": [Datetime],
    "transactionNumber": [String],
    "type": [String]
}

Revenue
{
    // Fields
    "amount": [Decimal],
    "Id": [String],
    "revenueDate": [Date],
    "toDelete": [Boolean]
    "totalEarnedRevenue": [Decimal],
    "totalUnearnedRevenue": [Decimal]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Sample InsPolicy JSON

Below is an example InsPolicy JSON taken from an auto policy. A couple of things:

-   While it is not shown in this JSON, an `insuredParties` object can have child coverages.
    
-   You can use the `additionalInfo` map to retrieve and insert custom fields not listed in the JSON payload.
    
    When you write a `get` Data Mapper or custom class, you can put custom fields into the `additionalInfo` map.
    
    When you a write a `post` or `update` Data Mapper or custom class, you can retrieve custom fields via the `additionalInfo` map.
    

```
{
  "transactions": [
    {
      "type": "Sold Policy",
      "transactionNumber": null,
      "transactionDate": "2019-12-01T08:00:00.000Z",
      "totalAmount": 1091.6,
      "taxAmount": 251.6,
      "postDate": "2019-12-01T08:00:00.000Z",
      "name": "Sold Policy",
      "Id": "a5pB00000004Q8UIAU",
      "feeAmount": 100,
      "amount": 740,
      "additionalInfo": null
    }
  ],
  "totalTaxForVersions": 0,
  "totalTaxForTerm": 251.6,
  "totalTaxFeeAmount": 351.6,
  "totalTaxAmount": 251.6,
  "totalSumInsured": null,
  "totalPremiumForVersions": 0,
  "totalPremiumForTerm": 740,
  "totalFeeForVersions": 0,
  "totalFeeForTerm": 100,
  "totalFeeAmount": 100,
  "totalAmountForTerm": 1091.6,
  "totalAmount": 1091.6,
  "term": "Semi-Annual",
  "status": "Initial",
  "standardPremium": 740,
  "revenueSchedule": [
    {
      "totalUnearnedRevenue": 614.64,
      "totalEarnedRevenue": 125.36,
      "toDelete": null,
      "revenueDate": "2019-12-31",
      "insTransaction": null,
      "Id": "a5oB00000004IdRIAU",
      "amount": 125.36
    },
    {
      "totalUnearnedRevenue": 489.28,
      "totalEarnedRevenue": 250.72,
      "toDelete": null,
      "revenueDate": "2020-01-31",
      "insTransaction": null,
      "Id": "a5oB00000004IdSIAU",
      "amount": 125.36
    },
    {
      "totalUnearnedRevenue": 372.01,
      "totalEarnedRevenue": 367.99,
      "toDelete": null,
      "revenueDate": "2020-02-29",
      "insTransaction": null,
      "Id": "a5oB00000004IdTIAU",
      "amount": 117.27
    },
    {
      "totalUnearnedRevenue": 246.65,
      "totalEarnedRevenue": 493.35,
      "toDelete": null,
      "revenueDate": "2020-03-31",
      "insTransaction": null,
      "Id": "a5oB00000004IdUIAU",
      "amount": 125.36
    },
    {
      "totalUnearnedRevenue": 125.34,
      "totalEarnedRevenue": 614.66,
      "toDelete": null,
      "revenueDate": "2020-04-30",
      "insTransaction": null,
      "Id": "a5oB00000004IdVIAU",
      "amount": 121.31
    },
    {
      "totalUnearnedRevenue": 0,
      "totalEarnedRevenue": 740,
      "toDelete": null,
      "revenueDate": "2020-05-31",
      "insTransaction": null,
      "Id": "a5oB00000004IdWIAU",
      "amount": 125.34
    }
  ],
  "productId": "01tB0000000VP2TIAW",
  "productCode": "AUTOROOT",
  "pricingAdjustments": [
    {
      "transactionId": null,
      "priceListEntryName": "Auto Root Test Fee",
      "priceListEntryId": "a2tB0000000LyJPIA0",
      "isRefundable": false,
      "Id": "a5nB00000004j7vIAA",
      "applicableItemType": null,
      "amount": 20,
      "adjustmentType": "Fee"
    },
    {
      "transactionId": null,
      "priceListEntryName": "Auto Root Test Tax",
      "priceListEntryId": "a2tB0000000LyJKIA0",
      "isRefundable": true,
      "Id": "a5nB00000004j7wIAA",
      "applicableItemType": null,
      "amount": 125.8,
      "adjustmentType": "Tax"
    }
  ],
  "previousVersionId": null,
  "policyNumber": "5df21f6f-62d6-2c63-6a1a-c67e2bdd6fec",
  "originalVersionId": "0YTB0000000TRFcOAO",
  "originalEndDate": null,
  "originalEffectiveDate": null,
  "name": "Auto Root",
  "monthlyPremium": 123.33333333333333,
  "insuredParties": [
    {
      "totalTaxFeeAmount": 0,
      "totalSumInsured": null,
      "totalProratedAmount": 0,
      "totalAmount": 0,
      "taxAmount": null,
      "proratedTaxAmount": null,
      "proratedPremium": null,
      "proratedFeeAmount": null,
      "productSpecId": "01tB0000000VP2PIAW",
      "productSpecCode": "DRIVER",
      "productChildItemId": null,
      "pricingAdjustments": null,
      "premium": null,
      "partyId": null,
      "name": "Joan Smith",
      "lastModifiedDate": "2019-12-18T03:08:23.000Z",
      "instanceKey": "Joan Smith",
      "Id": "0aoB0000000TdKwIAK",
      "feeAmount": null,
      "currencySymbol": null,
      "currencyCode": null,
      "coverages": null,
      "attributeSelectedValues": {
        "AGE": 20,
        "FN": "Joan",
        "GENDER": "Female",
        "LN": "Smith",
        "isPrimary": false
      },
      "additionalInfo": {}
    },
    {
      "totalTaxFeeAmount": 0,
      "totalSumInsured": null,
      "totalProratedAmount": 0,
      "totalAmount": 0,
      "taxAmount": null,
      "proratedTaxAmount": null,
      "proratedPremium": null,
      "proratedFeeAmount": null,
      "productSpecId": "01tB0000000VP2PIAW",
      "productSpecCode": "DRIVER",
      "productChildItemId": null,
      "pricingAdjustments": null,
      "premium": null,
      "partyId": null,
      "name": "John Smith",
      "lastModifiedDate": "2019-12-18T03:08:23.000Z",
      "instanceKey": "John Smith",
      "Id": "0aoB0000000TdKxIAK",
      "feeAmount": null,
      "currencySymbol": null,
      "currencyCode": null,
      "coverages": null,
      "attributeSelectedValues": {
        "AGE": 30,
        "FN": "John",
        "GENDER": "Male",
        "LN": "Smith",
        "isPrimary": false
      },
      "additionalInfo": {}
    }
  ],
  "insuredItems": [
    {
      "totalTaxFeeAmount": 102.9,
      "totalSumInsured": null,
      "totalProratedAmount": 0,
      "totalAmount": 472.9,
      "taxAmount": 62.9,
      "proratedTaxAmount": null,
      "proratedPremium": null,
      "proratedFeeAmount": null,
      "productSpecId": "01tB0000000VP2OIAW",
      "productSpecCode": "AUTO",
      "productChildItemId": "a32B00000009ktaIAA",
      "primaryInsuredParty": {
        "totalTaxFeeAmount": null,
        "totalSumInsured": null,
        "totalProratedAmount": null,
        "totalAmount": null,
        "taxAmount": null,
        "proratedTaxAmount": null,
        "proratedPremium": null,
        "proratedFeeAmount": null,
        "productSpecId": null,
        "productSpecCode": null,
        "productChildItemId": null,
        "pricingAdjustments": null,
        "premium": null,
        "partyId": null,
        "name": null,
        "lastModifiedDate": null,
        "instanceKey": null,
        "Id": "0aoB0000000TdKwIAK",
        "feeAmount": null,
        "currencySymbol": null,
        "currencyCode": null,
        "coverages": null,
        "attributeSelectedValues": {},
        "additionalInfo": {}
      },
      "pricingAdjustments": [
        {
          "transactionId": null,
          "priceListEntryName": "Auto Test Tax",
          "priceListEntryId": "a2tB0000000LyJAIA0",
          "isRefundable": true,
          "Id": "a5nB00000004j7xIAA",
          "applicableItemType": "Insurance Policy Asset",
          "amount": 62.9,
          "adjustmentType": "Tax"
        },
        {
          "transactionId": null,
          "priceListEntryName": "Auto Test Fee",
          "priceListEntryId": "a2tB0000000LyJFIA0",
          "isRefundable": false,
          "Id": "a5nB00000004j7yIAA",
          "applicableItemType": "Insurance Policy Asset",
          "amount": 20,
          "adjustmentType": "Fee"
        }
      ],
      "premium": 370,
      "name": "2015 Lexus LX250",
      "lastModifiedDate": "2019-12-18T03:08:24.000Z",
      "insuredRels": [
        {
          "parentInstanceKey": "2015 Lexus LX250",
          "parentId": null,
          "childProductCode": "DRIVER",
          "childInstanceKey": "Joan Smith",
          "childId": "0aoB0000000TdKwIAK",
          "childAttributeSelectedValues": {
            "AGE": 20,
            "FN": "Joan",
            "GENDER": "Female",
            "LN": "Smith",
            "isPrimary": false
          },
          "attributeSelectedValues": {
            "AGE": 20,
            "LN": "Smith",
            "GENDER": "Female",
            "FN": "Joan"
          },
          "additionalInfo": {}
        }
      ],
      "instanceKey": "2015 Lexus LX250",
      "Id": "0YWB0000000TTiiOAG",
      "feeAmount": 40,
      "currencySymbol": null,
      "currencyCode": null,
      "coverages": [
        {
          "totalTaxFeeAmount": 0,
          "totalProratedAmount": 0,
          "totalAmount": 1000,
          "taxAmount": null,
          "proratedTaxAmount": null,
          "proratedPremium": null,
          "proratedFeeAmount": null,
          "productSpecId": "01tB0000000VP2KIAW",
          "productSpecCode": "LIABILITY_COVERAGE",
          "productChildItemId": "a32B00000009ktfIAA",
          "pricingAdjustments": null,
          "premium": 1000,
          "name": "Liability (BI/PD)",
          "Id": "0cYB0000000L6idMAC",
          "feeAmount": null,
          "endDate": null,
          "effectiveDate": null,
          "currencySymbol": null,
          "currencyCode": null,
          "attributeSelectedValues": {
            "LIABILITY": "$100k/$300k/$100k"
          },
          "additionalInfo": {}
        },
        {
          "totalTaxFeeAmount": 0,
          "totalProratedAmount": 0,
          "totalAmount": 500,
          "taxAmount": null,
          "proratedTaxAmount": null,
          "proratedPremium": null,
          "proratedFeeAmount": null,
          "productSpecId": "01tB0000000VP2JIAW",
          "productSpecCode": "COMP_COVERAGE",
          "productChildItemId": "a32B00000009ktcIAA",
          "pricingAdjustments": null,
          "premium": 500,
          "name": "Comprehensive",
          "Id": "0cYB0000000L6ieMAC",
          "feeAmount": null,
          "endDate": null,
          "effectiveDate": null,
          "currencySymbol": null,
          "currencyCode": null,
          "attributeSelectedValues": {
            "COMPREHENSIVE": "500"
          },
          "additionalInfo": {}
        },
        {
          "totalTaxFeeAmount": 0,
          "totalProratedAmount": 0,
          "totalAmount": 0,
          "taxAmount": null,
          "proratedTaxAmount": null,
          "proratedPremium": null,
          "proratedFeeAmount": null,
          "productSpecId": "01tB0000000VP2HIAW",
          "productSpecCode": "COL_WAIVER",
          "productChildItemId": "a32B00000009ktdIAA",
          "pricingAdjustments": null,
          "premium": 0,
          "name": "Collision Deductible Waiver",
          "Id": "0cYB0000000L6ifMAC",
          "feeAmount": null,
          "endDate": null,
          "effectiveDate": null,
          "currencySymbol": null,
          "currencyCode": null,
          "attributeSelectedValues": {
            "DED_WAIVER": "No coverage"
          },
          "additionalInfo": {}
        },
        {
          "totalTaxFeeAmount": 20,
          "totalProratedAmount": 0,
          "totalAmount": 520,
          "taxAmount": null,
          "proratedTaxAmount": null,
          "proratedPremium": null,
          "proratedFeeAmount": null,
          "productSpecId": "01tB0000000VP2IIAW",
          "productSpecCode": "COL_COVERAGE",
          "productChildItemId": "a32B00000009ktbIAA",
          "pricingAdjustments": [
            {
              "transactionId": null,
              "priceListEntryName": "Collision Test Fee",
              "priceListEntryId": "a2tB0000000LyJUIA0",
              "isRefundable": false,
              "Id": "a5nB00000004j81IAA",
              "applicableItemType": "Insurance Policy Coverage",
              "amount": 20,
              "adjustmentType": "Fee"
            }
          ],
          "premium": 500,
          "name": "Collision",
          "Id": "0cYB0000000L6igMAC",
          "feeAmount": 20,
          "endDate": null,
          "effectiveDate": null,
          "currencySymbol": null,
          "currencyCode": null,
          "attributeSelectedValues": {
            "COLLISION": "500"
          },
          "additionalInfo": {}
        }
      ],
      "childInsuredItems": null,
      "attributeSelectedValues": {
        "BodyClass": "Sedan/Saloon",
        "VehicleType": "PASSENGER CAR",
        "autoLicNum": "Lexus",
        "isPrimary": true,
        "autoYear": 2015,
        "autoModel": "LX250",
        "est_annual_mileage": "1-10000"
      },
      "additionalInfo": {}
    },
    {
      "totalTaxFeeAmount": 102.9,
      "totalSumInsured": null,
      "totalProratedAmount": 0,
      "totalAmount": 472.9,
      "taxAmount": 62.9,
      "proratedTaxAmount": null,
      "proratedPremium": null,
      "proratedFeeAmount": null,
      "productSpecId": "01tB0000000VP2OIAW",
      "productSpecCode": "AUTO",
      "productChildItemId": "a32B00000009ktaIAA",
      "primaryInsuredParty": {
        "totalTaxFeeAmount": null,
        "totalSumInsured": null,
        "totalProratedAmount": null,
        "totalAmount": null,
        "taxAmount": null,
        "proratedTaxAmount": null,
        "proratedPremium": null,
        "proratedFeeAmount": null,
        "productSpecId": null,
        "productSpecCode": null,
        "productChildItemId": null,
        "pricingAdjustments": null,
        "premium": null,
        "partyId": null,
        "name": null,
        "lastModifiedDate": null,
        "instanceKey": null,
        "Id": "0aoB0000000TdKxIAK",
        "feeAmount": null,
        "currencySymbol": null,
        "currencyCode": null,
        "coverages": null,
        "attributeSelectedValues": {},
        "additionalInfo": {}
      },
      "pricingAdjustments": [
        {
          "transactionId": null,
          "priceListEntryName": "Auto Test Tax",
          "priceListEntryId": "a2tB0000000LyJAIA0",
          "isRefundable": true,
          "Id": "a5nB00000004j7zIAA",
          "applicableItemType": "Insurance Policy Asset",
          "amount": 62.9,
          "adjustmentType": "Tax"
        },
        {
          "transactionId": null,
          "priceListEntryName": "Auto Test Fee",
          "priceListEntryId": "a2tB0000000LyJFIA0",
          "isRefundable": false,
          "Id": "a5nB00000004j80IAA",
          "applicableItemType": "Insurance Policy Asset",
          "amount": 20,
          "adjustmentType": "Fee"
        }
      ],
      "premium": 370,
      "name": "2006 Honda Odyssey",
      "lastModifiedDate": "2019-12-18T03:08:24.000Z",
      "insuredRels": [
        {
          "parentInstanceKey": "2006 Honda Odyssey",
          "parentId": null,
          "childProductCode": "DRIVER",
          "childInstanceKey": "John Smith",
          "childId": "0aoB0000000TdKxIAK",
          "childAttributeSelectedValues": {
            "AGE": 30,
            "FN": "John",
            "GENDER": "Male",
            "LN": "Smith",
            "isPrimary": false
          },
          "attributeSelectedValues": {
            "AGE": 30,
            "LN": "Smith",
            "GENDER": "Male",
            "FN": "John"
          },
          "additionalInfo": {}
        }
      ],
      "instanceKey": "2006 Honda Odyssey",
      "Id": "0YWB0000000TTijOAG",
      "feeAmount": 40,
      "currencySymbol": null,
      "currencyCode": null,
      "coverages": [
        {
          "totalTaxFeeAmount": 0,
          "totalProratedAmount": 0,
          "totalAmount": 1000,
          "taxAmount": null,
          "proratedTaxAmount": null,
          "proratedPremium": null,
          "proratedFeeAmount": null,
          "productSpecId": "01tB0000000VP2KIAW",
          "productSpecCode": "LIABILITY_COVERAGE",
          "productChildItemId": "a32B00000009ktfIAA",
          "pricingAdjustments": null,
          "premium": 1000,
          "name": "Liability (BI/PD)",
          "Id": "0cYB0000000L6ihMAC",
          "feeAmount": null,
          "endDate": null,
          "effectiveDate": null,
          "currencySymbol": null,
          "currencyCode": null,
          "attributeSelectedValues": {
            "LIABILITY": "$100k/$300k/$100k"
          },
          "additionalInfo": {}
        },
        {
          "totalTaxFeeAmount": 0,
          "totalProratedAmount": 0,
          "totalAmount": 500,
          "taxAmount": null,
          "proratedTaxAmount": null,
          "proratedPremium": null,
          "proratedFeeAmount": null,
          "productSpecId": "01tB0000000VP2JIAW",
          "productSpecCode": "COMP_COVERAGE",
          "productChildItemId": "a32B00000009ktcIAA",
          "pricingAdjustments": null,
          "premium": 500,
          "name": "Comprehensive",
          "Id": "0cYB0000000L6iiMAC",
          "feeAmount": null,
          "endDate": null,
          "effectiveDate": null,
          "currencySymbol": null,
          "currencyCode": null,
          "attributeSelectedValues": {
            "COMPREHENSIVE": "500"
          },
          "additionalInfo": {}
        },
        {
          "totalTaxFeeAmount": 0,
          "totalProratedAmount": 0,
          "totalAmount": 0,
          "taxAmount": null,
          "proratedTaxAmount": null,
          "proratedPremium": null,
          "proratedFeeAmount": null,
          "productSpecId": "01tB0000000VP2HIAW",
          "productSpecCode": "COL_WAIVER",
          "productChildItemId": "a32B00000009ktdIAA",
          "pricingAdjustments": null,
          "premium": 0,
          "name": "Collision Deductible Waiver",
          "Id": "0cYB0000000L6ijMAC",
          "feeAmount": null,
          "endDate": null,
          "effectiveDate": null,
          "currencySymbol": null,
          "currencyCode": null,
          "attributeSelectedValues": {
            "DED_WAIVER": "No coverage"
          },
          "additionalInfo": {}
        },
        {
          "totalTaxFeeAmount": 20,
          "totalProratedAmount": 0,
          "totalAmount": 520,
          "taxAmount": null,
          "proratedTaxAmount": null,
          "proratedPremium": null,
          "proratedFeeAmount": null,
          "productSpecId": "01tB0000000VP2IIAW",
          "productSpecCode": "COL_COVERAGE",
          "productChildItemId": "a32B00000009ktbIAA",
          "pricingAdjustments": [
            {
              "transactionId": null,
              "priceListEntryName": "Collision Test Fee",
              "priceListEntryId": "a2tB0000000LyJUIA0",
              "isRefundable": false,
              "Id": "a5nB00000004j82IAA",
              "applicableItemType": "Insurance Policy Coverage",
              "amount": 20,
              "adjustmentType": "Fee"
            }
          ],
          "premium": 500,
          "name": "Collision",
          "Id": "0cYB0000000L6ikMAC",
          "feeAmount": 20,
          "endDate": null,
          "effectiveDate": null,
          "currencySymbol": null,
          "currencyCode": null,
          "attributeSelectedValues": {
            "COLLISION": "500"
          },
          "additionalInfo": {}
        }
      ],
      "childInsuredItems": null,
      "attributeSelectedValues": {
        "BodyClass": "Minivan",
        "VehicleType": "MULTIPURPOSE PASSENGER VEHICLE (MPV)",
        "autoLicNum": "Honda",
        "isPrimary": true,
        "autoYear": 2006,
        "autoModel": "Odyssey",
        "est_annual_mileage": "1-10000"
      },
      "additionalInfo": {}
    }
  ],
  "Id": "0YTB0000000TRFcOAO",
  "financialAccountId": null,
  "endDate": "2020-05-31T07:00:00.000Z",
  "effectiveDate": "2019-12-01T08:00:00.000Z",
  "currencySymbol": null,
  "currencyCode": null,
  "createdDate": "2019-12-18T03:08:19.000Z",
  "coverages": [
    {
      "totalTaxFeeAmount": 0,
      "totalProratedAmount": 0,
      "totalAmount": 0,
      "taxAmount": null,
      "proratedTaxAmount": null,
      "proratedPremium": null,
      "proratedFeeAmount": null,
      "productSpecId": "01tB0000000VP2LIAW",
      "productSpecCode": "UNINSURED_COVERAGE",
      "productChildItemId": "a32B00000009ktXIAQ",
      "pricingAdjustments": null,
      "premium": 0,
      "name": "Uninsured/Underinsured Motorist BI",
      "Id": "0cYB0000000L6icMAC",
      "feeAmount": null,
      "endDate": "2020-06-01T06:59:59.000Z",
      "effectiveDate": "2019-12-01T08:00:00.000Z",
      "currencySymbol": null,
      "currencyCode": null,
      "attributeSelectedValues": {
        "UNINSURED": "$100k/$300k"
      },
      "additionalInfo": {}
    }
  ],
  "attributeSelectedValues": {},
  "additionalInfo": {},
  "accountId": "001B0000015bAwCIAU"
}
```

## See Also

[The InsPolicy FSC-Vlocity Mapping Interface](https://help.salesforce.com/s/articleView?id=ind.insurance_the_inspolicy_fsc_vlocity_mapping_interface_650389.htm&language=en_US&type=5 "The InsPolicy interface is a generic service interface that lets Vlocity policy services work with any policy data model, including the Salesforce FSC Insurance Policy data model.")

Did this article solve your issue?

Let us know so we can improve!

YesNo