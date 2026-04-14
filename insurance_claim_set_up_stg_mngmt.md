---
title: "Set Up Stage Management"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_set_up_stg_mngmt.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Stage Management

Set Up Stage Management[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Stage Management

Define how a claim progresses through the different stages in your claim process. Create a stage definition for the Claim object and configure stage transitions for each stage.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

Note Before setting up Stage Management, create at least one record type for the Claim object. If you create stage definitions without record types and add record types later, the stage transitions and any rules based on those transitions become invalid.

1.  Enable the Stage Management setting.[](https://help.salesforce.com/s?language=en_US)
    1.  From Setup, in the Quick Find box, find and select **Stage Management**.
    2.  Turn on **Stage Management**.
2.  Create a stage definition.[](https://help.salesforce.com/s?language=en_US)
    1.  From the Stage Management page, click **New**.
    2.  Enter a name for the stage definition.
    3.  In the Reference Object, select **Claim**.
    4.  In the Reference Object Field, select **Status**.
    5.  If needed, select a record type for the Claim object.
    6.  Save the stage definition.
3.  Configure stage transitions to define stage movement for the Claim object. For example, define the stage transition to move the claim from the Submitted stage to the Approved stage and from the Submitted stage to the Rejected stage.[](https://help.salesforce.com/s?language=en_US)
    1.  Click the name of the stage definition to open the definition in the Stage Management console.
    2.  In the Stage Management console, to add a stage transition for the source stage, click **Add Stage Transition**.
    3.  In Transition To, select the target stage.
    4.  Click **Add**.
        
        Add stage transitions for all stages to create a stage transition plan for your business process.
        
4.  Activate the stage definition.

Did this article solve your issue?

Let us know so we can improve!

YesNo