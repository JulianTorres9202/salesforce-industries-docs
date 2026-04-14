---
title: "Group Enrollment Business Process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_enrollment_business_process.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Enrollment Business Process

Group Enrollment Business Process[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Enrollment Business Process

Upload group benefits product enrollment data with census members and dependents by using the Enrollment Census Lightning web component.

Before you begin:

-   Create a group class.
-   Create group class contribution records.
    
    Only complete this task if you want to specify employer contributions at the member-level in group classes. To learn how, see [Learn About Group Classes and Group Class Contributions](https://help.salesforce.com/s/articleView?id=ind.insurance_get_to_know_about_group_class_and_group_class_contribution_records.htm&language=en_US&type=5 "Group classes are groups of members who all receive similar benefits. Examples of group classes include Executives, Managers, and Directors. Group class contributions have details about the benefits provided by the employer for a group class.").
    
-   Map the group classes with contract group plans in the contract group plan group class object.
    
    Only complete this task if you want to filter plans based on the group class.
    

1.  On the Enroll Members tab on the group account page, upload a census CSV file.
2.  Select an enrollment census path. If there’s already an enrollment census associated with the account, you can either create a new census or retry with the existing census.
    
    If there's already an enrollment census associated with the account, you can either create a new census or retry with the existing census.
    
    Important To prevent creating duplicate policy records, use the retry option if a previous enrollment process failed.
    
    If there isn’t an enrollment census associated with the account, click **Upload CSV** and then select the census CSV file.
    
3.  On the Map Fields screen, map the fields in the uploaded CSV file to the corresponding Group Census Member fields. Map the plan categories fields that specify the plan selection (Vision, Medical, Dental) to the Contract Group Plan ID.
4.  Save the uploaded file.
    
    The census is uploaded and shows census members in an expandable tree view.
    
5.  Edit member information, add a dependent, or view coverages by using the member dropdown menu.
6.  Confirm plan selections for each member, and then click **Enroll**.
    
    A bell notification lets you know when enrollment is complete. If you receive a bell notification alerting you that enrollment couldn't be completed, generate an error CSV file, fix the identified errors, and try again. To learn how, see [Group Enrollment Error Handling](https://help.salesforce.com/s/articleView?id=ind.insurance_group_enrollment_error_handling.htm&language=en_US&type=5 "If you receive a bell notification alerting you that enrollment couldn't be completed, generate an error CSV file, fix the identified errors, and try again.").
    
7.  After enrollment, view policy details on the individual member’s Insurance Policy record.
    
    SEE ALSO
    
    [Group Benefits Bulk Enrollment with Census Management in the Salesforce Data Model](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_bulk_enrollment_with_census_management_in_the_salesforce_data_model.htm&language=en_US&type=5 "The Enrollment Census Lightning web component for the Salesforce data model shows group members, dependents, and plan selections. The hierarchical tree view helps brokers and insurance carrier administrators browse through large, detailed data sets more efficiently.")
    

-   **[Group Enrollment Error Handling](https://help.salesforce.com/s/articleView?id=ind.insurance_group_enrollment_error_handling.htm&language=en_US&type=5)**  
    If you receive a bell notification alerting you that enrollment couldn't be completed, generate an error CSV file, fix the identified errors, and try again.

Did this article solve your issue?

Let us know so we can improve!

YesNo