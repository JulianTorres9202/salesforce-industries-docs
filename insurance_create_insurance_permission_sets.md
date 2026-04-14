---
title: "Create Insurance Permission Sets"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_insurance_permission_sets.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Insurance Permission Sets

Create Insurance Permission Sets[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Insurance Permission Sets

Use anonymous Apex to create Insurance Permission Sets.

Note You can create Insurance Permission Sets in the Summer '21 release onward. This step isn't for orgs upgrading to the Spring '21 release.

1.  Click the quick access menu (Setup gear icon), and click **Developer Console**.
2.  From the Debug menu, select **Open Execute Anonymous Window**.
3.  Paste the following code into the **Enter Apex Code** dialog box:
    
    ```
    Map<String, Object> inputs = new Map<String, Object>();
    Map<String, Object> output = new Map<String, Object>();
    Map<String, Object> options = new Map<String, Object>();
    vlocity_ins.VlocityInsUpgradeMethods vium = new vlocity_ins.VlocityInsUpgradeMethods();
    vium.invokeMethod('createInsurancePermissionSets', inputs, output, options);
    ```
    
4.  Click **Execute**.

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)You can now assign these permission sets to your users:

[](https://help.salesforce.com/s?language=en_US)

-   Insurance Create/Update Census Data
    
-   Insurance Create/Update Quote
    
-   Insurance View Census Data
    
-   Insurance View Quote
    

Did this article solve your issue?

Let us know so we can improve!

YesNo