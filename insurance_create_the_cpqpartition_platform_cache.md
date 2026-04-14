---
title: "Create the CPQPartition Platform Cache"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_cpqpartition_platform_cache.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create the CPQPartition Platform Cache

Create the CPQPartition Platform Cache[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create the CPQPartition Platform Cache

The Insurance managed package comes with a platform cache partition and you can create a new one if needed.

1.  From Setup, in the Quick Find box, enter Platform, and then select **Platform Cache**.
2.  Click **New Platform Cache Partition**.
3.  On the New Platform Cache Partition page, in the Detail section, enter these details:
    
    | Field | Value |
    | --- | --- |
    | Label | CPQPartition |
    | Name | CPQPartition |
    
4.  In the Session Cache Allocation list, in the Organization box, enter a number between one and five. One is recommended.
5.  In the Org Cache Allocation list, in the Organization box, enter a number between one and the maximum cache allowed on your org.
6.  Save the new Platform Cache Partition.

Did this article solve your issue?

Let us know so we can improve!

YesNo