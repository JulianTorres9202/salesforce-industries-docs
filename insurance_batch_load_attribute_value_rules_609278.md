---
title: "Batch Load Attribute Value Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_batch_load_attribute_value_rules_609278.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Batch Load Attribute Value Rules

Batch Load Attribute Value Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Batch Load Attribute Value Rules

An attribute value rule is a rule you assign to one specific attribute value.

[](https://help.salesforce.com/s?language=en_US)The only rule type that's valid for attribute values is Hide. In the UI, an attribute value rule looks like this:

[](https://help.salesforce.com/s?language=en_US)For example, you have a coverage on a health insurance product with a Copay attribute. On one or more health insurance products, you've listed values for the Copay attribute of $10, $20, $25, and $100. You can attach a rule to any of these specific values. For example, on the Outpatient Surgery coverage in a health plan, you can attach a rule to the $10 copay that specifies that if Deductible < = $1000, the rule evaluates to true and the $10 copay is hidden from the user.

[](https://help.salesforce.com/s?language=en_US)Attribute value rules are stored in the AttributeAssignment\_\_c.ValidValuesData\_\_c field. For any value that has an attached rule, a rule node is stored in the field.

[](https://help.salesforce.com/s?language=en_US)We recommend that you use `"value":"thisattributevalue"` to identify values to attach rules to. The `"id":"idvalue"` varies per coverage and product, and isn't a reliable hook to use to batch load the correct rules to the correct attribute values.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Before you start putting your script together, put together a plan that contains:

[](https://help.salesforce.com/s?language=en_US)

-   PCI IDs (for product child level rules ) or Product IDs (for spec level rules) for all coverages you want to add attribute value rules to on coverages, insured items, and insured parties
    
    or
    
    Product IDs for all coverage specs, insured items, and insured parties you want to add attribute value rules to
    
-   Product IDs for all root products with product-level attributes with values you want to add rules to
    
-   AttributeUniqueCodes for the attributes that have values you want to add rules to
    
-   Values the rule will apply to
    
-   Definition of each rule
    

[](https://help.salesforce.com/s?language=en_US)When you create your script, make sure that the attribute value rule data is stored in the `AttributeAssignment__c.ValidValuesData__c` field.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)Note

If you've used a SOQL query to extract the rule structure from an org, be aware that the following lines are added by the UI, and are not required when you're using a script to upload rules directly to the database:

-   `"$$hashKey"`
    
-   `"validation": {...}`
    

[](https://help.salesforce.com/s?language=en_US)

## Attribute Value Rule Structure

For all attribute value rules, the following information is stored in the `AttributeAssignment__c.ValidValuesData__c` field:

```
[{
		"isAvailable": true,
		"id": 0,
		"displayText": "30",
		"value": "30",
		"isDefault": false,
		"showRules": false,
		"rules": []
	},
	{
		"isAvailable": true,
		"value": "90",
		"isDefault": true,
		"displayText": "90",
		"id": 1,
		"showRules": false,
		"rules": []
	},
	{
		"isAvailable": true,
		"value": "180",
		"isDefault": false,
		"displayText": "180",
		"id": 2,
		"showRules": true,
		"rules": [{
			"ruleType": "Hide",
			"messageType": {},
			"expression": "%InsLife.lifeCoveageAmt% = 250000",
			"messageText": ""
		}]
	}
]
```

Did this article solve your issue?

Let us know so we can improve!

YesNo