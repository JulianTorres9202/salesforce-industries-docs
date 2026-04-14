---
title: "Custom Setup for Calculating Adjustments and Processing Limits"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_logic.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Custom Setup for Calculating Adjustments and Processing Limits

Custom Setup for Calculating Adjustments and Processing Limits[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Custom Setup for Calculating Adjustments and Processing Limits

Insurers can extend or override the default adjustment and limit processing logic based on their specific product configuration, locale-specific compliance needs, or customer specific rules, while maintaining consistency within the core claim adjudication workflow.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

The feature promotes efficiency through a low-code configuration, by using Integration Procedures as an orchestration layer to inject external calculations, fetch reference data, or call decision services without changing core product logic. This approach maintains system integrity and tracking, as outputs such as adjusted amounts and limit deductions are properly integrated into standard downstream processes even when custom logic is applied. These processes include insurance policy limit tracking record creation and financial summary calculations.

You can use the payment processing setup to configure the processing logic for claims. You can choose either the prebuilt logic or a custom Integration Procedure to determine how adjustments are calculated or limits are processed.

-   **[Extend the Prebuilt Expression Set to Perform Custom Calculations](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_calc.htm&language=en_US&type=5)**  
    The Calculate Adjustments Prebuilt Expression Set is a customizable algorithm designed to determine how benefit categories such as Deductible, Copay, and Out-of-Pocket Maximum (OOPM) transform a claimed amount into an adjusted amount, while also generating auditable postings such as Insurance Policy Limit Tracking (IPLT) and Claim Coverage Payment Adjustment (CCPA) records. You can copy and change the prebuilt expression set, or create an expression set for specific areas, regions, or networks. You can do this without changing the main APIs.
-   **[Extend the Prebuilt Expression Set to Perform Custom Processing of Limits](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_exp_set_lmts.htm&language=en_US&type=5)**  
    The Processing Limits Expression Set offers powerful extensibility to handle complex payment scenarios while maintaining compliance with carrier-approved policies. By leveraging this flexibility, the system accommodates scenarios where carriers enable payments beyond the sold policy limit under specific tolerances. This extension enables precise control over payment thresholds, ensuring that payments are processed smoothly up to the effective allowance limit while enforcing strict caps beyond it. In addition, it provides robust tracking and tagging mechanisms to monitor consumption beyond the sold limit, supporting transparency, auditability, and regulatory compliance.
-   **[Build Your Expression Set or Version From an Executable Template](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_exp_set.htm&language=en_US&type=5)**  
    An executable template is active, so you can use it as-is in flows or as subexpressions. But you can’t make changes or additions to an executable template. To reuse a template’s components and then build on top of them, or to modify the components, save the template as an expression set or a version of an expression set.
-   **[Simulate and Activate Your Expression Set Version](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_simulate_exp_set.htm&language=en_US&type=5)**  
    After you modify the expressions and activate it for runtime usages, run simulations with default and custom test input variables. If the expression set doesn't work as expected, edit the elements and resimulate. When you're satisfied, activate the expression set version. The expression set version is linked to a context definition. Perform the simulation by using the context mappings available in the context definition.
-   **[Custom Integration Procedures for Adjustment Calculations](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_ip_cal.htm&language=en_US&type=5)**  
    The standard expression set is designed to handle obligations within the Insurance Policy Limit context. There are instances where you need more specialized calculations. When you need to calculate Deductibles, Copays, Coinsurance, or Out-of-Pocket Maximum (OOPM) with custom logic, you can extend the calculation flow by using a custom Integration Procedure (IP).
-   **[Custom Integration Procedures for Processing Limits](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_custom_ip_limits.htm&language=en_US&type=5)**  
    The standard expression set is designed to manage responsibilities within the context of the Insurance Policy Limit. However, there are situations where more specialized calculations are required. In such cases, when you need to process limits by using custom logic, you can enhance the calculation flow by implementing a custom Integration Procedure (IP). This enables a more tailored and precise handling of policy limits.

Did this article solve your issue?

Let us know so we can improve!

YesNo