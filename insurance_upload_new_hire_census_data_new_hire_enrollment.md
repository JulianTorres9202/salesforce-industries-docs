---
title: "Upload New Hire Census Data for Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_upload_new_hire_census_data_new_hire_enrollment.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Upload New Hire Census Data for Enrollment

Upload New Hire Census Data for Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Upload New Hire Census Data for Enrollment

After a contract is in place, upload group benefits product enrollment data with new hire census members and dependents.

1.  From an Account page, click **Bulk Enroll New Hires**.
2.  Click **Upload Census**.
3.  Map fields in the source data to fields in Group Census Member records.
    
    -   The field labels are the same as the column headings in the source file.
        
    -   The field values displayed in the dropdown lists are populated from the Group Census Member object.
        
    
    After mapping fields and clicking **Save,** uploaded census members appear in a hierarchical tree view.
    
4.  Click **Enroll**.
    
    The `InsEnrollmentServiceStd:enrollMembersAsync` service creates policies for new hires and calculates the employer contribution on a prorated basis based on the group class specified for the primary members.
    

During the new hire enrollment process, you may encounter errors during uploading a CSV file or when the asynchronous enrollment jobs are completed. Get notified when the enrollment is completed, and receive a list of errors if enrollment couldn't be completed.

To learn how to handle errors for the new hire enrollment process, see [Error Handling for Bulk Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_error_handling_bulk_enrollment.htm&language=en_US&type=5 "During the bulk enrollment process, errors may occur during a CSV file upload or because of missing or inaccurate data processes by asynchronous enrollment job. Get notified when the enrollment is completed and receive a list of errors if enrollment couldn't be completed.").

Did this article solve your issue?

Let us know so we can improve!

YesNo