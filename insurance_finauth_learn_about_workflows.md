---
title: "Learn About Financial Authorization Workflows"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_learn_about_workflows.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Learn About Financial Authorization Workflows

Learn About Financial Authorization Workflows[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Learn About Financial Authorization Workflows

Authorization workflows ensure that the financial decisions your team members make align with their skills and experience. Use an authorization workflow to establish financial controls and automatically route requests for financial approval to the appropriate supervisors and managers.

New team members handle smaller, straightforward claims. More senior team members handle the more complex and expensive claims. Keep this in mind when you configure separate limits on how much users can pay or approve for losses, and how much they can pay or approve for expenses. With limits in place, your workflow can efficiently route financial approval requests to users with greater authority.

Pre-configured tools in Insurance give you a head start on a financial authorization workflow.

-   A User Financial Authority user interface lets team leaders define transaction threshold amounts for their team members. This feature uses Salesforce sharing rules.
    
-   Services run for claim financial transactions determine if a user is attempting to exceed their maximum threshold.
    
-   Status values govern financial authority processes.
    
-   Workflows within Salesforce approval processes ensure team leaders don't exceed their own maximum thresholds when they approve financial transactions.
    
-   Salesforce flows govern Approve and Reject actions in approval processes.
    

You're responsible for these parts of the workflow:

-   Understand default status values and make sure your end-to-end process uses status values consistently across custom settings, flows, and services.
    
-   Configure payment processes to run the financial authority service.
    
-   Create your own approval process.
    

Example: Judith is a Claims Adjuster on Stephen's Claims Team. Stephen gives her the authority to pay up to $400 for losses. In his configuration, he doesn't specify a particular product, so Judith's $400 limit applies to losses for coverages on any product.

If Judith attempts to pay one or more payment details all at once, `InsClaimItemService: claimCoverageValuation` makes sure she has the authority to pay all of them given what's already been paid for that coverage. If the total amount Judith's attempting to pay pushes her over the threshold she can pay for a coverage, a warning appears. It lets her know that the payment attempt was unsuccessful, and an approval request is sent to her supervisor.

To keep things simpler for financial authority approvers like Stephen and his manager, only one approval request is generated for a claim at a time.

-   **[Building Blocks of Your Workflow](https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_building_blocks.htm&language=en_US&type=5)**  
    Pre-configured tools in Insurance give you a head start on a financial authorization workflow. These tools drive records through the financial authorization workflow by evaluating whether users have the authority to pay or approve amounts. Based on the results of this evaluation, the tools update status values in claims, claim coverages, and claim coverage payment details.

Did this article solve your issue?

Let us know so we can improve!

YesNo