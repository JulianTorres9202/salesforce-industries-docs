---
title: "Add a Claim Participant"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_add_clm_prtpnt.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Add a Claim Participant

Add a Claim Participant[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add a Claim Participant

Add a new participant to a claim by associating them with an account or contact, assigning a role, and linking them to a specific insurance policy.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

1.  From the App Launcher, find and select **Claims**.
2.  Select a claim from the list view.
3.  Navigate to the Participants tab.
4.  Click **Add Participant**. The Claim and Claim Instance Identifier fields are auto-generated but you can override the value while adding the claim participant.
    
    You can add, edit, delete, and customize the fields on this page. See [Manage Fields for a Specific Object](https://help.salesforce.com/s/articleView?id=platform.viewing_fields.htm&language=en_US&type=5).
    
5.  In the Participant Account and Participant Contact fields, search and select a value to associate a Contact or an Account to the participant.
    
    If both an Account and a Contact are associated, the Account record takes priority, and its details are used for the participant's name and contact information.
    
6.  Select **Injured** if the claim participant was injured in the accident.
7.  To assign a role, move the desired values from Available to Chosen by using the arrow buttons.
    
    A claim participant can be assigned more than one role.
    
8.  In the Insurance Policy Participant field, search and select the participant from the policy number that’s associated with the claim. You can refer to the policy number from the details tab of the claim record page.
9.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo