---
title: "Group Census Management for Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_census_management_enrollment.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Census Management for Enrollment

Group Census Management for Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Census Management for Enrollment

The census drives enrollment workflows, allowing carriers to capture final primary member and dependent plan and coverage selections into policies.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions of Digital Insurance with Digital Insurance Product Admin Add On, Digital Insurance Group Benefits AddOn, Digital Insurance Group Enrollment AddOn,Digital Insurance Group Benefits Customer Community AddOn, and Digital Insurance Group Benefits Partner Community AddOn licenses</td></tr></tbody></table>

-   [Create a Group Class](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_create_group_class.htm&language=en_US&type=5 "Group classes are groups of members who all receive similar benefits. Examples of group classes include Executives, Managers, and Directors.") - Group classes are groups of members who all receive similar benefits. Examples of group classes include Executives, Managers, and Directors.
-   [Create a Group Census](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_create_group_census.htm&language=en_US&type=5 "Create a group census to capture member and dependent information for quoting, rating, and enrollment.") - Create a group census to capture member and dependent information for quoting, rating, and enrollment.
    
    Note For the Enrollment census type, ensure that a contract is associated where the contract start date and end date is between the effective date and expiration date of the census.
    
-   [Add the Insurance Group Census Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_group_census_lwc.htm&language=en_US&type=5 "The Insurance Group Census Lightning web component gives users a straightforward way to incorporate census data into group census. After a Salesforce admin configures the component and incorporates it into workflows, insurance carrier administrators and brokers upload census data and fix data exceptions.").
-   [Understand the Census Management for Enrollment flow](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_lge_flow_steps.htm&language=en_US&type=5 "Understand the default configuration of Group Enrollment flow and customize it according to your business requirement.").
-   [Upload Group Census](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_upload_group_census_data.htm&language=en_US&type=5 "Use a csv file to upload census information such as group members and dependents into a group census.") - Use a CSV file to upload census information such as group members and dependents into a group census. Keep these additional guidelines in mind when census type is Enrollment:
    -   Have a separate column for each product category. For example, Dental, Medical, and Vision. For members having different root products within the same product category like Dental Gold, Dental Silver, etc, use the same column in the CSV.
    -   The root product name and the coverage name should be the same as the contract group plan name of the contract associated with the census.
    -   The root product and coverage should be eligible for the member based on the group class (if applicable).
    -   The coverages should follow the root product separated by “|” (pipe) operator.
-   [Manage Group Census](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_manage_group_census_data.htm&language=en_US&type=5 "Browse and update information about group members, dependents, and plan selections. The fields you see when adding or editing a member or dependent are based on the default page layout of the Group Census Member object.") - Browse through details about group members, dependents, and plan selections. Add, edit, and delete participant data as needed. You can also configure plans and coverages for enrollment.

-   **[Configure Plans and Coverages for Census Members Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_group_benefits_core_configure_plan.htm&language=en_US&type=5)**  
    Manage plan and coverage selections for primary members and dependents.

Did this article solve your issue?

Let us know so we can improve!

YesNo