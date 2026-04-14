---
title: "Understand Claim Workflow Rules Runtime"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_undrstnd_wrkflw_rules_rntm.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Understand Claim Workflow Rules Runtime

Understand Claim Workflow Rules Runtime[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Understand Claim Workflow Rules Runtime

The runtime phase is initiated automatically to evaluate a specific claim against the rules configured during design time.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

1.  The process begins when an API call is made to the Rule Evaluation API, specifying the claim and the rule to be evaluated.
2.  The API's first step is to call the Context Service to get the context definition of the object (Claim). This service retrieves the complete, hydrated context definition for the claim object, gathering all necessary data points required for evaluation.
3.  The hydrated claim data, along with the rule definition, is passed to the Business Rules Engine (BRE). The BRE performs the core evaluation, comparing the claim's data against the rule's logic and returning an output (e.g. true or false).
4.  Based on the evaluation output from the BRE, the associated actions are enqueued and executed by the Dynamic Revenue Orchestrator (DRO). When a rule condition is evaluated as true or false, specific actions are triggered.

-   **[Example: Claim Transition from Draft to Payment Processing](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_example_clm_transition.htm&language=en_US&type=5)**  
    This example demonstrates how a Product Admin can configure conditions to transition a claim from Draft to either Payment Processing or Under Review.

Did this article solve your issue?

Let us know so we can improve!

YesNo