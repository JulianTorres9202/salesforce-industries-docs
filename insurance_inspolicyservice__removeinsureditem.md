---
title: "InsPolicyService:removeInsuredItem"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__removeinsureditem.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsPolicyService:removeInsuredItem

InsPolicyService:removeInsuredItem[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsPolicyService:removeInsuredItem

Use this service to remove an insured item from an existing policy.

This service can be a part of modify policy OmniScripts and Integration Procedures. It works best with other services that form complete policy modification flows. For example, it can come after `getInsuredItems`, and before `createPolicyVersion`.

This service works with Salesforce Financial Services Cloud.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsPolicyService`

Method: `removeInsuredItem`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `insuredItemId` and the `effectiveDate`.
    
2.  Removes the insured item from the policy JSON.
    
3.  Recalculates the premium for the policy and returns the price difference and the modified policy JSON.
    
    If the policy JSON includes taxes and/or fees, the policy JSON includes and updates the `taxesAndFees`, `taxAmount`, `feeAmount`, `totalTaxForTermDiff`, and/or `totalFeeForTermDiff` fields (whichever of these are used).
    

[](https://help.salesforce.com/s?language=en_US)Note

All of the remote options used in the [InsProductService:getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.") service may also be used here.

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`aggByKey`

 | 

`PRODUCT.instanceKey`

The service sends this option to a calculation procedure that includes an aggregation step, so that the calculation procedure returns the correct amount.

For example, an auto insurance policy has multiple drivers attached to each insured vehicle. The insured vehicle has a separate instanceKey for each instance in the policy. The aggByKey takes the all the instance keys for the vehicles and creates an array of coverage premiums per instanceKey, and passes them to the calculation procedure so that premiums can be calculated correctly.

 |
| 

`calculateTaxesAndFees`

 | 

`true` or `false`

Calculates taxes and fees on the target product.

If set to `true`, recalculates the taxes and fees for the modified policy.

[](https://help.salesforce.com/s?language=en_US)If you use Salesforce FSC and you set this option to `true`, you must also specify `getDataDRBundleName` or `getDataCustomClassName` option.

 |
| 

`effectiveDate`

 | 

Required.

`“YYYY-MM-DD HH:MM:SS”` or `%OmniScriptDataElement%`

Defaults to today's date.

The date the removal of this insured item will take effect.

 |
| 

`getDataDRBundleName`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the Omnistudio Data Mapper this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataCustomClassName`.

 |
| 

`getDataCustomClassName`

 | 

[](https://help.salesforce.com/s?language=en_US)The name of the custom class this service uses to retrieve policy (asset) information.

[](https://help.salesforce.com/s?language=en_US)If you're using Salesforce FSC, you must specify either this option or `getDataDRBundleName`.

 |
| 

`includeInputKeys`

 | 

A string of comma-separated key/value pairs that the service passes into and out of the calculation procedure.

These key/value pairs are included in the output product object within the `CalculatedPriceData` object. They're there to help you parse the calculation results.

Only input keys used by the calculation procedure have a value in the results.

 |
| 

`insuredItemId`

 | 

Required.

`%theIdYouNeed%`

The Id of the insured item to be removed from the policy.

 |
| 

`policyId`

 | 

Required only if you use Salesforce FSC.

The ID of the InsurancePolicy.

 |
| 

`ratingDate`

 | 

Determines the rating procedure for repricing the policy. If not provided, pricing is done based on the effective date of the modified policy.

Note You can't pass a specific time for ratingField as the field type is Date. So, the rating date timestamp defaults to 12:00 am.





 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an output JSON without the removed item records and the recalculated premium information.

[](https://help.salesforce.com/s?language=en_US)For taxes and fees, in particular, the `totalTaxForTermDiff` and `totalFeeForTermDiff` fields are returned and only appear when calculating taxes and fees. They represent the difference between the prorated tax/fee of the target policy and the prorated tax/fee of the modified policy (similar to the `totalPremiumForTermDiff` field).

[](https://help.salesforce.com/s?language=en_US)The following keys and their values are included in the output:

[](https://help.salesforce.com/s?language=en_US)

-   `priceDiff`
    
-   `totalPremiumForTermDiff`
    

[](https://help.salesforce.com/s?language=en_US)`"totalSize": 0, "records": [{     "displaySequence": -1,     "Id": "02i1I000001jL2WQAU",     "productId": "01t1I000002fuBoQAI",     "accountId": "0011I00000QknfjQAB",     "policyNumber": "AUTOROOT-000154-2019-",     "productName": "Auto Root",     "EffectiveStart": "2018-08-15",     "EffectiveEnd": "2019-01-29",     "Price": 440,     "PricingFormula__c": "SUM(AutoPremium__autoPremium + rentalTotal + medicalTotal + roadsideTotal + dedWaiverTotal + uninsuredMotoristPDTotal + uninsuredMotoristBITotal)",     "ProductCode": "AUTOROOT",     "term": "Semi-Annual",     "TotalPremiumForTerm__c": 1661.74,     "CalculatedPriceData": {       "2015 Lexus LX250": {         "DRIVER.LN": null,         "DRIVER.FN": null,         "AUTO.instanceKey": "2015 Lexus LX250",         "uninsuredMotoristBITotal": 100,         "uninsuredMotoristPDTotal": 0,         "dedWaiverTotal": 10,         "roadsideTotal": 10,         "medicalTotal": 10,         "rentalTotal": 40,         "comprehensiveTotal": 500,         "ID": "0"       },       "2006 Honda Odyssey": {         ...       },       "2018 530 BMW": {         ...       },       "2016 Camry Toyota": {         ...       }     },     "priceDiff": -1380,     "totalPremiumForTermDiff": -904.32,     "attributeCategories": {       ...     }     "childProducts": {       ...     }`

Did this article solve your issue?

Let us know so we can improve!

YesNo