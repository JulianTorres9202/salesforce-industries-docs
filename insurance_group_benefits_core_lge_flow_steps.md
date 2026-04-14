---
title: "Understand the Enrollment Flow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_lge_flow_steps.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Understand the Enrollment Flow

Understand the Enrollment Flow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Understand the Enrollment Flow

Understand the default configuration of Group Enrollment flow and customize it according to your business requirement.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

Typical Steps in the Process Group Census Member Data Flow Workflow
| Step | Label | Element | Description | Possible Customization |
| --- | --- | --- | --- | --- |
| 1 | Get Group Census Member Plan | Get Records | Retrieves the group census member plan ID for the primary member based on `contractGroupPlanId` and `GroupCensusMemberId`. Needed to check the enrollment status for the member–plan combination. | Not Recommended |
| 2 | Is Enrollment Applicable for Primary Member and Plan? | Decision | Detrmines whether the primary member has subscribed to the root plan and whether enrollment is already completed, ensuring the flow proceeds only if enrollment is pending. | Not Recommended |
| 3 | Get Associated Group Census Members | Get Records | Retrieves dependent members associated with the primary member. Required because a single policy covers the primary member and dependents. | Not Recommended |
| 4 | Is Person Account Enabled | Decision | Checks if Person Accounts are enabled in the org. Policy records must be linked to an Account or Contact. If Person Accounts are enabled, they are preferred. Otherwise, Contacts and the group Account are used. | Not Recommended |
| 5 | Create Contacts and Users from Group Census Members or Group Census | Invocable Action | Creates Contact records and optionally portal Users for members. Contacts uniquely identify members for policy association. Portal Users allow members to access the community portal. | `CreatePortalUsers` flag can be set to False. If True, a `profileId` must be provided. |
| 6 | Create Person Accounts and Users from Group Census Members or Group Census | Invocable Action | Creates Person Account records and optionally portal Users for members. Person Accounts uniquely identify members for policy association. Portal Users allow members to access the community portal. | `CreatePortalUsers` flag can be set to False. If True, a `profileId` must be provided. |
| 7 | Members Rating and Contribution | Invocable Action | Retrieves standard and prorated rates for members and plans, including contributions if requested. Provides premium and contribution details at coverage, member, and plan level. | Effective Date can be customized. |
| 8 | Process Member Enrollment | Invocable Action | Processes members and their selected plans to create policies and related records. Creates insurance policies, coverages, participants, and related objects using plan, attribute, and premium data. | Create related object records to create participant-related objects and duplicate check required to check for duplicate policies. |

Input Parameters
| Parameter name | default value | required | description |
| --- | --- | --- | --- |
| contractGroupPlanId | NA | Yes | The ID of the root contract group plan. Passed by the Bulk Enrollment API when a user clicks Enroll in the Census LWC. |
| groupCensusMemberId | NA | Yes | The ID of the primary group census member in the family to be enrolled. Passed by the Bulk Enrollment API when a user clicks Enroll in the Census LWC. |
| isPersonAccountEnabled | NA | Yes | Boolean value that determines whether to create a Person Account or a Contact. Passed by the Bulk Enrollment API when a user clicks Enroll in the Census LWC. |
| matchingKeysList | NA | No | Comma-separated list of Account or Contact fields used to detect duplicate accounts. Configured by the admin in the flow. |
| contactOrAccountFieldMappings | NA | No | Map of Group Census Member fields to Account or Contact fields. Configured by the admin in the flow. |
| createPortalUsers | True | No | Flag indicating whether to create portal users. Configured by the admin in the flow. |
| profileId | NA | No (Yes, if createPortalUsers is true) | The Profile ID used when creating user records. Configured by the admin in the flow. |
| timezoneSidKey | NA | No | The time zone SID key used when creating user records. Configured by the admin in the flow. |
| localeSidKey | NA | No | The locale SID key used when creating user records. Configured by the admin in the flow. |
| emailEncodingKey | NA | No | The email encoding key for user records (for example, ISO-8859-1 or UTF-8). Configured by the admin in the flow. |
| languageLocaleKey | NA | No | The language locale for user records (for example, `fr` for French, `zh_TW` for Traditional Chinese). Configured by the admin in the flow. |
| personAccountRecordTypeName | NA | No | The record type name to use when creating Person Accounts. Configured by the admin in the flow. |
| createRelatedObjectRecords | False | No | Flag indicating whether to create related records for each Insurance Policy Participant. When true, two related records are created: one linked to the Group Census Member and another linked to either a Person Account or a Contact. Configured by the admin in the flow. |
| effectiveDate | Contract.startDate | No | The date when rating becomes effective. Defaults to the contract start date. Configured by the admin in the flow. |

Did this article solve your issue?

Let us know so we can improve!

YesNo