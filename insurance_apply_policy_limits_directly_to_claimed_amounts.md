---
title: "Apply Policy Limits Directly to Claimed Amounts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_apply_policy_limits_directly_to_claimed_amounts.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Apply Policy Limits Directly to Claimed Amounts

Apply Policy Limits Directly to Claimed Amounts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Apply Policy Limits Directly to Claimed Amounts

Streamline claims processing by automatically applying currency limits to claimed amounts. Don’t wait until the payment processing stage to find out a claimed amount exceeds the limit. Configure your system to adjust the claimed amount upfront instead. Adjusting claimed amounts directly leads to smoother payment processing and a faster resolution of claims.

[](https://help.salesforce.com/s?language=en_US)**Where:** Available in Summer '22 and later releases.

**Why:** Applying limits early in the claims handling process improves the quality of data for the users who process payments later. The team members who issue payments don’t get errors about claimed amounts that exceed limits. With fewer errors, a higher volume of payments can get processed in less time.

**How:** Create a power attribute to track the limit.

-   For Attribute Class, select **Limit - Currency**.
    
-   For Applicable Actions, select **ClaimLineItemClaimedAmountEntered**.
    

For each claimed amount, the Claim Coverage Payment Detail record that’s created behind the scenes reflects an Adjusted Amount that accounts for the limit.

When a payment is made, services update term tracking entries to reflect the posted and remaining limit amounts.

## See Also

[Create Power Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_create_power_attributes_604759.htm&language=en_US&type=5 "Use power attributes to track limits, deductibles, copays, coinsurance, and out of pocket maximums. Create power attributes the same way you create regular attributes, in the same attribute categories, and then complete some extra configuration steps.")

Did this article solve your issue?

Let us know so we can improve!

YesNo