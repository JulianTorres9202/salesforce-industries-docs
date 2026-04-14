---
title: "Display Attribute Messages Based on User Profiles"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_display_attribute_messages_based_on_user_profile.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Display Attribute Messages Based on User Profiles

Display Attribute Messages Based on User Profiles[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Display Attribute Messages Based on User Profiles

Show users product attribute messages based on their user profile. For example, when a Customer Service Representative creates an auto insurance quote, display a message alerting them that the Good Student attribute is subject to GPA verification. When a Sales Agent creates a quote, don’t display the message.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package.

**How:** Create a `Message` attribute rule with the `USER_PROFILE` parameter in the expression. For example, to display an attribute message for the Customer Service Representative profile, use this syntax in the expression.

```json
%USER_PROFILE% = 'Customer Service Representative'
```

## See Also

-   [Profile-Based Insurance Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_profile-based_insurance_rules.htm&language=en_US&type=5 "Customize your insurance product model internally and across customer channels by using rules tailored to different user profiles.")

Did this article solve your issue?

Let us know so we can improve!

YesNo