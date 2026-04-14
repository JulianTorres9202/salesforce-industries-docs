---
title: "Customize Attribute Values Based On User Profiles"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_designate_attribute_availability_with_profile_based_attribute_rules_.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize Attribute Values Based On User Profiles

Customize Attribute Values Based On User Profiles[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize Attribute Values Based On User Profiles

Show users unique product attribute values based on their user profile. For example, when a Customer Service Representative creates a travel insurance quote, set the luggage loss coverage limit to $250 by using attribute rules. When a Captive Agent creates a quote, set the same coverage limit to $500.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package.

**How:** Create a `Set Value` or `Set Default Value` attribute rule with the `USER_PROFILE` parameter in the expression.

```json
USER_PROFILE = 'Customer Service Representative'
```

## See Also

[Profile-Based Insurance Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_profile-based_insurance_rules.htm&language=en_US&type=5 "Customize your insurance product model internally and across customer channels by using rules tailored to different user profiles.")

Did this article solve your issue?

Let us know so we can improve!

YesNo