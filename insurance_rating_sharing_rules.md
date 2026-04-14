---
title: "Create Sharing Rules for Rating Procedure Components"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_rating_sharing_rules.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Sharing Rules for Rating Procedure Components

Create Sharing Rules for Rating Procedure Components[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Sharing Rules for Rating Procedure Components

If you use calculation procedures or expression sets in product ratings, ensure that quoting works for partner users who issue quotes using the Broker Portal. Create sharing rules that give partner users read-only access to the objects used by rating procedures.

For example, set up sharing rules based on record owner or create other types of sharing rules that grant partner users read-only access to:

-   Attribute Assignments
    
-   Vlocity Attribute Category
    
-   Vlocity Calculation Matrices
    
-   Vlocity Calculation Procedures
    
-   Decision Matrices
    
-   Expression Sets
    

1.  From Setup (Setup gear icon), in the Quick Find box, enter Sharing Settings, and then select **Sharing Settings**.
2.  In the **Manage sharing settings for** object list, scroll down and select **Attribute Assignment**.
3.  In the **Attribute Assignment Sharing Rules** related list, click **New**.
4.  Enter the label and rule name. Optionally, enter a description.
5.  Select a rule type, which records to share, and users to share records with.
    
    For example, if you select the **Based on record owner** rule type:
    
    -   For records to be shared, select records owned by members of the Admin role.
        
    -   For users to share with, select all partner users in public groups.
        
    
6.  For Access Level, select **Read Only**.
7.  Click **Save**.
8.  Repeat these steps for **Vlocity Attribute Category**, **Vlocity Calculation Matrix**, **Vlocity Calculation Procedure**, **Decision Matrices**, and **Expression Sets** objects.

Did this article solve your issue?

Let us know so we can improve!

YesNo