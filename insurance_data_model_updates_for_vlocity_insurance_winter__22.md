---
title: "Data Model Updates for Vlocity Insurance Winter '22"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_data_model_updates_for_vlocity_insurance_winter__22.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Data Model Updates for Vlocity Insurance Winter '22

Data Model Updates for Vlocity Insurance Winter '22[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Data Model Updates for Vlocity Insurance Winter '22

This section provides a list of new data model objects and enhanced data model objects for this release.

[](https://help.salesforce.com/s?language=en_US)

## New Data Model Objects

We added these objects to the data model for this release:

| 
New Object

 | 

Description

 |
| --- | --- |
| 

Async Process

 | 

Tracks the overall async process details.

This object includes the following fields:

-   Additional Data: Global data used by the custom processes.
    
-   Async Process Steps: Async process details and steps (JSON).
    
-   Current Step Number: The step number, which is about to execute or is in execution for async process request.
    
-   Items to Process List: List of the items to be processed.
    
-   Message: Message related to async process request.
    
-   Reference Id: A Salesforce ID of any object for which async process request started.
    
-   Status: Status of the async process request.
    
-   Step Name: Name of the current step of the async process request.
    
-   Total Number Of Steps: Number of steps to be executed as part of the async process request.
    

 |
| 

Async Process Job

 | 

Tracks the async job details.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Async Process: Lookup to the async process object.
    
-   Async Process Step: Lookup to async process step object.
    
-   Items Processed List: List of the items processed by the async process job.
    
-   Items to Process List: List of the items to be processed by the remaining async job chain.
    
-   Job Id: Queueable process system ID.
    
-   Message: Message related to async process job.
    
-   Status: Status of the async process job.
    
-   Status Code: Status code of the process job.
    
-   Step Progress: The progress of job type.
    

 |
| 

Async Process Step

 | 

Tracks the step process details.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Additional Data: Additional inputs to the execute and finish process.
    
-   Async Process: A lookup relationship to the async process object.
    
-   Items to Process List: List of the items to be processed through the execute and finish process.
    
-   Message: Message related to the async process request.
    
-   Number Of Items Processed The number of items processed currently out of the total number of items.
    
-   Start Process Additional Data: Additional data inputs to the start process.
    
-   Start Process Items to Process List: List of the items to be processed in the start process.
    
-   Status: Status of the async process request.
    
-   Step Configuration: Async process details and steps (JSON).
    
-   Step Number: Step number of the async process step.
    
-   Total Number Of Items To Be Processed: The total number of items to be processed for async process.
    

 |
| 

Async Execute Job

 | 

Controls the creation of queueable jobs.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Additional Data: Additional data for all async job steps (JSON).
    
-   Async Process: ID of the async process record.
    
-   Async Process Step: ID of the async process step record.
    
-   Items To Process List: List of the items to be processed.
    
-   Job Configuration: Job configuration details such as VIP/Apex name and AsyncSetSize.
    

 |
| 

Async Execute Job Update

 | 

Controls the progress of each queueable job.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Async Process: ID of the async process record.
    
-   Async Process Job: ID of the async process job record.
    
-   Async Process Step: ID of the async process step record.
    
-   Number of Items Processed: Number of items processed by the async job.
    
-   Status: Status of the async execute job updates.
    

 |
| 

Async Process Manager

 | 

Controls the progress of the async process steps.

This object includes the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Additional Data: Additional data for all async job steps (JSON).
    
-   Async Process: ID of the async process record.
    
-   Async Process Step: ID of the async process step record.
    
-   Async Process Steps: Async process details and steps definition (JSON).
    
-   Async Step Progress: Controls the async process execution (Step Start Process > Step Finish Process > Step Completed).
    
-   Items To Process List: List of the Items to be processed.
    
-   Status: Status of the async process.
    
-   Step Number: Step number for the event created.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Enhanced Data Model Objects

We added fields and made other enhancements to the following objects for this release:

| 
Enhanced Object

 | 

What's Changed

 |
| --- | --- |
| 

Opportunity Group

 | 

We added the following field:

-   Has Unapplied Members: Indicates if at least one member of the group has no opportunity created.
    

 |
| 

Order Group

 | 

We added the following field:

[](https://help.salesforce.com/s?language=en_US)

-   Has Unapplied Members: Indicates if at least one member of the group has no order created.
    

 |
| 

Quote Group

 | 

We added the following field:

[](https://help.salesforce.com/s?language=en_US)

-   Has Unapplied Members: Indicates if at least one member of the group has no quote created.
    

 |
| 

Orchestration Item

 | 

We added the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Async Response Omni Data Transform Name: Name of the omni data transformation (Load type) for response payload provided by an external system through an asynchronous integration adapter.
    
-   Integration Retry Policy
    
-   Request Items Omni Data Transform Name: Name of the omni data transformation (Transform type) for order and fulfillment request items nodes of the request payload.
    
-   Request Omni Data Transform Name: Name of the omni data transformation (Extract, Turbo Extract, or Transform type) for request payload by an integration adapter.
    
-   Response Attrs Omni Data Transform Name: Name of the omni data transformation (Load type) for attributes of the response payload provided by an external system through an integration adapter.
    
-   Response Items Omni Data Transform Name: Name of the omni data transformation (Load type) for order items node of the response payload provided by an external system through an integration adapter.
    
-   Response Omni Data Transform Name: Name of the omni data transformation (Load type) for response payload provided by an external system through an integration adapter.
    
-   Timestamp (Retry No Earlier Than)
    

 |
| 

Quote

 | 

We added the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Source System
    
-   Source System Identifier
    

 |
| 

Quote Line Item

 | 

We added the following field:

[](https://help.salesforce.com/s?language=en_US)

-   Source System Identifier
    

 |
| 

Orchestration Item Definition

 | 

We added the following fields:

[](https://help.salesforce.com/s?language=en_US)

-   Async Response Omni Data Transform Name: Name of the omni data transformation (Load type) for response payload provided by an external system through an asynchronous integration adapter.
    
-   Request Items Omni Data Transform Name: Name of the omni data transformation (Transform type) for order and fulfillment request items nodes of the request payload.
    
-   Request Omni Data Transform Name: Name of the omni data transformation (Extract, Turbo Extract, or Transform type) for request payload by an integration adapter.
    
-   Response Attrs Omni Data Transform Name: Name of the omni data transformation (Load type) for attributes of the response payload provided by an external system through an integration adapter.
    
-   Response Items Omni Data Transform Name: Name of the omni data transformation (Load type) for order items node of the response payload provided by an external system through an integration adapter.
    
-   Response Omni Data Transform Name: Name of the omni data transformation (Load type) for response payload provided by an external system through an integration adapter.
    

 |
| 

System Interface

 | 

We added the following field:

[](https://help.salesforce.com/s?language=en_US)

-   Status
    

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo