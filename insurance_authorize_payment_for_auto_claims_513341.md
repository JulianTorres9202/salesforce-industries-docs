---
title: "Authorize Payment for Auto Claims"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_authorize_payment_for_auto_claims_513341.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Authorize Payment for Auto Claims

Authorize Payment for Auto Claims[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Authorize Payment for Auto Claims

Claim approvers, claim handlers, and claim adjusters are all assigned a maximum limit that they can authorize a claim payment for. If the claim amount is over the authorized limit for a particular role, the claim needs to be approved by a claim manager before it can be paid. A guided OmniScript flow simplifies this approval process.

[](https://help.salesforce.com/s?language=en_US)

1.  Navigate to the **Financials** tab of the claim record.
2.  You can now create either a new loss item or a new expense item. For this example, we're creating a new loss item. Click **New Loss Item**.
3.  Select the coverages for the item.
4.  Enter details for the coverage and click **Add**.
    
    The Adjusted Amount here is automatically calculated by the workflow.
    
5.  To individually pay an item, click **Pay** on the loss item.
6.  To pay multiple items at once, select them and choose Pay from the drop-down.
    
    Any amount that exceeds the user's authority is sent for approval and the status is changed to Pending Authority. The approver receives an email with a link to approve this claim item. They are navigated to a page that lets them approve, deny, or reassign the request.
    
7.  After approval, the status changes to Authority Approved. Now click **Pay**.
    
    The status changes to paid.
    

-   **[How Does Authorize Payment for Auto Claims Work](https://help.salesforce.com/s/articleView?id=ind.insurance_how_does_authorize_payment_for_auto_claims_work.htm&language=en_US&type=5)**  
    The claim recovery workflow runs using the claim covergae Integration Procedure. You can find this Integration Procedure in OmniStudio Integration Procedure under:

Did this article solve your issue?

Let us know so we can improve!

YesNo