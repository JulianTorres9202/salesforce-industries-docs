---
title: "Create the Member-Based Census Rating Batch Job"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_the_member_based_census_rating_batch_job.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create the Member-Based Census Rating Batch Job

Create the Member-Based Census Rating Batch Job[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create the Member-Based Census Rating Batch Job

Create and configure a batch job to process member-based census ratings for large group quoting.

1.  From Setup, in the Quick Find box, enter Batch Management, and then select **Batch Management**.
2.  Click **New**. Enter these values:
    
    | Field | Value |
    | --- | --- |
    | Name | Member-Based Census Rating |
    | API Name | MemberBasedCensusRating |
    | Description | Performs member-based census rating. |
    | Process Type | Flow |
    | Execution Process | The flow you configured in [Configure the Generate Census Rating Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_generate_census_rating_flow.htm&language=en_US&type=5 "Use this flow to compile available products for group census members and generate rating processes."). |
    | Group | Insurance |
    | Batch Size | 200 |
    | Retry Count | 1 |
    | Retry Interval | 1,000 |
    
    Important Use these exact values.
    
3.  Click **Next**, and then enter these values:
    
    | Field |   | Value |   |
    | --- | --- | --- | --- |
    | Flow Input Variable | groupCensusMemberId |
    | Object | Group Census Member |
    | Conditions |
    | Select Records When | **All Conditions Are Met (AND)** |
    | Resource: Group Census ID | Operator: Equals | Type: Input Variable | Value: groupCensusId |
    | Resource: Relationship to Primary Member | Operator: Equals | Type: Value | Value: Self |
    
    Tip Create a **New Input Variable** for groupCensusId.
    
4.  Save and activate the batch job.
    
    SEE ALSO
    
    [Batch Management](https://help.salesforce.com/s/articleView?id=ind.concept_batch_management.htm&language=en_US&type=5)
    

Did this article solve your issue?

Let us know so we can improve!

YesNo