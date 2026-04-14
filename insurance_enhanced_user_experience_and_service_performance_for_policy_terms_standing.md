---
title: "Enhanced User Experience and Performance for Policy Terms Standing"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_enhanced_user_experience_and_service_performance_for_policy_terms_standing.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Enhanced User Experience and Performance for Policy Terms Standing

Enhanced User Experience and Performance for Policy Terms Standing[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Enhanced User Experience and Performance for Policy Terms Standing

We've enhanced the Policy Terms Standing card to show policy terms separately in Policy Details and Coverage Details sections. The Policy Details section displays terms standing at the policy level and policy coverage level without any participant or asset ID. The Coverage Details section shows the list of participants or assets that belong to the `policyId` and retrieves the current standings for the selected `insuredId` at the coverage level.

We have also added new `PolicyParticipantId`, `PolicyCoverageId`, and `PolicyAssetId` parameters in InsPolicyTermsService:getCurrentStanding to improve the service performance and expand its usage in claims, insurance policies, and payments.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package.

Did this article solve your issue?

Let us know so we can improve!

YesNo