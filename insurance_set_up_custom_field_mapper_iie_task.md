---
title: "Set Up Custom Field Mapper for Insurance Industries Extension"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_custom_field_mapper_iie_task.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Custom Field Mapper for Insurance Industries Extension

Set Up Custom Field Mapper for Insurance Industries Extension[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Custom Field Mapper for Insurance Industries Extension

To get Insurance Policy items to display correctly, download the CustomFieldMap file from Static Resources, then install it as a DataPack.

1.  Delete existing Insurance Industries Extension mappings.
    1.  From the App Launcher, find and select **Field Mapper**.
    2.  In **Source Object**, select **Quote<Quote>**.
    3.  In **Destination Object**, select **Insurance Policy<InsurancePolicy>**.
    4.  Click **Load Settings**.
    5.  Select all fields in the **Fields Map** section.
    6.  Click **Delete**.
    7.  Repeat steps 4-6 with **Insurance Policy<InsurancePolicy>** as the Source Object and **Quote<Quote>** as the Destination Object.
2.  Download and install the FSCCustomFieldMap file.
    1.  From Setup, in the Quick Find box, enter Static Resources and then select **Static Resources**.
    2.  Click **DP\_CUSTOM\_FSCCustomFieldMap**.
    3.  Right-click **View File** and select **Save Link As**.
    4.  Add .JSON as an extension to the end of the filename suggested. Browse to a place on your local computer where you can find the file again easily, and then click **Save**.
    5.  Back in your org, from the App Launcher, find and select **OmniStudio DataPacks**.
    6.  Click the **Installed** tab.
    7.  Click **Import From**, and then select **From File**.
    8.  Click **Browse**, then navigate to the DP\_CUSTOM\_FSCCustomFieldMap.JSON file on your local computer.
    9.  Click **Open**, and then click **Next**.
    10.  In the **Select Items to Import** window, make sure all the items are selected, and then click **Next**.
    11.  Click **Next** again. When the import is complete, click **Done**.
3.  Verify the custom field mappings for the Insurance Policy object.
    1.  From the App Launcher, find and select **Field Mapper**.
    2.  In **Source Object**, select **Quote<Quote>**.
    3.  In **Destination Object**, select **Insurance Policy<InsurancePolicy>**.
    4.  Click **Load Settings**.
    5.  Verify the mapped fields listed in the **Fields Map**, and add other custom field mappings as needed.
4.  Verify the custom field mappings for the Quote object.
    1.  From the App Launcher, find and select **Field Mapper**.
    2.  In **Source Object**, select **Insurance Policy<InsurancePolicy>**.
    3.  In **Destination Object**, select **Quote<Quote>**.
    4.  Click **Load Settings**.
    5.  Verify the mapped fields listed in the **Fields Map**, and add other custom field mappings as needed.

Did this article solve your issue?

Let us know so we can improve!

YesNo