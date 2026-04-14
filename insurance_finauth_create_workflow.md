---
title: "Create a Payment Authorization Workflow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_create_workflow.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Payment Authorization Workflow

Create a Payment Authorization Workflow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Payment Authorization Workflow

Configure the building blocks of your business process for financial transaction payment authorization.

-   **[Set Limits on Amounts Users Can Pay and Approve](https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_limits_for_users.htm&language=en_US&type=5)**  
    Limit how much users can pay or approve for each type of financial activity by using User Financial Authority records.
-   **[Create Approval Processes for Financial Authorization Workflows](https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_approval_processes.htm&language=en_US&type=5)**  
    Create an approval process that routes payment authorization requests to the appropriate manager or supervisor.
-   **[Create Flows for Financial Authorization Workflows](https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_flows.htm&language=en_US&type=5)**  
    Create two clones of the **Update Records Based on Their Financial Authority Approval Status** flow. Configure them to take required actions when a user's financial authority is either approved or rejected.
-   **[Check Financial Authority in Claim Payment Processes](https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_claiminitiatepaymentip.htm&language=en_US&type=5)**  
    As part of your financial authorization workflow, configure the Integration Procedure that's specified for the **ClaimInitiatePaymentIP** Insurance Configuration Setup custom setting. This is the same Integration Procedure that's kicked off by `InsClaimItemService: invokeInitiatePaymentIP`.
-   **[Configure Claim Financial Settings](https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_claim_financial_settings.htm&language=en_US&type=5)**  
    Services use Claim Financial Settings to identify which records require financial authorization. Configure them to use **Pending Authority**, **Authority Approved**, and **Authority Denied** status values.

Did this article solve your issue?

Let us know so we can improve!

YesNo