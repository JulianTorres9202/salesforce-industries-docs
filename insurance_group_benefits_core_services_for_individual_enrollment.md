---
title: "Configuration of Individual Enrollment Using APIs and Omnistudio"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_services_for_individual_enrollment.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configuration of Individual Enrollment Using APIs and Omnistudio

Configuration of Individual Enrollment Using APIs and Omnistudio[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configuration of Individual Enrollment Using APIs and Omnistudio

Use these out-of-the-box APIs and Omnistudio to manage members and plans for individual enrollment, or use custom implementation according to your business requirement.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

| Functionality | description | connect api | implementation approach |
| --- | --- | --- | --- |
| Get Census Member Information | Get the primary and dependent member information. | N/A | Integration Procedures (DataRaptors) or Apex |
| Add Dependents | Add a dependent to the primary member | Add Member | Remote Action through OmniScript or Integration Procedures |
| Delete Dependents | Delete an existing dependent member. | Delete Member | Remote Action through OmniScript or Integration Procedures |
| Update Member | Update personal information for an existing dependent member. | Update Member | Remote Action through OmniScript or Integration Procedures |
| Get Eligible Plans for Selection | Get the eligible plans for a member based on the contract and the group class assigned to the member. | Get Eligible Plans | OmniStudio + API |
| Get Selected Plans | Capture and store selected plan information. Plan details are stored and passed for each member. | N/A | OmniStudio components or custom LWC |
| Rules | Apply business rules before adding or updating plans. Displays only coverages relevant to the user. Complements Add, Update, and Delete Plan APIs. | Rules Execution | OmniStudio + API |
| Add Plan | Assign plans to members based on user selections. | Add Member Plan | OmniStudio + API |
| Update Plan | Update existing member plans. Use the Update Plan API or combine Add and Delete APIs. | Update Member Plan | OmniStudio + API |
| Delete Plan | Remove a plan associated with a member. | Delete Member Plan | OmniStudio + API |
| Rating + Employee/Employer Contribution | Perform rating on selected plans. Calculates employee and employer contributions for group and nongroup scenarios. | Individual Enrollment Rating | OmniStudio + API |
| Enroll Family | Enroll a family (primary member and dependents) and issue the policy based on prior selections. | Enroll Family | OmniStudio + API |

Did this article solve your issue?

Let us know so we can improve!

YesNo