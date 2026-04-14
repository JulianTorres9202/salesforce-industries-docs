---
title: "Multiple Rating Procedures per Product or Multiple Specs at Any Level for repriceProduct"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_multi_rating_procs_per_product_or_multi_specs_at_any_level.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Multiple Rating Procedures per Product or Multiple Specs at Any Level for repriceProduct

Multiple Rating Procedures per Product or Multiple Specs at Any Level for repriceProduct[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Multiple Rating Procedures per Product or Multiple Specs at Any Level for repriceProduct

Format `InsProductService:repriceProduct userInputs` for products that use multiple rating procedures in the product hierarchy or multiple child specs in any level of the hierarchy.

For example, a commercial product that uses unique rating procedures for Location, Building, and Infrastructure has multiple rating procedures in the product hierarchy.

Note

Products configured before Winter '23 release 240.22 can have multiple child specs in a given level of the hierarchy, no grandchild specs, and only one rating procedure at the root level. For these products, use the same `userInputs` format as you did in earlier releases. See [One Rating Procedure per Product for repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_one_rating_procedure_per_product.htm&language=en_US&type=5 "Format InsProductService:repriceProduct userInputs for products that use a single rating procedure per root product.").

A Home Insurance product with more than one piece of art and jewelry insured at a given property has multiple child specs in a single level of the product hierarchy.

Note

To rate products that use a single rating procedure per root product, you format input JSON differently. To prevent errors, run the service with only one type of userInputs format at a time. See [One Rating Procedure per Product for repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_repriceproduct_one_rating_procedure_per_product.htm&language=en_US&type=5 "Format InsProductService:repriceProduct userInputs for products that use a single rating procedure per root product.").

`InsProductService: repriceProduct` looks for a `userInputs` key in the input JSON. Products with ratings at the insured item level have one `userInputs` for each insured item instance, and one separate `userInputs` for the root instance and its coverages.

In the unique `userInputs` with insured item-level details:

-   For the insured items related directly to the root product, set `parentInstanceKey` to the product code of the root product.
    
-   For lower-level insured items, set `parentInstanceKey` to the `instanceKey` value of the parent. For example, at a Location called 1 Market Street, there's a Building called Building 100. The `parentInstanceKey` value in `userInputs` for Building 100 is 1 Market Street (`'parentInstanceKey' => '1 Market Street'`).
    
-   Set `instanceKey` to the `instanceKey` value of the insured item. For example, the `instanceKey` value in userInputs for "Building 100" is "Building 100" ('BUILDING.instanceKey' => 'Building 100').
    
-   Include the insured item instance's coverages.
    

In the separate single `userInputs` with root-level details:

-   Set `instanceKey` to the root product's product code.
    
-   Include root-level coverages.
    

For example, a Traveler Insurance product (TRAVEL\_ROOT) covers a TRAVELER (Insured Party), LUGGAGE (Insured Item), and VALUABLES (Insured Item). The root product has accident coverage (TRAVEL\_ACCIDENT), and the child products each have their own coverage (TRAVELER\_HEALTH, LUGGAGE\_LOSS and VALUABLES\_THEFT).

| Sample Input JSON |
| --- |
| 
```json
{
'TRAVEL_ROOT.instanceKey' => 'TRAVEL_ROOT',
'parentInstanceKey' => '',
'TRAVEL_ACCIDENT.FaceAmount' => 3000
}
```

 | 

`userInputs` for the root product specify the `instanceKey` TRAVEL\_ROOT and the root-level TRAVEL\_ACCIDENT coverage.

 |
| 

```json
{
'TRAVELER.persName' => 'John Smith',
'TRAVELER.persIncome' => 100000,
'TRAVELER.instanceKey' => John Smith',
'parentInstanceKey' => 'TRAVEL_ROOT',
'TRAVELER_HEALTH.CoInsurance' => 0.2
},
```

 | 

`userInputs` for the child instance 'John Smith' specify the `instanceKey` 'John Smith', the `parentInstanceKey` TRAVEL\_ROOT, and the child-level TRAVELER\_HEALTH coverage.

 |
| 

```json
{
'LUGGAGE.valuableName' => 'Suitcase',
'LUGGAGE.valuableValue' => 400,
'LUGGAGE_LOSS.ded_limit_Limit' => 400,
'LUGGAGE.instanceKey' => 'Suitcase',
'parentInstanceKey' => 'John Smith'
},
```

 | 

`userInputs` for the child instance 'Suitcase' specify the `instanceKey` 'Suitcase', the `parentInstanceKey` 'John Smith', and the child-level LUGGAGE\_LOSS coverage.

 |
| 

```json
{
'VALUABLES.valuableName' => 'iPad',
'VALUABLES.valuableValue' => 600,
'VALUABLES_THEFT.ded_limit_Limit' => 400,
'VALUABLES.instanceKey' => 'iPad',
'parentInstanceKey' => 'John Smith'
}
```

 | 

`userInputs` for child instance 'iPad' specify the `instanceKey` 'iPad', the `parentInstanceKey` 'John Smith', and the child-level VALUABLES\_THEFT coverage.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo