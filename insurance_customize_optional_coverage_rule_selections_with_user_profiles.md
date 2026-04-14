---
title: "Customize Optional Coverage Rule Selections Based on User Profiles"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_customize_optional_coverage_rule_selections_with_user_profiles.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize Optional Coverage Rule Selections Based on User Profiles

Customize Optional Coverage Rule Selections Based on User Profiles[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize Optional Coverage Rule Selections Based on User Profiles

Automatically select Required Coverage or Default Selected optional coverage rules for users based on their user profile. For example, when a Customer Service Representative creates a car insurance quote, have the Rental Car coverage selected automatically. When a Sales Agent creates a quote, list Rental Car coverage as available for selection but not selected automatically.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package.

**How:** Create an expression for a Required Coverage or Default Selected optional coverage rule with the `USER_PROFILE` parameter. For example, to automatically select an optional coverage as Required for the Customer Service Representative profile, use this syntax in the expression.

```json
USER_PROFILE = 'Customer Service Representative'
```

## See Also

-   [Profile-Based Optional Coverage Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_profile_based_optional_coverage_rules.htm&language=en_US&type=5 "Customize optional coverage rule behaviors for users based on the user profiles.")

Did this article solve your issue?

Let us know so we can improve!

YesNo