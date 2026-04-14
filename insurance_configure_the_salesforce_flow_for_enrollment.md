---
title: "Configure the Salesforce Flow for Enrollment"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_the_salesforce_flow_for_enrollment.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the Salesforce Flow for Enrollment

Configure the Salesforce Flow for Enrollment[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the Salesforce Flow for Enrollment

Use this flow to enroll group census members and create insurance policies based on their plan selection in the group census member plan.

Note This task is only for configuring the enrollment flow with the Spring ’24 package. To configure this flow for the first time in an org with the Winter '24 managed package installed, contact your account team for help.

1.  From Setup, in the Quick Find box enter Flows, then select **Flows**.
2.  Click **Enrollment Flow**.
3.  If the org doesn't have Person Accounts enabled, remove the **Create Account** Action element, and then add a **Create Contacts from Group Census Members** Action element below the **Get Rating Facts** action. Enter these details, and then click **Done**.
    
    | Field | Value | Toggle to Include |
    | --- | --- | --- |
    | **Label** | Create Contact |   |
    | **API Name** | create\_contacts |   |
    | **Description** | Invocable action to create contacts for the group census member family. |   |
    | Set Input Values for the Selected Action |
    | **Group Census Members** | {!get\_cm\_and\_family} |   |
    | **Matching Keys List** | {!matchingKeysList} |   |
    | **Gender Field Name** | {!genderFieldName} | ✔️ |
    
4.  Click **Save As**. Enter a **Flow Label**, **Flow API Name**, and **Description**.
5.  Save and activate the flow.
6.  Add this flow to the Batch Management configured for large group enrollment.

Did this article solve your issue?

Let us know so we can improve!

YesNo