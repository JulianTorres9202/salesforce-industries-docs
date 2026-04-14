---
title: "Services for Individual Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_services_for_individual_enrollment.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Services for Individual Enrollment

Services for Individual Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Services for Individual Enrollment

Use these services to configure the workflow for individual enrollment, or use custom implementation according to your business requirement.

| Functionality Name | Description | Service To Use |
| --- | --- | --- |
| Get Member Information | Get the existing personal information, selected plans, and coverages of the group census members. | `InsCensusServiceStd.getMembersWithPlans` |
| Get Eligible Plans for Selection | Get the eligible plans for a member based on the contract and the group class assigned to the member. | `InsGroupClassService.GetGroupClassesByContract` |
| Add a Dependent | Add a new dependent to the primary member. | `InsCensusServiceStd.addMembers` |
| Delete a Dependent | Delete any existing dependent member along with the dependent member’s selected plans. | `InsCensusServiceStd.deleteMembersWithPlans` |
| Update Dependent Information | Update the personal information of an existing dependent member. | `InsCensusServiceStd.updateMembersWithPlans` |
| Get Member-level Premium | Rate the selected plan based on the coverage selection for each member along with employee and employer contribution. | `InsEnrollmentServiceStd.getRatedGroupProducts` |
| Save Member Plans and Coverage Selections | 
Add or update the plans selected by the group census members.

Note You must save the plans before calling the enrollment functionality.





 | `InsCensusServiceStd.updateMembersWithPlans` |
| Enroll a Family | Enroll the group census members and associated dependents, and then issue the policy. | `InsEnrollmentServiceStd.enrollFamily` |

Did this article solve your issue?

Let us know so we can improve!

YesNo