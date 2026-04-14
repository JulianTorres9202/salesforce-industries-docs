---
title: "Optional Coverage Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_optional_coverage_rules.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Optional Coverage Rules

Optional Coverage Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Optional Coverage Rules

Several types of rules apply to optional coverages on Insurance and Health products. Set rules up based on eligibility for optional coverage, whether optional coverages are required or selected by default, and valid combinations of optional coverages.

Note

When you enter expressions into optional coverage rules, you'll see `isSelected` appear in the type-ahead for all types of rules.

But `isSelected` is evaluated only on validation rules.

-   **[Add Optional Coverage Eligibility Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_add_optional_coverage_eligibility_rules_607720.htm&language=en_US&type=5)**  
    When an optional coverage eligibility rule is invoked, the customer or agent sees only the available insurance products that meet this rule (that is, when the rule returns true).
-   **[Add Required Coverage Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_add_required_coverage_rules_607787.htm&language=en_US&type=5)**  
    You can create rules that describe the situations where some insurance policies require a specific optional coverage. For example, an Auto policy requires Collision Deductible Waiver coverage when Comprehensive coverage is selected.
-   **[Add Default Coverage Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_add_default_coverage_rules_607816.htm&language=en_US&type=5)**  
    To specify when an optional coverage is selected by default, use default coverage rules. For example, for Roadside Assistance optional coverage in an Auto policy, you can create a rule that makes Roadside Assistance selected by default when Comprehensive coverage is selected.
-   **[Add Optional Coverage Validation Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_add_optional_coverage_validation_rules_607850.htm&language=en_US&type=5)**  
    To validate whether an optional coverage can be selected in a quote or policy, create optional coverage validation rules. These rules can display custom error messages that tell your users how to fix a problem that keeps them from adding an optional coverage. For example, a rule can ensure that a certain optional coverage isn't selected if a different optional coverage is already selected.
-   **[Add Optional Coverage Relationship Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_add_optional_coverage_relationship_rules_607925.htm&language=en_US&type=5)**  
    Use optional coverage relationship rules for optional coverages that are either dependent on other optional coverages, or mutually exclusive of other optional coverages.

Did this article solve your issue?

Let us know so we can improve!

YesNo