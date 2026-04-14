---
title: "Track Policies with Rolling Limits and Deductibles"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_track_policies_with_rolling_limits_and_deductibles.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Track Policies with Rolling Limits and Deductibles

Track Policies with Rolling Limits and Deductibles[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Track Policies with Rolling Limits and Deductibles

Track policies that cap a benefit over rolling time periods. For example, set a limit of two cleanings every 12 months for dental coverage. You can use rolling 12-month limits and deductibles out of the box, and configure additional rolling time periods for any number of days or months. The amount that accumulates toward a limit or deductible on a current policy rolls over into the limit or deductible on a new policy version.

[](https://help.salesforce.com/s?language=en_US)**Where:** Available in Spring '22 and later releases.

**Why:** Limits and deductibles can accumulate beyond the strict boundaries of policy effective dates. Claims adjusters get a clearer picture of policy terms if they reflect the consumption of rolling limits and deductibles.

**How:** In Custom Metadata Types, create Insurance Term Configuration records for the rolling time periods that you use. For example, create a Rolling 24 Month or Rolling 36 Month record.

Then add the Insurance Term Configuration record values to the Vlocity Attribute object's Duration Type picklist.

Users who configure power attributes can then select the rolling time periods.

Did this article solve your issue?

Let us know so we can improve!

YesNo