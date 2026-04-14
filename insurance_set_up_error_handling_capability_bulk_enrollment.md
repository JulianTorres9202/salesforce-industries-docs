---
title: "Set up Error Handling for Bulk Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_error_handling_capability_bulk_enrollment.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set up Error Handling for Bulk Enrollment

Set up Error Handling for Bulk Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set up Error Handling for Bulk Enrollment

Get notified if any errors occur during a CSV file upload and when completed asynchronous jobs identify missing or incomplete data.

[](https://help.salesforce.com/s?language=en_US)

-   On the Insurance Contract object, create a custom field to use as a lookup for Insurance Async Bulk Request. The field stores the `asyncBulkRequestId` when the enrollment process starts using the `enrollMembersAsync` service.
    
    [](https://help.salesforce.com/s?language=en_US)Note Use this custom field only for error handling.
    
-   Ensure your **Rating Procedure Type** field of your product is set to **Expression Set**, and **Rating Procedure Name** field is set to the name of the Expression Set.
    
-   Associate the Data Mapper bundle to the rating fact product. The Data Mapper must be **OmniDataTransform** type, which is Omnistudio on core object.
    
    [](https://help.salesforce.com/s?language=en_US)Note If you are using a Data Mapper from managed package, use the
    
    [migration tool](https://help.salesforce.com/s/articleView?id=sf.os_migrate_get_ready_authenticate_the_salesforce_command_line.htm&language=en_US&type=5)
    
    to migrate the packaged version Data Mapper to the Omnistudio on core Data Mapper.
    

1.  From the Setup menu, click **Developer Console**.
2.  Create an **InsBatchFailureService** Apex Class. Copy and paste the Apex code provided in the LargeGroupEnrollment\_Artifacts file to this Apex Class.
    
    Important If you’ve configured the `InsBatchFailureService` Apex Class with Winter’ 24 package, replace it with the updated class provided in the LargeGroupEnrollment\_Artifacts file. Ensure the API version of the batch class is 60 or above.
    
3.  In the code, replace **vlocityins10\_\_InsuranceAsyncBulkRequest\_\_c** with the custom field name created above, and save the Apex Class.
4.  From the App Launcher, find and select **OmniStudio FlexCards**.
5.  Click **Import** and upload the `GenerateFailureErrorBatch.json` file provided in the LargeGroupEnrollment\_Artifacts file.
6.  Open the FlexCard and make sure it's activated and deployed.
7.  On the group Account page, click the **Gear** icon and select **Edit Page**.
8.  In Lightning App Builder, add a custom tab, and then and then drag and drop the FlexCard component on it. Then, select the FlexCard that's activated in step 6.

Did this article solve your issue?

Let us know so we can improve!

YesNo