---
title: "Product JSON Structure Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_product_json_structure_model_609451.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Product JSON Structure Model

Product JSON Structure Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Product JSON Structure Model

The product JSON object provides a portable product data object for runtime use between services and templates.

Many Vlocity insurance services are built to input and/or output product data objects. The product object definition is a map of a product as designed in Vlocity by a product administrator. Each product JSON object includes product data, attributes, child products, and service-specific data.

A product JSON's basic structure looks like this:

[](https://help.salesforce.com/s?language=en_US)

## Product- and Service-Specific Data

Product data with service-specific data looks like this:

[](https://help.salesforce.com/s?language=en_US)Many services add data to the product object as part of its action.

[](https://help.salesforce.com/s?language=en_US)Attributes data is organized by attribute category. Each attribute category contains data about the category and an object with an array of attributes directly associated to the product.

[](https://help.salesforce.com/s?language=en_US)Some services can take data added to the product object.

[](https://help.salesforce.com/s?language=en_US)For example, the `createUpdatePolicy` service can take an `additionalFields` JSON in the product object. The `additionalFields` JSON is a listing of field key/value pairs that it sets when creating or updating the product record.

[](https://help.salesforce.com/s?language=en_US)Each service has a list of specific data it takes in or adds to the product object as part of its input or output JSON.

[](https://help.salesforce.com/s?language=en_US)

## Attributes

Attributes help define a product. All the attributes for a product are stored in an object within an `attributeCategories` key. This object’s definition is the same whether it's for root products or child products. It only contains attributes associated to that specific product or child product.

[](https://help.salesforce.com/s?language=en_US)The attribute array is organized by attribute category. Each attribute category object in the array contains one or more attribute objects in the record array of the `productAttributes` object.

[](https://help.salesforce.com/s?language=en_US)Each attribute object in the array contains the attribute data defined by the attribute assignment record for the specific product attribute relationship in the product definition.

[](https://help.salesforce.com/s?language=en_US)An attribute object contains attribute data that defines the attribute. For configurable attributes, the attribute object can contain a single value or sets of values in an array of values objects. Configurable attributes have the `readonly` value set to `false`. Each attribute has a `userValue` that is the value used for rating if it's mapped.

[](https://help.salesforce.com/s?language=en_US)Rules associated to the attribute or values are added in an array of rules objects in a rules node.

[](https://help.salesforce.com/s?language=en_US)An attribute category with attribute data looks like this:

[](https://help.salesforce.com/s?language=en_US)

## Child and (grand)child Products

Child products are associated to root parent products or to first-level child products, they're never standalone. Coverage spec, insured item spec, insured party spec, and rating facts product types are examples of child products.

[](https://help.salesforce.com/s?language=en_US)You can find the record type of a child product in `RecordTypeName__c` of the child product object. Child products use the same product object structure as the root product, but they are defined differently based on their intended usage. Also, coverage spec child products include an `isOptional` key/value pair that's exposed in the product administration UI for child products, but not for the root product.

[](https://help.salesforce.com/s?language=en_US)Starting with the Vlocity Insurance Summer '18 release, child products include pricingFormula\_\_c.

[](https://help.salesforce.com/s?language=en_US)Starting with Vlocity Insurance/Vlocity Health Summer '18 release, the product structure supports the following structure:

[](https://help.salesforce.com/s?language=en_US)Child and grandchild products now include instanceKey fields. Each instanceKey describes a unique instance of an insured item in a policy that includes multiple insured items.

[](https://help.salesforce.com/s?language=en_US)

-   Root product
    
    -   Child product
        
        -   (Grand)Child product
            
            Grandchild products are called childProducts, but the records are nested inside the first-level child product they are associated with.
            

[](https://help.salesforce.com/s?language=en_US)Child and grandchild products now include instanceKey fields. Each instanceKey describes a unique instance of an insured item in a policy that includes multiple insured items.

[](https://help.salesforce.com/s?language=en_US)(Grand)Child product records and their attribute records are structured the same way as first-level child products and root products. They include a `parentInstanceKey` field that ties them to the instance of the first-level child product they're associated with.

[](https://help.salesforce.com/s?language=en_US)The child product structure looks like this:

[](https://help.salesforce.com/s?language=en_US)

## Keys Catalog

The following are lists of the most common keys organized by type.

[](https://help.salesforce.com/s?language=en_US)Many fields are pulled directly from the object in Salesforce, which are specified in the description. Most Salesforce object field names equal the name of the key and are also specified in the description. In Salesforce, the field is prefaced by the namespace `<namespace>__<fieldname>`, for example `vlocityins__isConfigurable`.

[](https://help.salesforce.com/s?language=en_US)

## Product

| 
Key

 | 

Description

 |
| --- | --- |
| 

`additionalFields`

 | 

Object that contains key/value pairs of any product fields that are not part of the service. An optional addition used for input to Create/Update services.

 |
| 

`attributeCategories`

 | 

Attribute category records data structure, which contains a records array of attribute categories. Each category contains an array of attributes data.

 |
| 

`CalculatedPriceData`

 | 

The JSON data produced by the calculation procedure or Integration Procedure.

 |
| 

`childProducts`

 | 

Child product records data structure, which contains records array of child products. Possible record types include coverage spec, insured item spec, and rating fact spec.

 |
| 

`Description`

 | 

Product2 field

 |
| 

`displaySequence`

 |   |
| 

`Family`

 | 

Product2 field

 |
| 

`Id`

 | 

Product2 field

 |
| 

`ImageId`

 | 

Product2 field pulled from `product2.Attachment`.

 |
| 

```
instanceKey
```

 | 

Identifies the specific instance of the insured item.

 |
| 

`IsConfigurable`\_\_c

 | 

Product2 field

 |
| 

`isOptional`

 | 

`ProductChildItem__c` field is `Optional__c`, used in coverage spec product records.

 |
| 

`IsRecommended__c`

 | 

Product2 field

 |
| 

`LineOfBusiness__c`

 | 

Product2 field

 |
| 

`Name`

 | 

Product2 field

 |
| 

```
parentInstanceKey
```

 | 

The instance key of a (grand)child product's parent product.

 |
| 

`Price`

 | 

Calculated using the formula in `PricingFormula__c` or `PricingSource__c`.

 |
| 

```
priceDiff
```

 | 

The difference between the existing policy price and the new calculated price.

 |
| 

`PricingFormula__c`

 | 

Product2 field

 |
| 

`ProductCode`

 | 

Product2 field

 |
| 

`productId`

 | 

Salesforce record ID of the product

 |
| 

```
rawPriceData
```

 | 

This node is included when the remote option `includeRawCalculationResult` is set to `true`.

 |
| 

`RecordTypeName__c`

 | 

Product, CoverageSpec, InsuredItemSpce, or RatingFactSpec

 |
| 

`SubType__c`

 | 

Product2 field

 |
| 

`Term__c`

 | 

Product2 field

 |
| 

`TotalInsuredFormula__c`

 | 

Product2 field

 |
| 

```
totalPremiumForTermDiff
```

 | 

The difference between the original total premium for term and the sum between the total premium for term of the new policy version and the updated premium for term of the old policy version

 |
| 

`totalSumInsured`

 | 

Calculated using the formula in `TotalInsuredFormula__c`.

 |
| 

`Type__c`

 | 

Product2 field

 |

[](https://help.salesforce.com/s?language=en_US)

## Attribute

| 
Key

 | 

Description

 |
| --- | --- |
| 

`Code__c`

 | 

Attribute category field

 |
| 

`displaySequence`

 | 

Attribute category field

 |
| 

`Id`

 | 

Attribute category field

 |
| 

`Name`

 | 

Attribute category field

 |
| 

`productAttributes`

 | 

Product attributes records data object, contains records array of attribute objects.

 |

[](https://help.salesforce.com/s?language=en_US)

## Values

[](https://help.salesforce.com/s?language=en_US)Note

The values array is stored in the `ValidValuesData__c` in the attribute assignment object.

| 
Key

 | 

Description

 |
| --- | --- |
| 

`disabled`

 |   |
| 

`id`

 | 

Sequencing id of value data object within the values array.

 |
| 

`label`

 | 

Display label for the UI.

 |
| 

`readonly`

 |   |
| 

`rules`

 | 

Array of rules objects.

 |
| 

`value`

 | 

The actual value the label represents.

 |

[](https://help.salesforce.com/s?language=en_US)

## Rules

[](https://help.salesforce.com/s?language=en_US)Note

The rules array is stored in the `RuleData__c` in the attribute assignment object.

| 
Key

 | 

Description

 |
| --- | --- |
| 

actions

 | 

Definition of the action.

 |
| 

expression

 | 

An expression that is evaluated as follows:

True: Trigger the action for the rule.

False: No action is triggered.

 |
| 

message

 | 

For rules of type message, this value contains

-   Text of the message to display
    
-   Message code
    
-   Message severity
    

The severity determines how the message displays.

 |
| 

rule type

 | 

Three rule types are supported:

-   Hide
    
-   Message
    
-   SetValue
    

 |
| 

value expression

 | 

Enter `valueExpression` as the key.

For value, enter a valid %valueExpression%.

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo