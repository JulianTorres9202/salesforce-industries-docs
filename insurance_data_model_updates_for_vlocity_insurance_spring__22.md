---
title: "Data Model Updates for Vlocity Insurance Spring '22"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_data_model_updates_for_vlocity_insurance_spring__22.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Vlocity Insurance Spring '22

Data Model Updates for Vlocity Insurance Spring '22[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Vlocity Insurance Spring '22

This section provides a list of new data model objects and enhanced data model objects for this release.

[](https://help.salesforce.com/s?language=en_US)

## New Data Model Object

We added this new object to the data model for this release:

| 
New Data Model Object

 | 

Description

 |
| --- | --- |
| 

Orchestration Item Log

 | 

Represents orchestration item callout attempts. OrchestrationItemLog\_\_b is a large object that includes orchestration item requests and responses.

This object includes the following new fields:

-   Actual Number Of Retries: The number of orchestration retries initiated by the orchestration item.
    
-   Orchestration Item: The orchestration item associated with the orchestration item log.
    
-   Orchestration Item Type: The type of orchestration item. Possible values include Callout, Push Event, Auto Task, Milestone, Manual Task.
    
-   Request: The orchestration item request JSON or XML data.
    
-   Response: The orchestration item response JSON or XML data.
    
-   State: The state of the orchestration item.
    
-   System Interface: The system interface associated with the orchestration item log.
    
-   Timestamp (Completed): The date and time at which the orchestration item was moved to the Completed state.
    
-   Timestamp (Ready): The date and time at which the orchestration item was moved to the Ready state.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Enhanced Data Model Objects

We added fields and made other enhancements to the following objects for this release:

| 
Enhanced Data Model Objects

 | 

Description

 |
| --- | --- |
| 

Async Process

 | 

This object includes the following new fields:

-   Last Step Finish Process Additional Data: The AdditionalData returned by the finishProcess last executed.
    
-   Technical Message: Technical details about the Async Engine execution.
    
-   UUID: Universally unique identifier.
    

 |
| 

Async Process Job

 | 

This object includes the following new field:

[](https://help.salesforce.com/s?language=en_US)

-   Technical Message: Technical details about the Async Engine execution.
    

 |
| 

Async Process Step

 | 

This object includes the following new field:

[](https://help.salesforce.com/s?language=en_US)

-   Technical Message: Technical details about the Async Engine execution.
    

 |
| 

Attribute Assignment

 | 

This object includes the following new field:

-   Override Context: Path and other override information that helps to uniquely identify and match an override Attribute Assignment record while migrating data between orgs using the IDX tool.
    

 |
| 

Cached API Response

 | 

This object includes the following new field:

-   Status: Validity of cache records.
    

 |
| 

Order Group

 | 

This object includes the following new field:

-   Selected Assets Common Configuration: Common configuration JSON object related to selected assets in group members.
    

 |
| 

Order

 | 

This object includes the following new field:

-   Force Supplementals: An internal flag for accepting Order changes after the Point Of No Return (PONR).
    

 |
| 

Quote Group

 | 

This object includes the following new fields:

-   Opportunity Group: Specifies the corresponding Opportunity Group from which this record is created.
    
-   Selected Assets Common Configuration: Specifies the common configuration JSON object related to selected assets in group members.
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo