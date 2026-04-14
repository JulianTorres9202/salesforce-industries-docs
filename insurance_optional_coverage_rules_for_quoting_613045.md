---
title: "Optional Coverage Rules for Quoting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_optional_coverage_rules_for_quoting_613045.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Optional Coverage Rules for Quoting

Optional Coverage Rules for Quoting[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Optional Coverage Rules for Quoting

When you make changes to insured items, insured parties, and coverages on the Quote UI, optional coverage rules run. Which rules run and what the system does depends on what you've done to the quote.

[](https://help.salesforce.com/s?language=en_US)

Note

The Vlocity Insurance Quote Lightning web component does not support grandchild coverages. Use the Insurance Quote Commercial LWC if you need the ability to configure coverages at the grandchild level.

| 
Action

 | 

Eligibility Rules Run?

 | 

Required Coverage Rules Run?

 | 

Default Selected Rules Run?

 | 

Validation Rules Run?

 | 

Relationship Rules Run?

 |
| --- | --- | --- | --- | --- | --- |
| 

Add root product

 | 

✔️

 | 

✔️

 | 

✔️

 | 

✔️

 | 

✔️

 |
| 

Edit root product

 | 

✔️

 | 

✔️

 |   | 

✔️

 | 

✔️

 |
| 

Add insured item

 | 

✔️

 | 

✔️

 | 

✔️

 | 

✔️

 | 

✔️

 |
| 

Edit insured item

 | 

✔️

 | 

✔️

 |   | 

✔️

 | 

✔️

 |
| 

Delete insured item

 |  |  |  | 

✔️

 |  |
| 

Add a grandchild insured item

 | 

✔️

 | 

✔️

 |   | 

✔️

 | 

✔️

 |
| 

Edit a grandchild insured item

 | 

✔️

 | 

✔️

 |   | 

✔️

 | 

✔️

 |
| 

Delete a grandchild insured item

 |  |  |  | 

✔️

 |  |
| 

Add optional coverage

 |  |  |  | 

✔️

 | 

✔️

 |
| 

Edit optional coverage

 | 

✔️

 | 

✔️

 |   | 

✔️

 | 

✔️

 |
| 

Remove optional coverage

 | 

✔️

 | 

✔️

 |   | 

✔️

 | 

✔️

 |

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)For all optional coverage rules, if a message appears, it's in colored text. The colors mean:

[](https://help.salesforce.com/s?language=en_US)[](https://help.salesforce.com/s?language=en_US)

-   Blue = Information message. Read it and keep it in mind. Sometimes these messages make recommendations about configuring the quote.
    
-   Yellow = Warning message. You may have made a choice that's not against any rules but could cause problems down the road.
    
-   Red = Error. This rule evaluated to true, which created an error condition you need to resolve before you can rate the quote.
    

[](https://help.salesforce.com/s?language=en_US)

## Validation Rules Results

The results of these rules runs are stored in JSONMessage format on the quote line item they apply to.

If a validation rule evaluates to true and it impacts an attribute on a coverage that you need to pay attention to, a message appears that tells you what the rule requires for the coverage to remain valid.

If a validation rule with Severity = Error evaluates to true, the system blocks you from rating the quote until you fix the problem. An error message appears that tells you what the problem is.

[](https://help.salesforce.com/s?language=en_US)

## Relationship Rules

If a required relationship rule evaluates to true, another optional coverage is required. The second optional coverage is added automatically and can't be removed. (It's displayed as a required coverage.)

If an Exclude relationship rule evaluates to true, the other optional coverage specified in the rule must be excluded from the quote. The Add button for that coverage is disabled (grayed out) and the coverage gets added to the exclusion node in the quote line item JSON.

You first choose optional coverage 1 that doesn't have an Exclude rule attached to it. Then you choose optional coverage 2, which has an Exclude rule that excludes optional coverage 1 when optional coverage 2 is chosen.

The system shows an error message that tells you which two optional coverages are in conflict and disables the Rate Now button. You must fix the problem (remove one of the optional coverages) before you can rate the quote.

-   **[Profile-Based Optional Coverage Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_profile_based_optional_coverage_rules.htm&language=en_US&type=5)**  
    Customize optional coverage rule behaviors for users based on the user profiles.
-   **[Scope of Rule Evaluations](https://help.salesforce.com/s/articleView?id=ind.insurance_scope_of_rule_evaluations.htm&language=en_US&type=5)**  
    Editing root items, insured items, insured item parties, or coverages can change how optional coverage rules evaluate.

Did this article solve your issue?

Let us know so we can improve!

YesNo