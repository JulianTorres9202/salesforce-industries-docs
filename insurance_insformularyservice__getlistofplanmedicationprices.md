---
title: "InsFormularyService:getListOfPlanMedicationPrices"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insformularyservice__getlistofplanmedicationprices.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsFormularyService:getListOfPlanMedicationPrices

InsFormularyService:getListOfPlanMedicationPrices[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsFormularyService:getListOfPlanMedicationPrices

Use this service to get a list of prices for covered drugs within a provider network, including copay calculation.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsFormularyService`

Method: `getListOfPlanMedicationPrices`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Uses `ProviderNetworkFormularyDrugPrice_c` and `getListOfPlanMedicationPrices` for the list of negotiated drug prices between the provider network and pharmacy.
    
2.  Calculates the drug's copay amounts based on the drug's formulary tier, which can be either a fixed copay amount or a percentage of the negotiated amount between the provider network and the pharmacy, using `FormularyDrugId__r` , `FormularyTierId__r` , `CoPayPercent__c`, or `CoPayAmount__c`.
    
3.  Output `result` provides list with drug's calculated copay amount, together with network and pharmacy names.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`formularyDrugIds`

 | 

Required.

One or more IDs based on the result of the FormularyServiceHandler's `getListOfCoveredDrugs` function.

 |
| 

`networkIds`

 | 

Optional.

Network Ids to filter the result, to show only the amounts from the selected networks.

 |
| 

`effectiveDate`

 | 

Optional.

 |
| 

`longitude`

 | 

Optional.

Must be used with `latitude`.

Sorts results according to distance closest to point selected.

Works only if the Pharmacy’s (Account) `BillingLongitude` and `BillingLatitude` are in use.

 |
| 

`latitude`

 | 

Optional.

Must be used with `longitude`.

Sorts results according to distance closest to point selected.

Works only if the Pharmacy’s (Account) `BillingLongitude` and `BillingLatitude` are in use.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo