---
title: "Deactivate the Winter ’24 Census Rating Batch Job and Flows"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_deactivate_the_winter_24_census_rating_batch_job_and_flows.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Deactivate the Winter ’24 Census Rating Batch Job and Flows

Deactivate the Winter ’24 Census Rating Batch Job and Flows[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Deactivate the Winter ’24 Census Rating Batch Job and Flows

We increased the number of plans you can rate at a time with the census rating flows. To continue using the Generate Census Rating and Finish Processing Census Rating flows in your org, you must deactivate the existing batch job and flows and configure the new versions.

Important This task is required only if you used the Generate Census Rating and Finish Processing Census Rating flows with the Winter ’24 package. Skip this task if you’re using these flows for the first time with the Spring ’24 package.

1.  Deactivate the Census Rating batch job.
    1.  From Setup, in the Quick Find box, enter Batch Management, and then select **Batch Management**.
    2.  Open the Census Rating batch job.
    3.  Click Deactivate.
2.  Deactivate the census rating flows.
    1.  From Setup, in the Quick Find box, enter Flows, and then select **Flows**.
    2.  Open the clone of the Generate Census Rating flow that you created for Winter ’24 in Flow Builder.
    3.  Click **Deactivate**.
    4.  Return to the Flows setup screen.
    5.  Open the clone of the Finish Processing Census Rating flow that you created for Winter ’24 in Flow Builder.
    6.  Click **Deactivate**.

Did this article solve your issue?

Let us know so we can improve!

YesNo