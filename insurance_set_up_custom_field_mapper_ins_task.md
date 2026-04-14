---
title: "Set Up Custom Field Mapper for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_custom_field_mapper_ins_task.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Custom Field Mapper for Insurance

Set Up Custom Field Mapper for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Custom Field Mapper for Insurance

To get Quote Line Items to display correctly, download the CustomFieldMap file from Static Resources, then install it as a DataPack.

1.  To get the mappings used by Insurance objects and fields, download and install the CustomFieldMap file.
    1.  From Setup, in the Quick Find box, enter Static Resources and then select **Static Resources**.
    2.  Click **DP\_CUSTOM\_CustomFieldMap**.
    3.  Right-click **View File** and select **Save Link As**.
    4.  Add .JSON as an extension to the end of the filename suggested. Browse to a place on your local computer where you can find the file again easily, and then click **Save**.
    5.  Back in your org, from the App Launcher, find and select **OmniStudio DataPacks**.
    6.  Click the **Installed** tab.
    7.  Click **Import From**, and then select **From File**.
    8.  Click **Browse**, then navigate to the DP\_CUSTOM\_CustomFieldMap.JSON file on your local computer.
    9.  Click **Open**, and then click **Next**.
    10.  In the **Select Items to Import** window, make sure all the items are selected, and then click **Next**.
    11.  Click **Next** again. When the import is complete, click **Done**.
2.  Verify the custom field mappings for the Quote Line Item object.
    1.  From the App Launcher, find and select **Field Mapper**.
    2.  In **Source Object**, select **Product<Product2>**.
    3.  In **Destination Object**, select **Quote Line Item<QuoteLineItem>**.
    4.  Click **Load Settings**.
    5.  Verify the mapped fields listed in the **Fields Map**.
3.  Verify and add to the mapping of other fields.
    1.  From the App Launcher, find and select **Field Mapper**.
    2.  From the **Source Object** dropdown menu, select a **Source Object** listed in the table below.
    3.  From the **Destination Object** dropdown menu, select the corresponding **Destination Object** listed in the table.
    4.  Click **Load Settings**.
    5.  Verify the mapped fields listed in the **Fields Map**, and add other custom field mappings as needed.
        
        | 
        Source Object
        
         | 
        
        Destination Object
        
         |
        | --- | --- |
        | 
        
        Product<Product2>
        
         | 
        
        Quote Line Item<QuoteLineItem>
        
         |
        | 
        
        Contract<Contract>
        
         | 
        
        Quote<Quote>
        
         |
        | 
        
        Census Member<GroupCensusMember\_\_c>
        
         | 
        
        Contact<Contact>
        
         |
        | 
        
        Quote<Quote>
        
         | 
        
        Asset<Asset>
        
         |
        | 
        
        Asset<Asset>
        
         | 
        
        Quote<Quote>
        
         |
        

Did this article solve your issue?

Let us know so we can improve!

YesNo