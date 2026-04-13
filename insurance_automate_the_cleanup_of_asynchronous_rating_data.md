---
title: "Automate the Cleanup of Asynchronous Rating Data​"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_automate_the_cleanup_of_asynchronous_rating_data.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Automate the Cleanup of Asynchronous Rating Data​

Automate the Cleanup of Asynchronous Rating Data​[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Automate the Cleanup of Asynchronous Rating Data​

Save time and effort by using custom settings and a scheduled batch job to remove unnecessary large group quoting and enrollment rating data. Choose whether or not to purge data and set the purge frequency as per your business needs. Keep your org running smoothly and reduce manual maintenance with rating data cleanup automation.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package and the Insurance Industries Extension managed package.

**How:** Use the `RatingRetentionDayCount`, `RatingPurgeQueryLimit`, and `RatingPurgeBatchSize` custom settings to specify the rating data purge limits. Then use the `InsRatingRequestPurgeScheduler` batch job to schedule the rating data purge frequency.

## See Also

-   [Large Group Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_large_group_rating.htm&language=en_US&type=5#insurance_large_group_rating "Rating for large groups is based on the rating procedure defined on the plans included in the quote. Rating procedures are created in the Business Rules Engine as Expression Sets.")

Did this article solve your issue?

Let us know so we can improve!

YesNo