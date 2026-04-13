---
title: "Batch Load Attribute Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_batch_load_attribute_rules_609199.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Batch Load Attribute Rules

Batch Load Attribute Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Batch Load Attribute Rules

You can write scripts to batch load attribute rules directly into the database.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Before you start putting your script together, put together a plan that contains:

[](https://help.salesforce.com/s?language=en_US)

-   PCI IDs for all coverages you want to add rules to on coverages, insured items, and insured parties
    
    or
    
    Product IDs for all coverage specs, insured items, and insured parties you want to add rules to
    
-   Product IDs for all root products with product-level attributes you want to add rules to
    
-   AttributeUniqueCodes for the attributes you want to add rules to
    
-   Values or conditions the rule will apply to
    
-   Type of each rule
    
-   Definition of each rule
    
-   Result of the rule evaluating true and false
    

[](https://help.salesforce.com/s?language=en_US)When you create your script, make sure of the following:

[](https://help.salesforce.com/s?language=en_US)

-   Attribute rule data is stored in the `AttributeAssignment__c.RuleData__c` field
    
-   Set `HasRule__c` to true
    

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

If you've used a SOQL query to extract the rule structure from an org, be aware that the following lines are added by the UI, and are not required when you're using a script to upload rules directly to the database:

-   `"$$hashKey"`
    
-   `"validation": {...}`
    

[](https://help.salesforce.com/s?language=en_US)

## Hide Rule Structure

In the UI, a hide rule looks like this:

For hide rules, the following information is stored in the `AttributeAssignment__c.RuleData__c` field:

```
[{
	"ruleType": "Hide",
	"messageType": {},
	"expression": "%ARF.Deductible% == 500",
	"messageText": ""
}]
```

For the expression, enter the condition under which the rule will evaluate to true and Vlocity will hide the attribute from the user. You can use any valid expression put together using standard formula syntax.

[](https://help.salesforce.com/s?language=en_US)

## Set Value Rule Structure

In the UI, a set value rule looks like this:

For set value rules, the following information is stored in the `AttributeAssignment__c.RuleData__c` field:

```
[{
	"ruleType": "Set Value",
	"messageType": {},
	"expression": "%InsLife.lifeCoveageAmt% == 1000000",
	"messageText": "",
	"valueExpression": "1200000"
}]
```

For the expression, enter the condition under which the rule will evaluate to true. You can use any valid expression put together using standard formula syntax.

The `valueExpression` is the value you want Vlocity to set if the rule condition in the expression field is met. `valueExpression` can be a constant or formula.

[](https://help.salesforce.com/s?language=en_US)

## Message Rule Structure

In the UI, a message rule looks like this:

For message rules, the following information is stored in the `AttributeAssignment__c.RuleData__c` field:

```
[{
	"ruleType": "Message",
	"messageType": {
		"code": "INFO"
	},
	"expression": "%InsLife.lifeCoveageAmt% == 1000000",
	"messageText": "Maximums is auto set to $1200000 because Coverage Amount is $250000"
}]
```

For the expression, enter the condition under which the rule will evaluate to true and the display the message set in the `messageText` field to the user. You can use any valid expression put together using standard formula syntax.

Did this article solve your issue?

Let us know so we can improve!

YesNo