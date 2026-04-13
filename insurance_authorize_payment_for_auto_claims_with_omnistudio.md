---
title: "Authorize Payment for Auto Claims with OS License"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_authorize_payment_for_auto_claims_with_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Authorize Payment for Auto Claims with OS License

Authorize Payment for Auto Claims with OS License[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Authorize Payment for Auto Claims with OS License

Claim approvers, claim handlers, and claim adjusters are all assigned a maximum limit that they can authorize a claim payment for. If the claim amount is over the authorized limit for a particular role, the claim needs to be approved by a claim manager before it can be paid. A guided OmniScript flow simplifies this approval process.

[](https://help.salesforce.com/s?language=en_US)

1.  Navigate to the **Financials** tab of the claim record.
2.  You can now create either a new loss item or a new expense item.
    
    For this example, we're creating a new loss item. Click **New Loss Item**.
    
3.  Select the coverages for the item.
4.  Enter details for the coverage and click **Add**.
    
    The Adjusted Amount here is automatically calculated by the workflow.
    
5.  To individually pay an item, click **Pay** on the loss item.
6.  To pay multiple items at once, select them and choose Pay from the drop-down.
7.  Any amount that exceeds the user's authority is sent for approval and the status is changed to Pending Authority.
8.  The approver receives an email with a link to approve this claim item. They are navigated to a page that lets them approve, deny, or reassign the request.
9.  After approval, the status changes to Authority Approved. Now click **Pay**.
10.  The status changes to paid.

-   **[How Authorize Payment for Auto Claims Works](https://help.salesforce.com/s/articleView?id=ind.insurance_how_authorize_payment_for_auto_claims_works_omnistudio.htm&language=en_US&type=5)**  
    Understand the workflow for payment authorization, and the levels of claim users and their authorities.

Did this article solve your issue?

Let us know so we can improve!

YesNo