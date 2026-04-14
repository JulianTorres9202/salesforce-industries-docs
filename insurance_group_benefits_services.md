---
title: "Group Benefits Services"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_services.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Benefits Services

Group Benefits Services[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Benefits Services

Services are methods of Apex classes that carry out common actions for insurance companies and health plans. Learn about the services typically used in the end-to-end business processes for Group Benefits.

## Quoting

| Service Class:Method | Description |
| --- | --- |
| [InsCensusServiceStd:addMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addmembers.htm&language=en_US&type=5) | Adds group census members to a group census |
| [InsCensusServiceStd:addPlanSelections](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__addplanselections.htm&language=en_US&type=5) | Creates group census member plan records for existing group census members |
| [InsCensusServiceStd:createContacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createcontacts.htm&language=en_US&type=5) | Creates contact records for group census members |
| [InsCensusServiceStd:createUpdateAccounts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__createaccounts.htm&language=en_US&type=5) | Creates and updates person account records for group census members |
| [InsCensusServiceStd:deleteAllMembers](https://help.salesforce.com/s/articleView?id=ind.Insurance_InsCensusServiceStddeleteAllMembers.htm&language=en_US&type=5) | Deletes primary members, dependents, and associated plans from a group census |
| [InsCensusServiceStd:deleteMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletemembers.htm&language=en_US&type=5) | Deletes primary members and dependents from a group census |
| [InsCensusServiceStd:deleteMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__deletememberswithplans.htm&language=en_US&type=5) | Deletes only the primary members and dependents who are associated with plans from a group census |
| [InsCensusServiceStd:findAccounts](https://help.salesforce.com/s/articleView?id=ind.Insurance_InsCensusServiceStdfindAccounts.htm&language=en_US&type=5) | Searches for existing person accounts |
| [InsCensusServiceStd:findContacts](https://help.salesforce.com/s/articleView?id=ind.Insurance_InsCensusServiceStdfindContacts.htm&language=en_US&type=5) | Searches for existing contacts |
| [InsCensusServiceStd:getFields](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getfields.htm&language=en_US&type=5) | Retrieves field definitions and field API names for group census members and group census member plans |
| [InsCensusServiceStd:getMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmembers.htm&language=en_US&type=5) | Retrieves the list of census members and group census member fields and headers from ​group census member​​ records |
| [InsCensusServiceStd:getMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__getmemberswithplans.htm&language=en_US&type=5) | Retrieves the list of census members for a given census |
| [InsCensusServiceStd:setCensusRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setcensusratingfacts.htm&language=en_US&type=5) | Sets selected attributes on the group census record based on a specified rating fact |
| [InsCensusServiceStd:setMemberRatingFacts](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__setmemberratingfacts.htm&language=en_US&type=5) | Sets selected attributes on the group census member records based on a specified rating fact |
| [InsCensusServiceStd:updateMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatemembers.htm&language=en_US&type=5) | Updates member data in a census |
| [InsCensusServiceStd:updateMembersWithPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestd__updatememberswithplans.htm&language=en_US&type=5) | Adds primary members, their dependents, and their pre-enrolled plan to a group census |

## Contracts

|   |   |
| --- | --- |
| [InsContractServiceStd:createUpdateContract](https://help.salesforce.com/s/articleView?id=ind.insurance_inscontractservicestd__createupdatecontract.htm&language=en_US&type=5) | Creates or updates a contract for the given quote |

## Enrollment

|   |   |
| --- | --- |
| [InsEnrollmentServiceStd:enrollFamily](https://help.salesforce.com/s/articleView?id=ind.insurance_InsEnrollmentServiceStd_enrollFamily.htm&language=en_US&type=5) | Enrolls a primary member and associated dependents into a group plan with selected coverages |
| [InsEnrollmentServiceStd:enrollMembers](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollmembers.htm&language=en_US&type=5) | Enrolls group census members into selected small and medium group plans |
| [InsEnrollmentServiceStd:enrollMembersAsync](https://help.salesforce.com/s/articleView?id=ind.Insurance_InsEnrollmentServiceStdenrollMembersAsync.htm&language=en_US&type=5) | Enrolls group census members into selected large group plans asynchronously |
| [InsEnrollmentServiceStd:enrollNewHires](https://help.salesforce.com/s/articleView?id=ind.Insurance_InsEnrollmentServiceStdenrollNewHires.htm&language=en_US&type=5) | Enrolls new group census members into selected plans in the middle of a contract term |
| [InsEnrollmentServiceStd:enrollPlans](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicestd__enrollplans.htm&language=en_US&type=5) | Creates insurance policy records for a census group member's selected plans |
| [InsEnrollmentServiceStd:getMemberEnrollments](https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentservicegetmemberenrollmentsstd_632876.htm&language=en_US&type=5) | Retrieves enrolled plans for a group census member and their dependents |
| [InsEnrollmentServiceStd:getPolicyDetails](https://help.salesforce.com/s/articleView?id=ind.Insurance_InsEnrollmentServiceStdgetPolicyDetails.htm&language=en_US&type=5) | Retrieves insurance policy records for primary group census members |
| [InsEnrollmentServiceStd:getRatedGroupProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insEnrollmentServiceStd_getRatedGroupproducts.htm&language=en_US&type=5) | Calculates the price of a root plan with coverages for a family, accounting for the employee contribution, the employer contribution, and proration for new hires |

Did this article solve your issue?

Let us know so we can improve!

YesNo