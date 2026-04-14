---
title: "Claim Financials Setup"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_financial_setup.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Claim Financials Setup

Claim Financials Setup[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Claim Financials Setup

Claims admins manage the entire setup process to operationalize the claims financials system.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

1.  **Map payment status:** Claim admins start by mapping the non-configurable CCPD static status to org-specific CCPD dynamic status. This alignment ensures that the correct user interface buttons and API automations are activated at the right times. It enforces both standard and custom actions on the claim financial UI and supports many-to-one mapping, allowing many dynamic enums to map to one static enum. See [Configurable Status to Action Mapping for Claim Payments](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_status_and_action_mapping.htm&language=en_US&type=5 "Claim admins manage business-specific claim workflows by mapping org specific dynamic Claim Coverage Payment Detail (CCPD) statuses to non-configurable CCPD static enums and configuring allowed actions accordingly.").
2.  **Map prebuilt or custom payment details actions:** Next, claim admins map both pre-built and custom payment detail actions to the relevant statuses. These actions include creating, canceling, deleting, and paying claims. In addition, admins can expose custom actions that enforce specific status-based functionalities. See [Configure Manageable Actions](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_configure_manageable_actions.htm&language=en_US&type=5 "Configure the actions that an adjuster can take based on the payment status of a claim coverage payment detail record. For example, enable the Edit, Pay, Delete, and Pay Ex Gratia actions when the payment status is Draft. Some statuses have preconfigured default actions. For example, the Paid status has a default Cancel Payment action.").
3.  **Attribute Scopes for Limit Tracking:** Claim admins then map attribute scopes to policy or coverage attributes. This step is crucial for maintaining accurate balances and ensuring that data is audit-ready. By correctly mapping these attributes, limits and adjustments are posted to the appropriate categories for accurate and compliant financial records. See [Product Attribute Scope Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_prd_att_scope_mapping.htm&language=en_US&type=5 "As a claim admin, you can configure a product with product attribute scopes. These scopes are used to enforce policy limits, such as deductibles, copays, limits, coinsurance, and out-of-pocket max on attributes associated with coverage and root products. These attributes have specific definitions that make sure that the claims management system enforces their policy limit requirements. To use a coverage or root attribute in claims with specific tracking to enforce a policy limit, create it as a record in the Product Attribute Scope entity and add it to either or both the root coverage and policy coverage overrridden attributes. Use the Product Attribute Scope to track the consumption of policy limits, such as deductibles, copays, coinsurance, and out-of-pocket maximums, through a claim for a policy.").
4.  **Extend Limit Tracking Logic:** Finally, admins can extend the limit tracking logic by attaching expression sets or integration procedures. This enables the calculation of adjustments and the processing of limits using custom algorithms. This extension preserves standardized, audit-ready outputs while providing the flexibility to accommodate the organization's unique needs. The result is a no-code configuration that empowers claim adjusters with the right actions, ensuring they can efficiently and accurately manage claims. See [Custom Setup for Calculating Adjustments and Processing Limits](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_logic.htm&language=en_US&type=5 "Insurers can extend or override the default adjustment and limit processing logic based on their specific product configuration, locale-specific compliance needs, or customer specific rules, while maintaining consistency within the core claim adjudication workflow.").

Did this article solve your issue?

Let us know so we can improve!

YesNo