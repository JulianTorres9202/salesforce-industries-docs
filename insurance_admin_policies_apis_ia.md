---
title: "APIs and Invocable Actions in Insurance Policy Administration"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_policies_apis_ia.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# APIs and Invocable Actions in Insurance Policy Administration

APIs and Invocable Actions in Insurance Policy Administration[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# APIs and Invocable Actions in Insurance Policy Administration

Enhance your insurance policy administration with policy APIs and invocable actions. These APIs integrate seamlessly with Omniscripts to help you efficiently manage policy data. Use the invocable actions in Salesforce flows to manage policies. An Insurance Policy Transaction record is created, categorizing the transaction for the insurance policy. Premium amounts and taxes are prorated based on the effective dates, if applicable. Tax details are stored in the InsurancePolicySurcharge object.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions with the DigitalInsuranceProductAdministrationAddOn, DigitalInsurancePolicyAdministrationAddOn, DigitalInsuranceProductRuntimeCCAddOn, and DigitalInsuranceProductRuntimePCAddOn licenses.</td></tr></tbody></table>

[](https://help.salesforce.com/s?language=en_US)

## APIs

[](https://help.salesforce.com/s?language=en_US)

Issue Insurance Policy

This API takes the context ID provided in the input JSON to generate a new insurance policy. You can also include optional fields and additional information in the input JSON. The API then returns the new policy ID in the output JSON.

Endorse Insurance Policy

This API takes the context ID and effective date of endorsement from the input JSON to endorse the latest version of the insurance policy. You can also include other optional fields and additional details in the input JSON. The API then returns the ID of the endorsed policy version in the output JSON.

Renew Insurance Policy

This API uses the context ID of an existing policy to generate a renewal policy. You can modify the renewal date and also add optional fields and additional information in the input JSON. The API then returns the renewed policy ID in the output JSON.

Cancel Insurance Policy

This API takes the effective date of cancellation from the input JSON to cancel the insurance policy versions. You can advance the cancellation date within the policy term, but you can’t postpone the cancellation.

Get Insurance Policy Details

This API returns the ID of the context or JSON with Insurance Policy details. This includes related assets, participants, and coverages. You can use query parameters to request additional information.

[](https://help.salesforce.com/s?language=en_US)

## Invocable Actions

[](https://help.salesforce.com/s?language=en_US)

Issue Insurance Policy

This action issues an insurance policy by using a set of user inputs that represent policy details.

Endorse Insurance Policy

This action endorses the latest version of the insurance policy by using a set of user inputs that represent policy details.

Renew Insurance Policy

This action renews an insurance policy by using a set of user inputs that represent policy details.

Cancel Insurance Policy

This action cancels an insurance policy by using a set of user inputs that represent policy details.

Get Insurance Policy

This action gets the details of an insurance policy.

#### See Also

-   [Insurance Policy Connect APIs](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/insurance_policy_business_api_overview.htm)
-   [Insurance Policy Invocable Actions](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/insurance_policy_invocable_actions_parent.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo