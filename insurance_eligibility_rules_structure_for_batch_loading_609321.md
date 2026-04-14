---
title: "Eligibility Rules Structure for Batch Loading"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_eligibility_rules_structure_for_batch_loading_609321.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Eligibility Rules Structure for Batch Loading

Eligibility Rules Structure for Batch Loading[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Eligibility Rules Structure for Batch Loading

If you have to add eligibility rules at the root product level or at the optional coverage level to hundreds or thousands of products, you can write scripts to batch load rules directly into the database.

[](https://help.salesforce.com/s?language=en_US)

## Root Product Eligibility Rules

Before you batch upload root product eligibility rules, create a plan that includes the following:

-   Product Ids for each product that needs eligibility rules
    
-   Definition of each rule
    

Root product eligibility rules are stored in the `Product2.EligibilityCriteria__c` field.

The only data you need to load into this field is the expression that creates the condition for the rule.

Did this article solve your issue?

Let us know so we can improve!

YesNo