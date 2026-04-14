---
title: "Add a Claim Item"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_add_clm_item.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Add a Claim Item

Add a Claim Item[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add a Claim Item

Add a new claim item to an existing participant in a two-step process by providing key details and configuring attributes for the item.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

1.  From the App Launcher, find and select **Claims**.
2.  Select a claim from the list view.
3.  Navigate to the Participants tab.
4.  Click the dropdown menu of the participant that you want to add a claim item for, and select **Add Claim Item**.
    
    The Claim and Claim Instance Identifier fields are auto-generated but you can override the value while adding the claim item.
    
5.  Enter the required details.[](https://help.salesforce.com/s?language=en_US)
    1.  The Claim and Claim Participant fields are automatically filled.
    2.  Enter a name for the claim item (Example: Fracture).
    3.  Select a category (Example: Involved Injury).
    4.  Select a product (Example: Involved Injury or Damaged Property). The product that you select must be a child product of the root product associated with the claim.
    5.  In the Insurance Policy Coverage and Insurance Policy Asset fields, select the coverage and asset that belong to the policy number associated with the claim.
        
        You can refer to the policy number from the details tab of the claim record page.
        
    6.  Click **Next**.
6.  Configure attributes.
    1.  The system loads the attributes associated with the selected product.
    2.  Fill in the attribute fields from the attribute category tabs, as needed.
        
        When a user fills in the attributes associated with the selected product, some fields might be disabled. These are extended attributes that are automatically filled from a related object, such as the participant's contact record. For example, if you select a contact (example: Carol White), the fields such as email, age, and so on are pre-filled from the contact. Attributes that do not have a defined category are grouped under the Other tab.
        
    3.  If the claim item is an asset already insured under a policy, select the existing asset to automatically fill all of its attributes. For example, when you choose an asset (Example: Audi) from the Insured Policy Asset field, the extended attributes are pre-filled from the asset Audi.
7.  Save your changes. The newly created claim item appears under the participant, grouped by its category.

Did this article solve your issue?

Let us know so we can improve!

YesNo