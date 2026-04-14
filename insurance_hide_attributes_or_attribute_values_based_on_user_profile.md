---
title: "Hide Attributes or Attribute Values Based on User Profiles"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_hide_attributes_or_attribute_values_based_on_user_profile.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Hide Attributes or Attribute Values Based on User Profiles

Hide Attributes or Attribute Values Based on User Profiles[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Hide Attributes or Attribute Values Based on User Profiles

Hide product attributes or attribute values from users based on their user profile. For example, when a Customer Service Representative creates an auto insurance quote, hide the Rental Car Limit attribute by using attribute rules. However, when a Sales Agent creates a quote, show the Rental Car Limit attribute.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package.

**How:** Create a `Hide` or `Attribute Value Hide` attribute rule with the `USER_PROFILE` parameter in the expression. For example, to hide an attribute value for the Customer Service Representative profile, use this syntax in the expression.

```json
%USER_PROFILE% = 'Customer Service Representative'
```

## See Also

-   [Profile-Based Insurance Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_profile-based_insurance_rules.htm&language=en_US&type=5 "Customize your insurance product model internally and across customer channels by using rules tailored to different user profiles.")

Did this article solve your issue?

Let us know so we can improve!

YesNo