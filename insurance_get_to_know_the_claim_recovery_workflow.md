---
title: "Get to Know the Claim Recovery Workflow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_get_to_know_the_claim_recovery_workflow.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Get to Know the Claim Recovery Workflow

Get to Know the Claim Recovery Workflow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Get to Know the Claim Recovery Workflow

You can configure business processes to support several different recovery paths.

Team members can:

-   Pursue an estimated recovery amount against a target account.
    
-   Accept a full reimbursement from the target account and finalize the recovery process.
    
-   Accept a partial reimbursement from the target account and write off the rest if pursuing more isn't cost-effective.
    
-   Accept a partial reimbursement from the target account and then pursue an additional amount through a standard process or legal action.
    

The status of each Claim Recovery record reflects the current state of that recovery attempt, such as Accepted Recovery, Accepted with Additional Pursuit, or Recovery Written Off.

Example: A claims agent pursues a $10,000 recovery amount against a third-party at fault for a loss. After a series of recoveries and additional pursuits, the agent accepts $9,000 in reimbursements and writes off the remaining $1,000.

Throughout the recovery effort, Claim Recovery records store each pursued and accepted amount, and the Financial Summary chart on the claim shows pursued and accepted amounts shrinking or growing over time.

| 
Timeline Details

 | 

Claim Recovery Record and Financial Summary

 |
| --- | --- |
| 

[](https://help.salesforce.com/s?language=en_US)Pursue $10,000

 |  |
| 

[](https://help.salesforce.com/s?language=en_US)Receive $6,000

 |  |
| 

Pursue $4,000 more

 |  |
| 

Receive $2,000

 |  |
| 

Pursue $2,000 more

 |  |
| 

[](https://help.salesforce.com/s?language=en_US)Receive $1,000

 |  |
| 

Accept $1,000

[](https://help.salesforce.com/s?language=en_US)Write off $1,000

 |  |

## See Also

[_Financial Services Cloud Developer Guide_: ClaimRecovery](https://developer.salesforce.com/docs/atlas.en-us.financial_services_cloud_object_reference.meta/financial_services_cloud_object_reference/sforce_api_objects_claimrecovery.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo