---
title: "Use the Rating Date During Policy Lifecycle"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_use_the_rating_date_during_policy_lifecycle.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Use the Rating Date During Policy Lifecycle

Use the Rating Date During Policy Lifecycle[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Use the Rating Date During Policy Lifecycle

Use the rating dates to determine the pricing procedures to apply during mid-term adjustments, renewals, and out-of-sequence endorsements. Insurance providers can use a date other than the effective date to calculate the insurance policy premium.

**Where**: This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions.

**How**: The field is now available as an optional parameter in these services:

-   [InsPolicyService:createPolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createpolicyversion.htm&language=en_US&type=5 "Use this service to create a new version of an existing policy, while maintaining the existing policy record as-is.")
-   [InsPolicyService:createRenewalPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createrenewalpolicy.htm&language=en_US&type=5 "Use this service to create a renewal policy from an existing policy.")
-   [InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.")
-   [InsPolicyService:getModifiedPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__getmodifiedpolicy.htm&language=en_US&type=5 "Use this service when a user makes changes to the insured items or insured parties in an existing policy. The service takes the changes the user makes and returns modified policy data, including the recalculated price.")
-   [InsPolicyService:prepareToRenewPolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__preparetorenewpolicy.htm&language=en_US&type=5 "Use this service to calculate the amount required for renewing an existing policy. This service returns renewal premium, taxes, and fees, or the renewal policy JSON without creating a policy.")
-   [InsPolicyService:removeInsuredItem](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__removeinsureditem.htm&language=en_US&type=5 "Use this service to remove an insured item from an existing policy.")

Did this article solve your issue?

Let us know so we can improve!

YesNo