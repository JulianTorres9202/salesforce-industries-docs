---
title: "Caching Mechanisms for BRE and Rating Components"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rating_cache_and_bre_cache_behavior.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Caching Mechanisms for BRE and Rating Components

Caching Mechanisms for BRE and Rating Components[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Caching Mechanisms for BRE and Rating Components

Expression Sets and Decision Matrices use Salesforce Scale cache automatically and don’t rely on the Platform cache (Rating Cache). Only Calculation Procedures and Calculation Matrices use Platform cache to store rating data.

Expression Sets and Decision Matrices are managed by the Business Rules Engine (BRE) and use Salesforce internal Scale cache for caching metadata and execution results.

They don't use the Platform Cache (Rating cache) configured through Insurance Settings.

-   For Expression Sets and Decision Matrices, use Salesforce Scale cache.
-   For Calculation Procedures and Calculation Matrices, use Platform cache.

You don’t need to turn on or configure Scale Cache. It’s automatically enabled by Salesforce to optimize BRE performance. If you invoke Decision Matrices from Integration Procedures, you won’t see entries in the Platform Cache monitor.

Did this article solve your issue?

Let us know so we can improve!

YesNo