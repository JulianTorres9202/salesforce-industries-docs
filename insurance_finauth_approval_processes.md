---
title: "Create Approval Processes for Financial Authorization Workflows"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_approval_processes.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Approval Processes for Financial Authorization Workflows

Create Approval Processes for Financial Authorization Workflows[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Approval Processes for Financial Authorization Workflows

Create an approval process that routes payment authorization requests to the appropriate manager or supervisor.

To align your approval process with pre-configured tools for financial authorization workflows, have the Approval Action update the field to **Authority Approved**. Have the Rejection Action update the field to **Authority Denied**.

The approval process locks the Claim record until an approver approves or rejects the request. To lock other claim objects during the approval process, use locking statements in Apex.

After an approver acts on a request, claims have a financial authority status of either Authority Approved or Authority Denied only temporarily. These statuses immediately trigger either an Approved flow or a Rejected flow. The flows update claim coverage and claim coverage payment detail records to the correct status. In the approval process, we recommend you configure the Final Approval Action and Final Rejection Action to update the claim's financial authority status back to No Authority Pending. If another approval process kicks off, the claim switches from No Authority Pending back to Pending Authority again.

## See Also

-   [Approval Processes](https://help.salesforce.com/s/articleView?id=platform.what_are_approvals.htm&language=en_US&type=5)
-   [_Developer Guide:_ Locking Statements](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/langcon_apex_locking_statements.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo