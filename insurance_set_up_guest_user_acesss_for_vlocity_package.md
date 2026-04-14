---
title: "Set Up Guest User Access for the Vlocity Package"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_guest_user_acesss_for_vlocity_package.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Guest User Access for the Vlocity Package

Set Up Guest User Access for the Vlocity Package

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

[](https://help.salesforce.com/s?language=en_US)

# Set Up Guest User Access for the Vlocity Package

Allow unauthenticated users to create and price quotes using the Vlocity package by assigning the necessary permission set licenses, permission sets, and object-level read access.

[](https://help.salesforce.com/s?language=en_US)

## Assign Permissions to the Guest User Profile

Provide guest users with appropriate permission set licenses and permission sets based on your package (FSC or Health Cloud).

1.  In Setup, enter digital experiences in the Quick Find box and select **All Sites**.
2.  Next to the site that you want to access, click **Builder**.
3.  In Experience Builder, click the General Settings icon and select **General**.
4.  Under Guest User Profile, click the profile name.
5.  Assign these permission set licenses.
    -   For Financial Services Cloud (FSC) users, assign Insurance Policy Administration Full Edition Package.
    -   For Health Cloud users, assign Health Individual Sales and Administration Package.
6.  Assign these permission sets to the guest user.
    -   For both Financial Services Cloud (FSC) and Health Cloud users, assign Rule Engine Runtime, Insurance Self Quoting, Insurance View Quote, and OmniStudio User RO.
    -   For Financial Services Cloud (FSC) users, assign Insurance Policy Admin Quoting Package.
    -   For Health Cloud users, assign Health Individual Sales and Administration Package.

[](https://help.salesforce.com/s?language=en_US)

## Create and Assign a Custom Permission Set to the Guest User Profile

Provide read-only access to required objects and fields by creating a custom permission set and assigning it to the guest user.

1.  From Setup, in the Quick Find box, find and select **Permission Sets**.
2.  Click **New** to create a new permission set.
3.  Provide a label to your permission set and click **Save**.
4.  In the Permission Set Overview, click **Object Settings**.
5.  Grant read access in Object Permissions and Field Permissions for these objects:
    
    | Object Name | api name |
    | --- | --- |
    | Accounts | Account |
    | Contacts | Contact |
    | Opportunities | Opportunity |
    | Price Books | Pricebook2 |
    | Products | Product2 |
    | Quotes | Quote |
    | Vlocity Attributes | vlocity\_ins\_\_Attribute\_\_c |
    | Vlocity Attribute Assignment Rules | vlocity\_ins\_\_AttributeAssignmentRule\_\_c |
    | Vlocity Attribute Categories | vlocity\_ins\_\_AttributeCategory\_\_c |
    | ProductAttributes | vlocity\_ins\_\_CachedPriceBookEntryAttributeValue\_\_c |
    | Vlocity Calculation Matrices | vlocity\_ins\_\_CalculationMatrix\_\_c |
    | Vlocity Calculation Matrix Columns | vlocity\_ins\_\_CalculationMatrixColumn\_\_c |
    | Vlocity Calculation Matrix Dimensions | vlocity\_ins\_\_CalculationMatrixDimension\_\_c |
    | Vlocity Calculation Matrix Rows | vlocity\_ins\_\_CalculationMatrixRow\_\_c |
    | Vlocity Calculation Matrix Versions | vlocity\_ins\_\_CalculationMatrixVersion\_\_c |
    | Vlocity Calculation Procedures | vlocity\_ins\_\_CalculationProcedure\_\_c |
    | Vlocity Calculation Procedure Step | vlocity\_ins\_\_CalculationProcedureStep\_\_c |
    | Vlocity Calculation Procedure Variables | vlocity\_ins\_\_CalculationProcedureVariable\_\_c |
    | Vlocity Calculation Procedure Versions | vlocity\_ins\_\_CalculationProcedureVersion\_\_c |
    | Vlocity Data Mapper Bundles | vlocity\_ins\_\_DRBundle\_\_c |
    | Vlocity Data Mapper Map Items | vlocity\_ins\_\_DRMapItem\_\_c |
    | Product Attribute Interface | vlocity\_ins\_\_Interface\_ProductAttribute\_\_c |
    | Vlocity OmniScripts | vlocity\_ins\_\_OmniScript\_\_c |
    | Vlocity OmniScript Compiled Definitions | vlocity\_ins\_\_OmniScriptDefinition\_\_c |
    | Saved OmniScripts | vlocity\_ins\_\_OmniScriptInstance\_\_c |
    | Product Override Definitions | vlocity\_ins\_\_OverrideDefinition\_\_c |
    | Taxes and Fees | vlocity\_ins\_\_PriceList\_\_c |
    | Product Taxes and Fees | vlocity\_ins\_\_PriceListEntry\_\_c |
    | ProductAttribXNs | vlocity\_ins\_\_ProductAttribXN\_\_c |
    | Product Child Items | vlocity\_ins\_\_ProductChildItem\_\_c |
    | Product Relationships | vlocity\_ins\_\_ProductRelationship\_\_c |
    | Product Relationship Types | vlocity\_ins\_\_ProductRelationshipType\_\_c |
    | Product Requirements | vlocity\_ins\_\_ProductRequirement\_\_c |
    | Quote Line Item Pricing Adjustments | vlocity\_ins\_\_QuoteLineItemPricingAdjustment\_\_c |
    
6.  Assign the new permission set to the guest user.
    
    Avoid granting access to insurance policy or claim objects to ensure guest users can't create policies or claims.
    

[](https://help.salesforce.com/s?language=en_US)

## Configure Guest User Sharing Settings

Grant record-level access to guest users by configuring guest user sharing settings.

1.  From Setup, in the Quick Find box, find and select **Sharing Settings**.
2.  To grant record-level access for the selected objects, [define guest user sharing settings](https://help.salesforce.com/s/articleView?id=platform.security_sharing_rules_guest.htm&language=en_US&type=5).
3.  Grant read-only access level for the Attribute Assignment and Compiled Attribute Override objects.
4.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo