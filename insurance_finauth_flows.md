---
title: "Create Flows for Financial Authorization Workflows"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_flows.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Flows for Financial Authorization Workflows

Create Flows for Financial Authorization Workflows[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Flows for Financial Authorization Workflows

Create two clones of the **Update Records Based on Their Financial Authority Approval Status** flow. Configure them to take required actions when a user's financial authority is either approved or rejected.

1.  From Setup, in the Quick Find box, enter Flows, and then select **Flows**.
2.  Click **Update Records Based on Their Financial Authority Approval Status**.
3.  Click **Save As**.
4.  Enter a label and name, and then click **Save**.
5.  In the Start element of one of the cloned flows, specify a set entry condition to launch the flow when a Claim object is updated with a FinancialAuthorityStatus value of Authority Approved.
    
    While you can configure a different value, the pre-configured tools included with Insurance are set up to use **Authority Approved**. It's easiest to use this default value.
    
6.  In the other cloned flow, specify a set entry condition to launch the flow when the FinancialAuthorityStatus value is Authority Denied.
7.  After configuring the cloned flows, activate them.

Did this article solve your issue?

Let us know so we can improve!

YesNo