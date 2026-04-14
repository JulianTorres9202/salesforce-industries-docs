---
title: "Quoting and Rating Key Considerations"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_quoting_and_rating_considerations.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Quoting and Rating Key Considerations

Quoting and Rating Key Considerations[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Quoting and Rating Key Considerations

Understand how quoting, pricing, and underwriting work in multi-root quotes, including product configuration, pricing aggregation, instance key rules, and rule evaluation behavior.

-   Quoting and Rating APIs are compatible with multi-root operations in the current format.
-   The Rating API JSON output response displays aggregated standard premium amounts for multi-root quotes.
-   You can add multiple products to the quote using the browse catalog on the quote UI and configure them independently via the configurator UI.
-   Multi-root quotes don’t support duplicate instance keys across different root product bundles. For example, if a quote includes two root products, such as Auto Silver and Auto Gold, and the ProductInstanceReuse flag is enabled for the Driver product, the same driver instance can be reused within Auto Silver or within Auto Gold when the instance key matches. However, the same driver instance can’t be shared across both Auto Silver and Auto Gold.
-   The reuse functionality is supported only within a single root product.
-   Use Decision Tables for pricing when quoting involves large data shapes. Decision Matrix doesn’t scale and supports a maximum of 200 invocations per pricing API call.
-   Underwriting Rules:
    -   You can define underwriting rules to multiple root products in a multi-root quote.
    -   When rulesets on different root products run for the same stage transition (for example, Draft to Submitted), underwriting rules evaluate the results using an AND condition.
    -   When an underwriting rule applies to a product that belongs to a product bundle, the rule evaluates to true if at least one instance of that product in the quote meets the criteria. For example, an underwriting rule checks whether Vehicle Year is greater than 2020. An Auto root product includes two vehicles with years 2018 and 2024. The rule evaluates to true because one vehicle instance meets the condition.
    -   Underwriting Rule response structure has been changed to show rulesets executed for each of the root products and their respective evaluation criteria with evaluation success result.
    -   Underwriting rule response structure
        -   The underwriting response returns rule evaluation results per root product, along with the evaluation criteria and the success or failure status for each ruleset.
        -   For each root product, the response identifies the product on which the rules run, shows the evaluation criteria applied to that product and indicates whether each rule and ruleset evaluates successfully. The overall stage transition result reflects the combined outcome of all root-product evaluations.

Sample response

The following example shows underwriting evaluation results returned for multiple root products during a stage transition.

```json
{
    "errors": [],
    "fromStage": "Draft",
    "isSuccess": false,
    "objectId": "0Q0xx0000004CNYCA2",
    "ruleSetResult": [
        {
            "evaluationCriteria": "1",
            "isSuccess": false,
            "productId": "01txx0000006i3DAAQ",
            "ruleResult": [
                {
                    "isSuccess": false,
                    "ruleApiName": "AutoModelSUVAndYearGT2020"
                }
            ]
        },
        {
            "evaluationCriteria": "1 AND 2",
            "isSuccess": true,
            "productId": "01txx0000006i3GAAQ",
            "ruleResult": [
                {
                    "isSuccess": true,
                    "ruleApiName": "Health_Rule_Draft_InReview"
                },
                {
                    "isSuccess": true,
                    "ruleApiName": "Medical_Rule_DepMember_AgeGT18"
                }
            ]
        }
    ],
    "stageTransitionUnderwritingEvaluationId": "1Mjxx0000004D0GCAU",
    "toStage": "In Review"
}
```

Sample Result

The following example shows how underwriting evaluation results store per root product after evaluation.

```json
{
  "objectId": "0Q0xx0000004CNYCA2",
  "objectName": "Quote",
  "stageTransitionName": "Draft To In Review",
  "fromStage": "Draft",
  "toStage": "In Review",
  "ruleSetResults": [
    {
      "productId": "01txx0000006i3DAAQ",
      "evaluationCriteria": "1",
      "ruleResults": [
        {
          "ruleApiName": "AutoModelSUVAndYearGT2020",
          "evaluationFailureTaskGroup": "13oxx0000004CdhAAE",
          "evaluationSuccessTaskGroup": "13oxx0000004CdgAAE",
          "success": false
        }
      ],
      "success": false
    },
    {
      "productId": "01txx0000006i3GAAQ",
      "evaluationCriteria": "1 AND 2",
      "ruleResults": [
        {
          "ruleApiName": "Health_Rule_Draft_InReview",
          "evaluationFailureTaskGroup": "13oxx0000004CaTAAU",
          "evaluationSuccessTaskGroup": "13oxx0000004CaSAAU",
          "quoteLineItemId": [
            "0QLxx0000004CsDGAU"
          ],
          "success": true
        },
        {
          "ruleApiName": "Medical_Rule_DepMember_AgeGT18",
          "evaluationFailureTaskGroup": "13oxx0000004CYrAAM",
          "evaluationSuccessTaskGroup": "13oxx0000004CYqAAM",
          "quoteLineItemId": [
            "0QLxx0000004CsTGAU"
          ],
          "success": true
        }
      ],
      "success": true
    }
  ],
  "errors": null,
  "success": false
}

```

Did this article solve your issue?

Let us know so we can improve!

YesNo