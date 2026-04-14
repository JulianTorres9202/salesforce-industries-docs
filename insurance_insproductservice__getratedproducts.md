---
title: "InsProductService:getRatedProducts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductService:getRatedProducts

InsProductService:getRatedProducts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductService:getRatedProducts

Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Class: `InsProductService`

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Method: `getRatedProducts`

[](https://help.salesforce.com/s?language=en_US)

To use this service, pass it the set of inputs the rating procedure needs to price products. The service returns a filtered array of products and a result JSON from the rating procedure.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service searches Salesforce to retrieve a set of active products that fall within the effective start and end dates. See effectiveDate below for more information.
    
    As part of the query, the services uses the criteria passed in the filter option to get an initial set of products. The data pulled from Salesforce includes the product’s eligibility rules and rating procedure, insured item specs, insured party specs, coverage specs, rating fact specs, and all its attributes.
    
2.  Evaluates each product in the initial set based on its eligibility rules, further reducing the product set.
    
3.  Searches the Input JSON for the `userInputs` key and retrieves the key's value. `userInputs` is the set of input data the rating procedure uses to get the price of the product. The service evaluates this object based on the product rating input mappings to create the input JSON needed by the rating procedure.
    
    You format `userInputs` differently depending on the product definition and the rating configuration. To prevent errors, filter for products that all use the same type of `userInputs` format.
    
4.  Rates each product in the set created in step 2. It calls the product’s associated rating procedure with the input JSON from step 3.
    
5.  Returns an array of product objects with each product's total price and the total insured sum.
    
    Each returned product object also includes the output JSON from the rating procedure as the value of `CalculatedPriceData`. The service also sets `price` and `totalSumInsured` if the formulas are set on the product.
    
    Keep in mind that:
    
    -   If a single attribute is set up with both a Set Value attribute rule and a Set Default Value attribute rule, `getRatedProducts` applies only the Set Default Value attribute rule.
        
    -   As a best practice, when you set up attribute rule expressions, don't reference attribute values in lower-level structures.
        

## Remote Options

Rating Options
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

When `aggByKey` is set, its value is included in the `aggregationResult` of the calculation procedure, if `aggregationResult` isn’t empty. (The `aggregationResult` is usually populated when a calculation procedure has aggregation steps configured).

For example, a car insurance policy that has multiple drivers insured for multiple cars requires `aggByKey` be passed to the calculation procedure.

 |
| 

`alwaysCreateInstance`

 | 

Set this option to `true` for products with multiple child specs in a given level of the hierarchy, no grandchild specs, and only one rating procedure at the root level.

Omit this option for products that don't meet all these criteria.

To format `userInputs` for this type of product, see [One Rating Procedure per Product for getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_one_rating_procedure_per_product.htm&language=en_US&type=5 "Format InsProductService:getRatedProducts userInputs for products that use a single rating procedure per root product.").

 |
| 

`includeInputKeys`

 | 

A string of comma-separated input keys to include in the output product object, within the `CalculatedPriceData` object.

Only input keys used by the calculation procedure have a value in the results.

 |
| 

`rateType`

 | 

`Age` or `Composite`

Use this option for small group rating.

 |
| 

`searchText`

 | 

PartOfAProductName

If this option is used, the service gets only products with names that contain the value you provided.

 |
| 

`sortBy`

 | 

productField1, productField2.

Sorts the products the service gets in the order you specify.

You can use `DESC` with this option to sort products in descending order. You can specify the first item to descend from. If you don't specify a place to start, `DESC` defaults to alphabetical order.

If you don't specify a value for this option, the service sorts products returned by name in ascending alphabetical order.

 |

Filter Options
| 
Option

 | 

Description

 |
| --- | --- |
| 

`attributeFilters`

 | 

A map of `attributeCode` and values

Returns only products that satisfy the attribute values provided in the filter.

 |
| 

`effectiveDate`

 | 

`“YYYY-MM-DD HH:MM:SS”` or `%OmniScriptDataElement%`

Defaults to today's date.

Service pulls products with an `effectiveDate` between `EffectiveDate__c` and `EndDate__c` and `IsActive`.

The service also uses the `effectiveDate` to select the correct version of the calculation procedure used to rate the product.

 |
| 

`filters`

 | 

`Product2FieldName:Value`

`Product2FieldName:%ElementName%`

Use the API name with a colon followed by either a value or a variable. For example, in an OmniScript, a variable can be a name of an element, such as an input picklist.

Separate multiple filter parameters with commas:

`ProductCode:Value,ProductCode:%ElementName%`

Filters can include any field on the `Product2` object.

 |
| 

`includeFilterAttrValues`

 | 

`true` or `false`

Defaults to `false`.

In the output JSON, along with the array of products, this adds the `filterAttrValues` object. This object contains the root product attributes marked filterable, with the possible list of values. This list is used by some UI templates to filter large sets of products.

Child product attributes aren’t included.

 |
| 

`whereClause`

 | 

Enter any valid Salesforce SOQL statement as the value for this option.

Use this when you need this service to look at multi-picklist fields when searching for products.

For example, the statement `vlocity_ins_marketsegment_c includes ('Small Group')` picks up products that have Market Segments 'Small Group' and either more or no more market segments in the multi-select picklist.

Important

Remove any reference to the fields in the `whereClause` from your filter key.

For example, if you have `vlocity_ins_marketsegment_c:Small Group` in the filter and a `whereClause` containing a reference to the same field, they’ll collide and conflict, producing unpredictable results.







 |

Optimization Options
| 
Option

 | 

Description

 |
| --- | --- |
| 

`includeOptionalCovSelectFlag`

 | 

`true` or `false`

Defaults to `false`.

Set this option to `true` to have the service evaluate optional coverage rules before passing rating inputs to calculation procedures.

If products don't use optional coverages, use the default setting of `false`. Getting and adding optional coverage data to rating input requires extra processing and can slow down this service.

 |
| 

`includeRawCalculationResult`

 | 

`true` or `false`

Defaults to `false`.

Includes the entire results of calculation procedure in the `RawPriceData` key.

 |
| 

`isBatchMode`

 | 

`true` or `false`

When set to `true`, the service returns a simplified product JSON that doesn’t include attribute categories, but does include attribute-selected values and rules.

When set to `false`, the service returns the full product JSON.

This option is useful when there's no UI consuming the results of the service. For example, if you're running an integration procedure in batch mode that contains this service.

 |
| 

`mergeList`

 | 

`true` or `false`

Defaults to `false`.

Optimizes rating calls by grouping rating procedure calls by products using the same rating procedure. It makes one rating call with an array of input objects.

This is useful when pulling a large list of products. Multiple rating calls can hit SQL limits. The rating procedure architecture is optimized to handle an array of input objects and minimize the number of SQL queries needed.

 |
| 

`omitChildren`

 | 

`true` or `false`

Set this option to true only if you also set `omitRating` to `true`. This returns products without pricing.

 |
| 

`omitRating`

 | 

`true` or `false`

If true, the service returns products without pricing.

 |
| 

`productClasses`

 | 

“ProductClassName1,ProductClassName2”

Comma-separated list of product class names. Limits the list of products to these product classes.

 |
| 

`rootPricingOnly`

 | 

`true` or `false`

Defaults to `false`.

This option improves performance by reducing heap sizes.

If the rating procedure you're using is defined at the root product level only, you can set this option to `true` to improve performance.

 |

Rules Options
| 
Option

 | 

Description

 |
| --- | --- |
| 

`evalOptionalCoverageRelationship`

 | 

`true` or `false`If set to `true`, the service runs optional coverage relationship rules.

 |
| 

`omitEligibility`

 | 

`true` or `false`

Defaults to `false`.

When set to `true`, the service doesn’t query for eligible products.

Instead, you must provide a list product Id under the key `products` in the input map or option map. Both a list of product Ids or a string of comma-separated product Ids are acceptable values for `products`.

 |
| 

`ruleAttributeSetValues`

 | 

`true` or `false`

When set to `false`, the service doesn’t run attribute set value rules.

When set to `true`, the service runs the attribute set value rules.

 |
| 

`validateCoverageSelection`

 | 

`true` or `false`

Set to `true` if you have validation rules that you need the service to run.

 |

Add-On Function Options
| 
Option

 | 

Description

 |
| --- | --- |
| 

`calculateTaxesAndFees`

 | 

Optional

`true` or `false`

When set to `true`, calculates taxes and fees on the target product.

 |
| 

[](https://help.salesforce.com/s?language=en_US)`includeFullProductJson`

 | 

[](https://help.salesforce.com/s?language=en_US)`true` or `false`

[](https://help.salesforce.com/s?language=en_US)This option controls the presence of additional grandchild nodes in response to the API based on the input JSON. When set to true, there are two changes in the output JSON:

[](https://help.salesforce.com/s?language=en_US)

-   If the grandchild's type is **Insured Party**, then the parent JSON node contains two extra child nodes; primary party and other parties. These two new nodes populate based on if the `isPrimary` flag is set for the grandchild node.
    
-   If the grandchild's type is **Insured Item**, then these two nodes (primary party and other parties) are not present in the response API. The grandchildren contained in the input JSON are linked to the correct parent node in the output JSON of the API.
    

[](https://help.salesforce.com/s?language=en_US)For backward compatibility, the default is `false`.

 |
| 

`jurisdictionIds`

 | 

Type: Stringifed list of ids

Used in conjunction with `calculateTaxesAndFees` option.

Calculates only those taxes and fees associated with the provided jurisdictions.

 |
| 

`taxAndFeeEffectiveDate`

 | 

The effective date this service uses to calculate taxes and fees. This option is separate from the `effectiveDate` option used to Price the product.

If a value is provided, the service uses that value.

If a value isn’t provided and the product JSON isn’t a policy, the service defaults to today’s date.

 |
| `withTaxFeeRounding` | 

Optional

If true, the calculated tax and fee amounts are rounded to two decimal places by using the half even rounding method. `withTaxFeeRounding` is effective only when the `calculateTaxesAndFees` option is also true. If false, rounding is disabled.

Default value is false.

 |

UI Options
| 
Option

 | 

Description

 |
| --- | --- |
| 

`lastRecordId`

 | 

Specifies the last product Id that the service pulled into the UI.

Use this option with the `pageSize` option.

 |
| 

`pageSize`

 | 

Determine how many products the service returns to the UI in one call.

 |

## Input JSON

`InsProductService: getRatedProducts` looks for a `userInputs` key in the input JSON. Use the appropriate `userInputs` format depending on the product definition and the rating configuration. The service accepts only one type of userInputs format at a time.

-   [One Rating Procedure per Product for getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_one_rating_procedure_per_product.htm&language=en_US&type=5 "Format InsProductService:getRatedProducts userInputs for products that use a single rating procedure per root product.")
    
    Format `userInputs` for products that use a single rating procedure per root product.
    
-   [Multiple Rating Procedures per Product or Multiple Specs at Any Level for getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_multiple_rating_procedures_per_product_or_multiple_specs_at_any_level.htm&language=en_US&type=5 "Format InsProductService:getRatedProducts userInputs for products that use multiple rating procedures in the product hierarchy or multiple child specs in any level of the hierarchy.")
    
    Format `userInputs` for products that use multiple rating procedures in the product hierarchy or multiple child specs in any level of the hierarchy.
    

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an array of one or more product objects. See the Product JSON Structure Model for more information about this object.

[](https://help.salesforce.com/s?language=en_US)Any mapped `userInputs` from the input JSON get added to the product object as the `userValues` key of the single instance of the attribute it was mapped to.

[](https://help.salesforce.com/s?language=en_US)For each product, the output JSON from the rating procedure calculation gets added to the product with the `CalculatedPriceData` key. If the pricing formula is set on the product, the value of `Price` will be set to its calculated value. If the total insured formula is set on the product, the value of `TotalInsured` is set to its calculated value.

[](https://help.salesforce.com/s?language=en_US)In this example, the pricing formula is set on the product, but the total insured formula isn’t. The `CalculatedPriceData` is added to the results from the rating procedure, then the price is calculated based on the formula. The total insured formula doesn’t appear in the data, nor does `TotalInsured`.

[](https://help.salesforce.com/s?language=en_US)`{   "totalSize": 2,   "records": [{       "displaySequence": -1,       "CalculatedPriceData": {         "ID": "1",         "basePremium": 719,         "premGenlLiab": "356"       },       "Id": "01t6A000000FshIQAS",       "Name": "Economy Business",       "Family": "Commercial Lines",       "ProductCode": "bop-ECON",       "LineOfBusiness__c": "Property & Casualty",       "Type__c": "BusinessOwners",       "IsRecommended__c": false,       "RecordTypeName__c": "Product",       "IsConfigurable__c": true,       "PricingFormula__c": "basePremium + premGenlLiab",       "Term__c": "Annual",       "productId": "01t6A000000FshIQAS",       "Price": 1075,       "childProducts": {         ...       },       "attributeCategories": {         ...       }     },     {       ...     }   }`

filterAttrValues Key

The `includeFilterAttrValues` option puts the product array in a `ratedProducts` node and adds a `filterAttrValues` result alongside.

[](https://help.salesforce.com/s?language=en_US)`{   "result": {     "filterAttrValues": {       "covType": {         "listOfValues": [           "Superior",           "Economy"         ],         "valueDataType": "Text",         "attributeName": "Type",         "categoryName": "Policy Terms"       },       "covDeductible": {         "listOfValues": [           "1000",           "250"         ],         "valueDataType": "Currency",         "attributeName": "Deductible",         "categoryName": "Policy Terms"       }     },     "ratedProducts": {       "totalSize": 2,       "records": [{           "displaySequence": -1,           "CalculatedPriceData": {             "ID": "1",             "basePremium": 719,             "premGenlLiab": "356"           },           "Id": "01t6A000000FshIQAS",           "Name": "Economy Business",           "Family": "Commercial Lines",           "ProductCode": "bop-ECON",           ...,           "Price": 1075,           "childProducts": {             ...           },           "attributeCategories": {             ...           }         },         {           ...         }       }     }   }`

[](https://help.salesforce.com/s?language=en_US)Each filterable attribute is added to the object with the key set to the attribute code. The value of each filter attribute is an object that contains the following:

| 
Key

 | 

Value

 |
| --- | --- |
| 

`attributeName`

 | 

The name of the attribute.

 |
| 

`categoryName`

 | 

The name of the category.

 |
| 

`listOfValues`

 | 

The list of possible values from the product in the array.

 |
| 

`valueDataType`

 | 

The data type of the attribute, such as Text or Currency.

 |

[](https://help.salesforce.com/s?language=en_US)

## Taxes and Fees

If taxes and fees use the service, calculated taxes and fees appear on a JSON record in three distinct ways:

1.  If the record has calculated taxes and fees, they’re stored as a list on the `taxesAndFees` field.
    
    ```
    {
      "taxesAndFees": [{
        "Id": 1,
        "calculatedAmount": 10,
        "Type__c": "Tax"
      }, {
        "Id": 2,
        "calculatedAmount": 15,
        "Type__c": "Fee"
      }]
    }
    ```
    
2.  If the record has calculated taxes on itself or its children, the sum of the calculated taxes on itself and its children are stored on the `taxAmount` field.
    
    ```
    {  "taxAmount”: 25 // 10 from self, 15 from children}
    ```
    
3.  If the record has calculated fees on itself or its children, the sum of the calculated fees on itself and its children are stored on the `feeAmount` field.
    
    ```
    {  "feeAmount”: 30 // 15 from self, 15 from children}
    ```
    

A sample JSON output, with taxes and fees on the child records as well as the root, will look something like this:

```
{
  "Id": 1,
  "productName": "Product",
  "taxesAndFees": [{
    "Id": 1,
    "calculatedAmount": 10,
    "Type__c": "Tax"
  }, {
    "Id": 2,
    "calculatedAmount": 15,
    "Type__c": "Fee"
  }],
  "taxAmount": 25
  "feeAmount": 30
  "childProducts": {
    "records": [{
      "Id": 2,
      "productName": "Insured Item",
      "taxesAndFees": [{
        "Id": 3,
        "calculatedAmount": 15,
        "Type__c": "Tax"
      }],
      "taxAmount": 15
    }, {
      "Id": 3,
      "productName": "Coverage",
      "taxesAndFees": [{
        "Id": 4,
        "calculatedAmount": 15,
        "Type__c": "Fee"
      }],
      "feeAmount": 15
    }]
  }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Star Rating

You can use the `attributeFilters` input to filter products based on ratings, created as attributes by a product modeler.

-   **[One Rating Procedure per Product for getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_one_rating_procedure_per_product.htm&language=en_US&type=5)**  
    Format `InsProductService:getRatedProducts userInputs` for products that use a single rating procedure per root product.
-   **[Multiple Rating Procedures per Product or Multiple Specs at Any Level for getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_multiple_rating_procedures_per_product_or_multiple_specs_at_any_level.htm&language=en_US&type=5)**  
    Format `InsProductService:getRatedProducts userInputs` for products that use multiple rating procedures in the product hierarchy or multiple child specs in any level of the hierarchy.

Did this article solve your issue?

Let us know so we can improve!

YesNo