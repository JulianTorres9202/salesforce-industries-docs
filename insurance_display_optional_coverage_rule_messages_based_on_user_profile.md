---
title: "Display Optional Coverage Rule Messages Based on User Profiles"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_display_optional_coverage_rule_messages_based_on_user_profile.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Display Optional Coverage Rule Messages Based on User Profiles

Display Optional Coverage Rule Messages Based on User Profiles[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Display Optional Coverage Rule Messages Based on User Profiles

Show users optional coverage validation rule messages based on their user profile. For example, when a Customer Service Representative creates an auto insurance quote, display a message on the Rental Car optional coverage rule stating that rental car users must be over 21 years old. When a Sales Agent creates a quote, don’t display the message.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package.

**How:** Create an expression for a Validation Rule on an optional coverage with the `USER_PROFILE` parameter. When the rule evaluates to false the message displays. For example, to display a message for the Customer Service Representative profile but not the Sales Agent profile, use this syntax in the expression.

```json
USER_PROFILE = 'Sales Agent'
```

## See Also

-   [Profile-Based Optional Coverage Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_profile_based_optional_coverage_rules.htm&language=en_US&type=5 "Customize optional coverage rule behaviors for users based on the user profiles.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo