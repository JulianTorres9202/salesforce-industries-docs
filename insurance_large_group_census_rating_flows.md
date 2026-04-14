---
title: "Large Group Census Rating Flows"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_large_group_census_rating_flows.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Large Group Census Rating Flows

Large Group Census Rating Flows[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Large Group Census Rating Flows

Support asynchronous member-based and summary-based rating with census rating flows.

Use the Rate Plan or Rate All Plans buttons on the Large Group Quote LWC to initiate rating. Before you can use Large Group Census Rating flows in your org, there's some setup to do:

1.  [Configure the Flows](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_census_rating_flows.htm&language=en_US&type=5 "Large group census rating uses two flows: Generate Census Rating and Finish Processing Census Rating. Use these flows as templates by cloning them.")
    1.  [Configure the Generate Census Rating Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_generate_census_rating_flow.htm&language=en_US&type=5 "Use this flow to compile available products for group census members and generate rating processes.")
    2.  [Customize the Generate Census Rating Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_customize_the_generate_census_rating_flow.htm&language=en_US&type=5 "To use the Generate Census Rating flow for large group quoting, add the fields you use for rating to action elements.")
    3.  [Considerations and Guidelines for the Generate Census Rating Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_and_guidelines_for_the_generate_census_rtng_flw.htm&language=en_US&type=5 "After you configure and customize the Generate Census Rating flow, keep this information in mind when using the flow in your org.")
    4.  [Configure the Finish Processing Census Rating Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_finish_processing_census_rating_flow.htm&language=en_US&type=5 "Use this flow to finish processing a rating batch job, update the rating request status, and send a status notification.")
    5.  [Grant Users Access to the Finish Processing Census Rating Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_grant_users_access_to_the_finish_processing_census_rating_flow.htm&language=en_US&type=5 "To perform large group rating processes, users must have access to the Finish Processing Census Rating flow.")
2.  Create the Census Rating Batch Job
    1.  [Create the Member-Based Census Rating Batch Job](https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_member_based_census_rating_batch_job.htm&language=en_US&type=5 "Create and configure a batch job to process member-based census ratings for large group quoting.")
    2.  [Create the Summary-Based Census Rating Batch Job](https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_summary_based_census_rating_batch_job.htm&language=en_US&type=5 "Create and configure a batch job to process summary-based census ratings for large group quoting.")
3.  [Configure the LargeGroupQuoteRatingFlow Custom Setting](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_largegroupquoteratingflow_custom_setting.htm&language=en_US&type=5 "To store the name of the census rating flow for summary census rating scenarios, create a custom setting.")
4.  [Configure the CPQPartition Platform Cache](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_cpqpartition_platform_cache.htm&language=en_US&type=5 "The CPQPartition platform cache can help keep your quoting processes running smoothly. Configure the CPQPartition platform cache to improve performance by caching product and pricing data.")
    1.  [Create the CPQPartition Platform Cache](https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_cpqpartition_platform_cache.htm&language=en_US&type=5 "The Insurance managed package comes with a platform cache partition and you can create a new one if needed.")
    2.  [Enable the CPQ Cache](https://help.salesforce.com/s/articleView?id=ind.insurance_enable_the_cpq_cache.htm&language=en_US&type=5 "To help your census rating flows run efficiently, enable the CPQ Cache after you enable the CPQPartition platform cache.")

Important If you used the Generate Census Rating and Finish Processing Census Rating flows with the Winter ’24 package, you must deactivate these existing flows and configure new versions. To learn how, see [Deactivate the Winter ’24 Census Rating Batch Job and Flows](https://help.salesforce.com/s/articleView?id=ind.insurance_deactivate_the_winter_24_census_rating_batch_job_and_flows.htm&language=en_US&type=5 "We increased the number of plans you can rate at a time with the census rating flows. To continue using the Generate Census Rating and Finish Processing Census Rating flows in your org, you must deactivate the existing batch job and flows and configure the new versions.").

To configure these flows for the first time in an org with the Winter '24 managed package installed, contact your account team for help.

-   **[Deactivate the Winter ’24 Census Rating Batch Job and Flows](https://help.salesforce.com/s/articleView?id=ind.insurance_deactivate_the_winter_24_census_rating_batch_job_and_flows.htm&language=en_US&type=5)**  
    We increased the number of plans you can rate at a time with the census rating flows. To continue using the Generate Census Rating and Finish Processing Census Rating flows in your org, you must deactivate the existing batch job and flows and configure the new versions.
-   **[Configure the Census Rating Flows](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_census_rating_flows.htm&language=en_US&type=5)**  
    Large group census rating uses two flows: Generate Census Rating and Finish Processing Census Rating. Use these flows as templates by cloning them.
-   **[Grant Users Access to the Finish Processing Census Rating Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_grant_users_access_to_the_finish_processing_census_rating_flow.htm&language=en_US&type=5)**  
    To perform large group rating processes, users must have access to the Finish Processing Census Rating flow.
-   **[Create Census Rating Batch Jobs](https://help.salesforce.com/s/articleView?id=ind.insurance_create_census_rating_batch_jobs.htm&language=en_US&type=5)**  
    Create batch jobs to process census rating for large group quoting.
-   **[Configure the LargeGroupQuoteRatingFlow Custom Setting](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_largegroupquoteratingflow_custom_setting.htm&language=en_US&type=5)**  
    To store the name of the census rating flow for summary census rating scenarios, create a custom setting.
-   **[Configure the CPQPartition Platform Cache](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_cpqpartition_platform_cache.htm&language=en_US&type=5)**  
    The CPQPartition platform cache can help keep your quoting processes running smoothly. Configure the CPQPartition platform cache to improve performance by caching product and pricing data.

Did this article solve your issue?

Let us know so we can improve!

YesNo