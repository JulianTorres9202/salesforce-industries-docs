---
title: "Group Enrollment Error Handling"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_enrollment_error_handling.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Enrollment Error Handling

Group Enrollment Error Handling[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Enrollment Error Handling

If you receive a bell notification alerting you that enrollment couldn't be completed, generate an error CSV file, fix the identified errors, and try again.

1.  Click **Generate Error CSV** on the Actions tab of the account page.
    
    A CSV file summarizing the errors is created and attached to the account record in the Files section on the Related tab.
    
2.  To view the error, download and review the CSV file.
3.  Resolve the error (or errors) listed on the CSV file.
4.  Follow the enrollment steps in [Group Enrollment Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_group_enrollment_business_process.htm&language=en_US&type=5 "Upload group benefits product enrollment data with census members and dependents by using the Enrollment Census Lightning web component.") using the Retry option to complete enrollment using an existing census.
    
    Important To prevent creating duplicate policy records, use only the retry option if enrollment previously failed.
    
    SEE ALSO
    
    [Error Handling for Bulk Enrollment](https://help.salesforce.com/s/articleView?id=ind.insurance_error_handling_bulk_enrollment.htm&language=en_US&type=5 "During the bulk enrollment process, errors may occur during a CSV file upload or because of missing or inaccurate data processes by asynchronous enrollment job. Get notified when the enrollment is completed and receive a list of errors if enrollment couldn't be completed.")
    
    [Bulk Enrollment Errors](https://help.salesforce.com/s/articleView?id=ind.insurance_common_bulk_enrollment_errors.htm&language=en_US&type=5 "The most common errors in asynchronous census enrollment occur because of incorrect or incomplete input in the census. But flow configuration and exceptions can also cause asynchronous rating errors. The batch job status can help you locate where in the enrollment process an error happened.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo