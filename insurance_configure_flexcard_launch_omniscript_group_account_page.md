---
title: "Configure the FlexCard to Launch New Hire Enrollment OmniScript on Group Account Page"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_flexcard_launch_omniscript_group_account_page.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure the FlexCard to Launch New Hire Enrollment OmniScript on Group Account Page

Configure the FlexCard to Launch New Hire Enrollment OmniScript on Group Account Page[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure the FlexCard to Launch New Hire Enrollment OmniScript on Group Account Page

After you configure the FlexCard to launch the New Hire Enrollment OmniScript on the Group Account page for the new hire enrollment process.

1.  From App Launcher, find and select **Vlocity Cards**.
2.  Click the action menu and then select **Install VlocityInsLwcFlexCards**.
3.  For **Select Items to Import**, click **Select None**, and then select **insMTANewHireBulkEnrollmentCard**.
4.  Click **Next**.
5.  From the App Launcher, find and select **OmniStudio FlexCards**.
6.  Click **insMTANewHireBulkEnrollmentCard**.
7.  Click **Setup** and then click the **Edit** icon for **Enroll\_New\_Hire\_Channel:newHireBulkEnrollment Event Listener**.
8.  For **Listener Properties**, in the **Flyout** field, enter the New Hire Enrollment OmniScript name. Then click **Save**.
9.  Activate the card.
10.  Add the card to the Account page where the Mid-Term Adjustments tab is configured. For **FlexCard Name**, enter insMTANewHireBulkEnrollmentCard.
11.  To launch the New Hire Enrollment OmniScript from the Mid-Term Adjustments tab, click **Bulk Enroll New Hire**.

Did this article solve your issue?

Let us know so we can improve!

YesNo