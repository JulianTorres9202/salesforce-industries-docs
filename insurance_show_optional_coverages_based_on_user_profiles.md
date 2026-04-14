---
title: "Show Optional Coverages Based on User Profiles"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_show_optional_coverages_based_on_user_profiles.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Show Optional Coverages Based on User Profiles

Show Optional Coverages Based on User Profiles[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Show Optional Coverages Based on User Profiles

Control which users can see optional coverages with profile-based eligibility rules. For example, when a Customer Service Representative creates an auto insurance quote, show the Rental Car coverage as available for selection. But when a Guest user creates a quote, don’t show the Rental Car coverage as an option.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package.

**How:** Create an expression for an Eligibility optional coverage rule with the ​USER\_PROFILE​ parameter. For example, to show an optional coverage as available for the Customer Service Representative profile, use this syntax in the expression.

```json
USER_PROFILE = 'Customer Service Representative'
```

## See Also

-   [Profile-Based Optional Coverage Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_profile_based_optional_coverage_rules.htm&language=en_US&type=5 "Customize optional coverage rule behaviors for users based on the user profiles.")

Did this article solve your issue?

Let us know so we can improve!

YesNo