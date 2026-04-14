---
title: "Configure the Bulk Enrollment OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_bulk_enrollment_omniscript.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Bulk Enrollment OmniScript

Configure the Bulk Enrollment OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Bulk Enrollment OmniScript

Customize the OmniScript that guides users through uploading census data for Group Benefits bulk enrollments and that creates the related objects in the Salesforce data model.

1.  From the App Launcher, find and select **OmniScripts**.
2.  Click **Import** and upload the sample `LGE OS.json` file you extracted from the `LargeGroupEnrollment_Artifacts` static resource.
3.  Add the Bulk Enrollment OmniScript with insOsEnrollmentCensus Lightning web component to the account page.
4.  Open the **OmniScript** and reactivate it.
    
    For new hire enrollments, also complete these steps:
    
    1.  In the imported OmniScript, for the upload step that uses insOsEnrollmentCensus LWC, add a **isNewHire** input property and set it to `true`.
    2.  In the step that calls the Integration Procedure after the census upload, there's a remote action to call the `InsEnrollmentServiceStd:enrollMembersAsync`. For that remote action, add a **isNewHire** remote action and set it to `true`.
    3.  Reactivate the OmniScript.

-   **[Get to Know the Default Configuration and Possible Customization for Bulk Enrollment OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_get_to_know_the_default_configuration_and_possible_customization_for_bulk_enrollment_os.htm&language=en_US&type=5)**  
    Understand the default configuration of bulk enrollment OmniScript and customize it according to your business requirement.

Did this article solve your issue?

Let us know so we can improve!

YesNo