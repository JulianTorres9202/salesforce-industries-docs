---
title: "Understand the Census Management Bulk Upload Flow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_census_quote_flow_steps.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Understand the Census Management Bulk Upload Flow

Understand the Census Management Bulk Upload Flow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Understand the Census Management Bulk Upload Flow

Understand the default configuration of Process Group Census Member Data flow and customize it according to your business requirement.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

Typical Steps in the Process Group Census Member Data Flow Workflow
| Step | Label | Element | Description | Purpose | Possible Customization |
| --- | --- | --- | --- | --- | --- |
| 1 | Is Bulk Upload? | Decision | Checks whether group census members are uploaded from a CSV file by evaluating if `asyncBulkRequestItemId` has a value. | Determines whether to process members through bulk upload or through individual Add Member and Update Member services. | Not Recommended |
| 2 | Get Insurance Async Bulk Request Item | Standard Action | Retrieves the insurance async bulk request item record that matches `asyncBulkRequestItemId` and stores the result in a flow variable. | Retrieves content document details and metadata about records to be processed. | Not Recommended |
| 3 | Get Group Census Members | Invocable Action | Retrieves group census member records from the content document of the specified async bulk request item. | Transforms content document data into structured records and fetches duplicate detection keys to determine whether to insert or update. | Not Recommended |
| 4 | Set Group Census Members Variables | Assignment | Assigns values for `groupCensusMembers`, `duplicateDetectionKeys`, and `groupCensusId` from the previous step. | Acts as a preprocessing step for member validation and updates. | Not Recommended |
| 5 | Validate Group Census Members | Invocable Action | Validates group census member records and applies default field values. | Ensures business rules are met. For example, validating group class or member associations and assigns required flow parameters. | Additional business validation steps can be added before or after this step. |
| 6 | Save Group Census Members Data | Invocable Action | Creates or updates group census member records for primary and dependent members. Updates dependent member IDs as needed. | Persists valid records and consolidates error records, which are either saved for later review or returned as action output. | Not Recommended |

Note : Steps 2, 3, and 4 are only needed in case of bulk processing through Bulk Census Management Connect API or through Upload Census action on the Census Management LWC.

Input Parameters
| Parameter Name | Default Value | Required | Description |
| --- | --- | --- | --- |
| asyncBulkRequestItemId | NA | No | The ID of the async bulk request item used to retrieve details of the batch process. This parameter is automatically provided when the flow is invoked through the Bulk Census Management Connect API or the Upload Census action in the Census Management LWC. |
| groupCensusMembers | NA | No | A collection of group census members to add or update in the census. This parameter must be passed by the caller when invoking the flow synchronously. For example, through AddMember/UpdateMember service, LWC, or Apex. |
| duplicateDetectionKeys | NA | No | A comma-separated list of fields used to identify unique group census member records. This parameter must be passed by the caller in synchronous flows when custom duplicate-detection logic is needed. Else, default keys (first name, last name, and association with primary member) are used. |
| operation | NA | No | Specifies the action to perform on group census member records. Valid values: Add or Edit. This parameter must be passed by the caller when invoking the flow synchronously. |
| groupCensusId | NA | No | The ID of the group census associated with the member records. This parameter must be passed by the caller when invoking the flow synchronously. |

Note : asyncBulkRequestItemId is only needed for bulk processing through the Bulk Census Management Connect API or Upload Census action in the Census Management LWC.

Note : groupCensusMembers, duplicateDetectionKeys, operation, and groupCensusId are needed only when the flow is invoked in a synchronous process.

Did this article solve your issue?

Let us know so we can improve!

YesNo