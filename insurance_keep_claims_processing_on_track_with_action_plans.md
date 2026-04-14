---
title: "Keep Claims Processing on Track with Action Plans"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_keep_claims_processing_on_track_with_action_plans.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Keep Claims Processing on Track with Action Plans

Keep Claims Processing on Track with Action Plans[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Keep Claims Processing on Track with Action Plans

Assign tasks and set completion dates to keep your staff focused and your performance goals on target. Action plans associated with a claim assign tasks and deadlines to claim team members based on their role: claim administrator, special investigator, or whoever is the best fit for the task.

1.  Prepare your org for Action Plans.
    
    -   Make sure users have the Action Plans license.
        
    -   Add Action Plans to the Related List on the Claim page layout.
        
    
2.  In Object Manager, for the Claim Team Member object, add picklist values to the Role field.
3.  Create a Claim Team Member record for each member of your team, and assign each team member the correct roles.
4.  Create action plan templates and action plans for claims. For example, create action plans that list the tasks the Claim Owner and Claim Supervisor must complete for a claim.
5.  Add action plans to claims.
    
    Build a flow that retrieves claim `OwnerId` and claim coverage `OwnerId`, and adds these values to `ClaimTeamMember` records. With these identifying values in the `ClaimTeamMember` records, action plans can get attached to particular claims.
    
    You can also add an action plan directly to a claim. On the claim record's related list, in the Action Plans section, click **New Plan**.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo