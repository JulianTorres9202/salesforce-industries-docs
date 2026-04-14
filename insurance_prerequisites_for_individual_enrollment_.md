---
title: "Prerequisites for Individual Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_prerequisites_for_individual_enrollment_.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Prerequisites for Individual Enrollment

Prerequisites for Individual Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Prerequisites for Individual Enrollment

Here are a few mandatory steps to be performed to enable individual enrollment for customers.

-   Create a Person Accounts or Person Contacts for all primary members for whom you want to enable Individual Enrollment.
-   Create Portal Users for all primary members for whom you want to enable Individual Enrollment.
-   Enable permission or sharing settings for member-level record access for group census members and group census member plans.
-   Enable calculation of member-level premium.
    -   You must configure the expression set to populate the member-level premium amount in the **memberPremium** field, and select the **Include in Output** checkbox.
        
    -   You must set the `isSaveMemberPremium` input parameter to `true` for the `InsEnrollmentServiceStd.getRatedGroupProducts` service and `InsEnrollmentServiceStd.enrollfamily` services.
        
-   Ensure your **Rating Procedure Type** field of your product is set to **Expression Set**, and **Rating Procedure Name** field is set to the name of the Expression Set.
-   Associate the Data Mapper bundle to the rating fact product. The Data Mapper must be **OmniDataTransform** type, which is Omnistudio on core object.
    
    Note If you are using a Data Mapper from managed package, use the
    
    [migration tool](https://help.salesforce.com/s/articleView?id=sf.os_migrate_get_ready_authenticate_the_salesforce_command_line.htm&language=en_US&type=5)
    
    to migrate the packaged version Data Mapper to the Omnistudio on core Data Mapper.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo