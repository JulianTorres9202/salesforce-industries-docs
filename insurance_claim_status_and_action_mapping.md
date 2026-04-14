---
title: "Configurable Status to Action Mapping for Claim Payments"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_status_and_action_mapping.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configurable Status to Action Mapping for Claim Payments

Configurable Status to Action Mapping for Claim Payments[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configurable Status to Action Mapping for Claim Payments

Claim admins manage business-specific claim workflows by mapping org specific dynamic Claim Coverage Payment Detail (CCPD) statuses to non-configurable CCPD static enums and configuring allowed actions accordingly.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

This setup enables claim adjusters to perform context-aware actions on financial items. Admins map dynamic picklist values of Claim Coverage Payment Detail Status to static enum values such as Draft, Paid, Canceled, and Deleted. They enable logic-driven actions such as Pay and Cancel that depend on a standardized, static Payment Status, regardless of custom dynamic values. The system supports configurable business actions, including standard ones such as Pay and Delete, as well as custom flow-based actions tailored to customer needs. This approach provides a flexible, low-code setup for mapping and future-proofing claim workflows without hardcoding logic.

Admins can map multiple dynamic enums to a single static enum-based status and set one value as the default. This mapping enables the system to use the dynamic status to drive both UI and API behavior. Admins can also configure actions for a given status. By linking a flow to a dynamic status value, the flow appears as an action in the UI for any record with that status.

-   **[Configure Static to Dynamic Status Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_create_status_action_mapping.htm&language=en_US&type=5)**  
    Map predefined static values for the status of a claim coverage payment detail record to dynamic values based on your organization’s needs. Make sure that you map at least one dynamic value for each static value.
-   **[Edit Static to Dynamic Status Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_edit_st_mapping.htm&language=en_US&type=5)**  
    You can add a new dynamic value to an already mapped static value or change the default dynamic status value.
-   **[Configure Manageable Actions](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_configure_manageable_actions.htm&language=en_US&type=5)**  
    Configure the actions that an adjuster can take based on the payment status of a claim coverage payment detail record. For example, enable the Edit, Pay, Delete, and Pay Ex Gratia actions when the payment status is Draft. Some statuses have preconfigured default actions. For example, the Paid status has a default Cancel Payment action.

Did this article solve your issue?

Let us know so we can improve!

YesNo