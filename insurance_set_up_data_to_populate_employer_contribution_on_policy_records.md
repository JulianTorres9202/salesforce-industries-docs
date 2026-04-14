---
title: "Configure Data to Populate Employer Contribution in Policy Records"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_data_to_populate_employer_contribution_on_policy_records.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Data to Populate Employer Contribution in Policy Records

Configure Data to Populate Employer Contribution in Policy Records[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Data to Populate Employer Contribution in Policy Records

Store employer contribution percentages and amounts in the policies created by the enrollment process.

1.  Create group class records for a given Account using the entity layouts.
2.  Create group class contribution records for the group classes.
    
    Note When multiple group class contribution records are created, the enrollment floe uses the record updated most recently to calculate premiums.
    
3.  In the Contract Group Plan Group Class object, link each Group Class Contribution either to a Contract Group Plan, Product, or Group Benefits Product Category .
    
    Note If you provide all three values, the Contract Group Plan is used for calculating the employer contribution amount. If you provide Product and Group Benefits Product Category values, but not Contract Group Plan, then Product is considered for calculation.
    

-   **[Learn About Group Classes and Group Class Contributions](https://help.salesforce.com/s/articleView?id=ind.insurance_get_to_know_about_group_class_and_group_class_contribution_records.htm&language=en_US&type=5)**  
    Group classes are groups of members who all receive similar benefits. Examples of group classes include Executives, Managers, and Directors. Group class contributions have details about the benefits provided by the employer for a group class.
-   **[Fetch Group Class Contribution Records for Premium Calculation](https://help.salesforce.com/s/articleView?id=ind.insurance_fetch_group_class_contribution_record_for_premium_calculation.htm&language=en_US&type=5)**  
    During enrollment, fetch all the valid group class contribution records for the group class associated with each member.

Did this article solve your issue?

Let us know so we can improve!

YesNo