---
title: "Give Users Access to Group Benefits in the Salesforce Data Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_give_users_access_to_group_benefits.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Give Users Access to Group Benefits in the Salesforce Data Model

Give Users Access to Group Benefits in the Salesforce Data Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Give Users Access to Group Benefits in the Salesforce Data Model

To use group benefits in the Salesforce data model, check your add-on licenses and permission set license assignments.

Note This topic is intended for users with the Enterprise license model and not the LP-based license model.

1.  Verify required licenses and permission set licenses for group benefits in Financial Services Cloud.
    1.  Confirm that your org includes the Insurance Contract & Enroll SKU, which contains the required Insurance Group Benefits add-on licenses. Note that only group benefits services require the Insurance Contract & Enroll SKU; group benefits objects alone do not require this SKU.
    2.  Verify that users who need access to Group Benefits entities have the Insurance Group Benefits User permission.
    3.  Assign the required permission set licenses to users:
        
        -   Insurance Group Benefits
        -   Insurance Group Benefits Package
        -   Insurance Policy Admin Quoting Package
        -   Insurance Product Catalog Admin Package
        
    4.  If you're upgrading from a managed package license to permission set licenses, confirm that your org includes the following additional add-on licenses:
        
        -   InsuranceGroupBenefitsAddOn
        -   InsuranceGroupBenefitsCCAddOn
        -   InsuranceGroupBenefitsPCAddOn
        -   InsuranceGrpBenDataModelAddOn
        -   InsurancePolicyAdministrationAddOn
        -   InsuranceProductAdministrationAddOn
        
2.  Verify Health Cloud Benefits SKU and Assign Required Licenses.
    1.  In your org, confirm that one of the following base SKUs is provisioned:
        
        -   Benefits Sales & Administration – Group
        -   Benefits Sales & Administration – Individual, Family and Medicare
        
    2.  Assign users the permission set licenses required for your SKU.
        
        If you have Benefits Sales & Administration – Group, assign:
        
        -   Health Group Sales and Administration Package
        -   Insurance Group Benefits
        -   Insurance Policy Administration
        
        If you have Benefits Sales & Administration – Individual, Family and Medicare, assign:
        
        -   Health Individual Sales and Administration Package
        -   Insurance Group Benefits
        -   Insurance Policy Administration
        
    3.  For community users, assign the corresponding Health Cloud community add-on license based on your edition and login model:
        
        -   Customer Community for Health Cloud – EE – Logins (Per Month)
        -   Customer Community for Health Cloud – EE – Members
        -   Customer Community for Health Cloud – PXE – Logins (Per Month)
        -   Customer Community for Health Cloud – PXE – Members
        -   Customer Community for Health Cloud – UE – Logins (Per Month)
        -   Customer Community for Health Cloud – UE – Members
        -   Customer Community Plus for Health Cloud – EE – Logins (Per Month)
        -   Customer Community Plus for Health Cloud – EE – Members
        -   Customer Community Plus for Health Cloud – Logins (Per Month)
        -   Customer Community Plus for Health Cloud – Members
        -   Customer Community Plus for Health Cloud – PXE – Logins (Per Month)
        -   Customer Community Plus for Health Cloud – PXE – Members
        -   Customer Community Plus for Health Cloud – UE – Logins (Per Month)
        -   Customer Community Plus for Health Cloud – UE – Members
        
3.  Grant Data Model Access to Community Profiles. Ensure that the appropriate Customer Community or Partner Community profile includes these permissions so community users can access the Group Benefits data model.
    1.  From Setup, enter Profiles in the Quick Find box and select **Profiles**.
    2.  Open the relevant community profile (for example, Partner Community Login User or the applicable Customer Community profile).
    3.  Click **Edit**.
    4.  In General User Permissions, enable:
        
        -   Insurance Group Benefits User
        -   Access Insurance Objects
        
    5.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo