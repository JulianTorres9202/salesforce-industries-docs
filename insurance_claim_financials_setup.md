---
title: "Claim Financials Component Overview"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_financials_setup.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Claim Financials Component Overview

Claim Financials Component Overview[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Claim Financials Component Overview

The Claim Financials lighting web component (LWC) is the central workspace where claim adjusters manage all financial aspects of a claim. This process starts after the First Notice of Loss (FNOL), after the system has created the foundational claim records, such as coverages, participants, and involved items. This component provides the capabilities needed to evaluate and then settle the claim.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

The Claim Financials LWC features a hierarchical data grid that empowers adjusters to efficiently organize loss and expense data grouped by coverages and claim items. This grid offers robust search, sort, and filtering capabilities, making it easy to find and manage specific information. Adjusters can also perform critical in-context actions directly from the grid, such as initiating payments or managing coverages, streamlining their workflow. The LWC supports comprehensive claim coverage management, enabling users to create and manage loss and expense items under open coverages.

To aid in informed decision-making, the Financial Dashboard provides real-time financial intelligence through visual summaries. This dashboard presents critical data, including insights into policy limits, payment progress, and the overall financial health of claims. Administrators have the flexibility to configure the entire experience, tailoring the layout, data views, and available actions to align with specific business processes.

-   **[Add the Claim Financials Component to the Claim Record Details Page](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_add_claim_financials_component.htm&language=en_US&type=5)**  
    Use Lightning App Builder to add the Claim Participants Lightning web component to the claim record details page.
-   **[Claim Financials Setup and Runtime Experience](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_dynamic_data_capture.htm&language=en_US&type=5)**  
    Use the configuration-driven framework for Claim Coverage Payment Detail (CCPD) forms to tailor the payment details data capture process as per your business needs. Define both the user interface layout and the underlying calculation logic without requiring custom code. The result is a dynamic system that ensures data is captured accurately and efficiently, adapting automatically to the context of the claim.
-   **[Claim Financials Setup](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_financial_setup.htm&language=en_US&type=5)**  
    Claims admins manage the entire setup process to operationalize the claims financials system.
-   **[Configurable Status to Action Mapping for Claim Payments](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_status_and_action_mapping.htm&language=en_US&type=5)**  
    Claim admins manage business-specific claim workflows by mapping org specific dynamic Claim Coverage Payment Detail (CCPD) statuses to non-configurable CCPD static enums and configuring allowed actions accordingly.
-   **[Customize Data Entry with Payment Detail Configuration](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_payment_detail_configuration.htm&language=en_US&type=5)**  
    When a claim adjuster adds a financial item such as a loss or expense, the system needs to identify the form to present and the calculation logic to use. Claim admins can specify this behavior for each product.
-   **[First Notice of Loss](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_fnol.htm&language=en_US&type=5)**  
    When policyholders, brokers, or insurance reps first report a loss to an insurance carrier, they use the First Notice of Loss (FNOL) flow. Insurance carriers set up this FNOL flow by using Omniscripts. Omniscripts provide the interface that policyholders, insurance carrier brokers, or insurance reps use to file a claim. This FNOL flow starts the claims processing and supports the submission of documents to support the claim. On the backend, the flow uses the verifyPolicyCoverage API to confirm if the policyholder has an active coverage on the date of the loss. Then, it uses the createClaim API to create the initial claim record and the updateClaim API to update the claim details with additional information.
-   **[Work with Claim Financials](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_work_clm_fin.htm&language=en_US&type=5)**  
    Claims adjusters can get a quick overview of claims and related tasks, and then dive into the management of individual claims.

Did this article solve your issue?

Let us know so we can improve!

YesNo