---
title: "Group Benefits Census Objects in the Salesforce Data Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_census_objects_in_the_salesforce_data_model.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Benefits Census Objects in the Salesforce Data Model

Group Benefits Census Objects in the Salesforce Data Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Benefits Census Objects in the Salesforce Data Model

Group Benefit census objects are the building blocks of census management in the Salesforce data model. Standard objects represent statistics about group members, personal information about members and dependents, and associations between members and group contract plans.

-   Group Census object
    
    Represents a snapshot of statistics about eligible members (employees or members) of a group (employer or association) and their legal dependents. Use this entity in quoting, rating, and the subsequent enrollment process. Child object of employer or group Account.
    
-   Group Census Member object
    
    Represents personal information about a member, for example employee or association member, or their dependents. GroupCensusMember is used to estimate the insurance plan cost for the group. GroupCensusMember is also used in the enrollment process to retrieve the member and dependent details. Child object of GroupCensus.
    
    All employees and their dependents have Group Census Member records. In records that represent a family group, the employee is the primary member of the group. Dependents such as a spouse and children have relationships with the primary member.
    
    Here's an example of a family group:
    
    -   David, the employee, is the primary member.
    -   Christine, a dependent, is David's spouse.
    -   Stephanie, another dependent, is David's child.
    
    Use the **First Name** and **Last Name** fields to store member names. To save the concatenated name, create a custom field. The **Name** field is reserved for Salesforce's use.
    
-   Group Census Member Plan object
    
    Represents the association of GroupCensusMember and ContractGroupPlan. Use this entity when census data includes previous member enrollment plan details and new member plan details. You can populate GroupCensusMemberPlan by reading the enrollment census in the enrollment services before creating insurance policies.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo