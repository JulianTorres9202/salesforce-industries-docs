---
title: "Add Custom Setting Values to Enable Platform Cache"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_custom_setting_values_to_enable_platform_cache.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Custom Setting Values to Enable Platform Cache

Add Custom Setting Values to Enable Platform Cache[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Custom Setting Values to Enable Platform Cache

To enable caching, you must first enable the platform cache in your org. Allocate a minimum of 5 MB of cache space to Organization Level Cache.

[](https://help.salesforce.com/s?language=en_US)Note

Don't enable the platform cache in any of your development environments. It is intended to speed performance in production and performance test environments. It can cause problems when you're actively developing in Vlocity.

1.  Enable the Platform Cache for Product Attributes
    1.  From **Setup**, in the **Quick Find** box, enter Custom Settings, and then select **Custom Settings**.
    2.  Click **Manage** next to **CPQ Configuration Setup**, and then click **New**.
    3.  For **Name**, enter CacheEnabled.
    4.  For **Setup Value**, enter true.
    5.  Save the custom setting.
2.  Enable the Platform Cache for Product Ratings
    1.  From **Setup**, in the **Quick Find** box, enter Custom Settings, and then select **Custom Settings**.
    2.  Click **Manage** next to **General Settings**, and then click **New**.
    3.  For **Name**, enter CalculationProcedureCachePartition.
    4.  For **Value**, enter RatingCache.
    5.  Save the custom setting.
3.  Enable Platform Cache for State Model
    1.  From **Setup**, in the **Quick Find** box, enter Custom Settings, and then select **Custom Settings**.
    2.  Click **Manage** next to **General Settings**, and then click **New**.
    3.  For **Name**, enter StateModelRulesCachePartition.
    4.  For **Value**, enter VlocityMetadata.
    5.  Save the custom setting.

[](https://help.salesforce.com/s?language=en_US)

Head back to the manual post-upgrade steps and complete the next task in the list.

-   **[Caching Mechanisms for BRE and Rating Components](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_cache_and_bre_cache_behavior.htm&language=en_US&type=5)**  
    Expression Sets and Decision Matrices use Salesforce Scale cache automatically and don’t rely on the Platform cache (Rating Cache). Only Calculation Procedures and Calculation Matrices use Platform cache to store rating data.

Did this article solve your issue?

Let us know so we can improve!

YesNo