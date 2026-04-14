---
title: "Configure Renewal Notifications"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_renewal_notifications_510048.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Renewal Notifications

Configure Renewal Notifications[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Renewal Notifications

You can send email notifications for policies that are up for renewal. When sending this email from Salesforce, you can select the organization-wide email address for the email’s **From** field and notifications are sent to email addresses listed in the member's Account record.

1.  Make sure all member Account records are associated with an email.
2.  From Setup, use Quick Find to search for org.
3.  Click **Organization-Wide Addresses**.
4.  Under **User Selectable Organization-Wide Email Addresses**, click **Add**.
5.  Enter the email details and click **Save**.
    
    Important
    
    Make sure you use a valid email address. You receive a verification email at the address and need to take action to complete the process.
    
6.  When the renewal email batch job completes its run, you have the option to get an email notification. To set this up, navigate back to your org, use the App Launcher to open **Vlocity Scheduled Jobs**.
7.  Open **PolicyRenewBatch**.
8.  In **Details**, under **Data Source Settings**, enter the email ID in **Email Address List**. This is the email where you get the completion notifications.
9.  Click **Save**.
10.  To start the batch job scheduler and run it at intervals of 15 minutes, navigate to Setup and click **Developer Console**.
11.  From **Debug**, select **Open Execute Anonymous Window**.
12.  Enter this code and click **Execute**.
     
     ```
     vlocity_ins.VlocityBatchFramework batchFramework = new 
     vlocity_ins.VlocityBatchFramework();
     batchFramework.startBatchScheduler('15 Minutes');
     ```
     

Did this article solve your issue?

Let us know so we can improve!

YesNo