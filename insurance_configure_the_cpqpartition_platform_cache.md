---
title: "Configure the CPQPartition Platform Cache"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_cpqpartition_platform_cache.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the CPQPartition Platform Cache

Configure the CPQPartition Platform Cache[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the CPQPartition Platform Cache

The CPQPartition platform cache can help keep your quoting processes running smoothly. Configure the CPQPartition platform cache to improve performance by caching product and pricing data.

1.  From Setup, in the Quick Find box, enter Platform, and then select **Platform Cache**.
2.  On the Platform Cache Partition page, if the CPQPartition appears in the list, go to step 3. If the CPQPartition doesn't appear in the list, go to [Create a Platform Cache Partition](https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_cpqpartition_platform_cache.htm&language=en_US&type=5 "The Insurance managed package comes with a platform cache partition and you can create a new one if needed.").
3.  Next to CPQPartition, click **Edit**.
4.  In the Session Cache Allocation list, in the Organization box, enter a number between one and five. One is recommended.
5.  In the Org Cache Allocation list, in the Organization box, enter a number between one and five. One is recommended.
6.  Save your changes.
    
    Note Insurance doesn't use CPQ to build its products like some other clouds do, but it does use some basic CPQ functionality to support quoting. Read [Configuring CPQ Platform Cache](https://help.salesforce.com/s/articleView?id=ind.comms_configuring_cpq_platform_cache.htm&language=en_US&type=5) in our Communications cloud documentation to learn more about how the platform cache is used in Industries orgs.
    

-   **[Create the CPQPartition Platform Cache](https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_cpqpartition_platform_cache.htm&language=en_US&type=5)**  
    The Insurance managed package comes with a platform cache partition and you can create a new one if needed.
-   **[Enable the CPQ Cache](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_the_cpq_cache.htm&language=en_US&type=5)**  
    To help your census rating flows run efficiently, enable the CPQ Cache after you enable the CPQPartition platform cache.

Did this article solve your issue?

Let us know so we can improve!

YesNo