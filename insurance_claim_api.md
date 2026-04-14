---
title: "APIs for Insurance Claims Management"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# APIs for Insurance Claims Management

APIs for Insurance Claims Management[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# APIs for Insurance Claims Management

Enhance your insurance claims management with APIs. These APIs integrate seamlessly with Omniscripts to help you efficiently manage claim data.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

-   [Create Policy Limits API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__pollmt)
    
-   [Create Claim API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__createclaim)
    
-   [Update Claim API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__updateclaim)
    
-   [Get Claim API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__getclaim)
    
-   [Verify Claim Coverage API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__vercov)
    
-   [Open Claim Coverage API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__opencov)
    
-   [Update Claim Coverage API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__updatecov)
    
-   [Field Set Fields API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__fieldset)
    
-   [Get Current Standings API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__currstnd)
    
-   [Calculate Adjustments API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__calcadj)
    
-   [Process Policy Limits API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__processlmt)
    
-   [Create Claim Coverage Payment Detail API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__creaetccpd)
    
-   [Cancel Claim Coverage Payment Detail API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__cancelccpd)
    
-   [Delete Claim Coverage Payment Detail API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__deleteccpd)
    
-   [Pay Claim Coverage Payment Detail API](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_api.htm&language=en_US&type=5#insurance_claim_api__payccpd)
    

[](https://help.salesforce.com/s?language=en_US)

## Create Policy Limits API

Use the Create Policy Limits API to define the terms of consumption and track the consumption of each attribute at the policy or policy coverage level by setting policy limits for a specific duration. These limits data is stored in the Product Attribute Scope entity and are mapped to the overridden inherited attributes (Product Attribute Definition) from the product. This mapping is configured at design time in the user interface and stored in the Product Attribute Mapped Scope object, which serves as a junction object between Product Attribute Definition and Product Attribute Scope. A policy created from this product can use this design setup for claims processing.

Tracking the consumption of different limits is managed by two runtime objects. The Insurance Policy Limit entity is a runtime instantiation of the trackable policy consumption limit, such as deductibles, limits, and copays for the policy and its coverages. The Insurance Policy Limit Tracking object stores all the consumption data for an Insurance Policy Limit.

The Create Policy Limits API accepts the policy version ID or an optional request payload containing a list of scopes and outputs the policy limit IDs. Generate the limits when creating the policy, before claim creation, or before running the Get Current Standings API. This step is a prerequisite for claims creation and is recommended to be done during the setup process.

Let’s look at an example for terms of consumption. A policyholder has a health insurance policy that includes dental coverage with a copay of $100. By running the Generate Policy Limits API, you can set a policy limit for this copay attribute with the scope defined as claim. This defines the term for consumption. This means that for each claim made under the dental coverage, the policyholder must pay $100 out of pocket. If the policyholder files a claim for $500, $100 is deducted, and the policyholder receives $400.

Let’s now consider another example where the consumption of the attribute is tracked. The policy holder has an auto insurance policy with a deductible attribute of $1000 configured at the policy root level. By running the Generate Policy Limits API, you can set a policy limit for this deductible attribute with the scope defined as policy. This means that the $1,000 deductible can be applied to one or more claims made under this policy. Each claim's deductible consumption is tracked to ensure accurate adjustments for future claims. If the policyholder files a claim for $500, the entire amount is adjusted and deducted from the deductible, resulting in no payout to the policyholder. The $500 is subtracted from the $1,000 deductible, leaving $500 remaining. When the policyholder files a second claim for $800, the remaining $500 deductible is applied, and the policyholder receives $300 from the insurer. The consumption of the $1,000 deductible across both claims is tracked to ensure the correct adjustment for future claims.

[](https://help.salesforce.com/s?language=en_US)

## Create Claim API

When a customer or insurance rep initiates the First Notice of Loss (FNOL) Claims process, they use the Create Claim API to generate the claim. The API takes the details provided in the input JSON to create a claim, accommodating optional and additional fields. It validates the data, creates the context, and executes the product configuration rules. The API returns either the new claim ID or an error response in the output JSON when any errors occur.

[](https://help.salesforce.com/s?language=en_US)

## Update Claim API

The Update Claim API enhances the claims process by enabling claimants to easily add or modify information for an existing claim. This ensures all necessary details are captured, improving accuracy and reducing errors. It streamlines workflows for claim adjusters, leading to faster resolution times and better decision-making. The Update Claim API updates an existing claim and its related claim items and claim participants by using the details provided in the input JSON. The input JSON can include additional fields. The API validates the data, creates the context, and executes the product configuration rules.

[](https://help.salesforce.com/s?language=en_US)

## Get Claim API

The Get Claim API offers comprehensive visibility into a claim by enabling users to access detailed information about the claim, including associated items, participants, and any relevant updates.

[](https://help.salesforce.com/s?language=en_US)

## Verify Claim Coverage API

The Verify Claim Coverage API validates whether a given policy coverage is applicable on a specified Loss Date (the date of the incident) under a specified insurance policy. In addition, it verifies that the specified policy coverage applies to the provided insured asset or participant. This API plays a crucial role in claim intake and processing, making sure that only valid coverages are considered for claims. By verifying eligibility before initiating the claim process, it helps avoid downstream issues and improves accuracy in determining claim validity. This also reduces the risk of processing claims against inactive or nonapplicable coverages, as well as assets or participants without valid coverage. The API performs checks to ensure coverage validity. It confirms that the insurance policy was active on the date of loss. It also checks that the specified policy coverage belongs to the same policy and was active on the date of loss.

[](https://help.salesforce.com/s?language=en_US)

## Open Claim Coverage API

Claim coverages are opened at the end of the First Notice of Loss (FNOL) flow, making sure that all relevant coverages are initiated based on initial information. For example, in a car accident involving two vehicles, both Collision and Property Damage coverages can automatically be initiated. In addition, claim adjusters can open coverages on existing claims as required. The Open Claim Coverage API uses the details of the input JSON, which includes the claim participant ID, claim item ID, the loss reserve amount, and expense reserve amount. It validates the data and creates the corresponding Claim Coverage, Claim Coverage Reserve Detail, and Claim Coverage Reserve Adjustments records.

[](https://help.salesforce.com/s?language=en_US)

## Update Claim Coverage API

The Update Claim Coverage API uses the details of the input JSON, which includes the loss reserve amount and expense reserve amount to update a claim coverage. It validates the data and updates the corresponding Claim Coverage, Claim Coverage Reserve Detail, and Claim Coverage Reserve Adjustments records.

[](https://help.salesforce.com/s?language=en_US)

## Field Set Fields API

The Field Set Fields API retrieves the complete set of fields that’s associated with a specific field set ID and the corresponding object name. By enabling dynamic retrieval and display of the appropriate fields based on the field set configuration, this API makes sure that the LWC component is always up-to-date with the latest data structure.

[](https://help.salesforce.com/s?language=en_US)

## Get Current Standings API

The Get Current Standings API provides real-time visibility into policy limit consumption, helping claim adjusters make accurate, compliant, and faster claim decisions while staying within coverage limits and financial controls. It calculates the consumption for various policy limits and applies the scopes for the defined duration: policy term, lifetime, calendar year, or a custom override date.

The Get Current Standings API is invoked internally during operations such as adding, editing, or deleting loss items in a claim coverage payment detail record. It's also triggered before payments, during the calculation of adjustments, and when reporting data on the financial dashboard. The API reports consumptions based on the scope, duration, attribute category, participant, and asset. It conducts basic validations and retrieves standings for input parameters such as policy ID, policy coverage ID, claim coverage, claim, policy participant, or policy asset. It calculates consumption, tracks usage, and determines the remaining amounts. Pending payments, representing the total value of loss items yet to be paid, are displayed for reporting purposes on the financial dashboard. The API also monitors the consumption of sublimits. The response from the API includes key financial metrics that are consumed by downstream APIs.

[](https://help.salesforce.com/s?language=en_US)

## Calculate Adjustments API

The Calculate Adjustments API calculates the adjusted amount at runtime by applying necessary deductions based on the attribute category, attribute scope, and duration type. It also considers previous consumptions of the policy. The input parameters for this API are the claimed amount, claim ID, and claim coverage ID. The API invokes the Get Current Standings API to retrieve the current consumption of the policy limits and then computes the adjusted amount.

The API response includes:

-   The adjusted amount and the reason for the adjustment
-   Insurance policy limit tracking (IPLT) and claim coverage payment adjustment (CCPA) data that's persisted by the consuming APIs.

The IPLT and CCPA records are consumed by the create CCPD API to create payment detail records.

The Calculate Adjustment API supports extensibility for calculating the adjusted amount. Admin users can configure custom calculations via an expression set or an integration procedure. The API uses a prebuilt executable expression set template for all default calculations of policy coverages. Customers can also use custom calculations for specific policy coverages.

There are two options for extensibility:

-   Extend the executable template with your own expression set and calculations.
    -   You can modify the calculation steps in the default expression set template and save it as a new custom expression set.
    -   When you create an expression set from scratch, make sure that you set the usage type to **Insurance Claim Processing**. Create local variables named **ClaimedAmount** and **AdjustedAmount**. For creating CCPA, use the naming convention `<category>_DeductionAmount` for local variables. In addition, mark all local variables, except for ClaimedAmount, with **Include in Output**. Refer to the default template for this configuration.
    -   This custom expression set can be used for any policy coverage, provided it's configured in the payment processing setup.
    -   Only one expression set can be active for a specific coverage product.
-   Use integration procedures to extend beyond the expression set.

When an incoming claim coverage is received, the system identifies the coverage product and the calculation component configured in the payment processing setup at design time. Based on this information, the API uses either an integration procedure or an expression set. If nothing is configured, the default expression set is used for calculation. The expression set uses the Policy Limit Context during the calculation. The output from the Get Current Standings API is stored in this context and is then used to calculate the adjustments.

Let's imagine a scenario where your car is involved in an accident, and you have the following auto insurance policy details:

**Auto Insurance Plan Details:**

-   **Deductible:** $1,000 - This is the amount you pay for covered repairs before your auto insurance starts to cover expenses, similar to the health insurance deductible.
-   **Coinsurance:** 10% - After meeting the deductible, you pay 10% of the remaining repair costs for a covered claim, and your insurance covers 90%.
-   **Out-of-Pocket Maximum (OOPM):** Maximum policyholder contribution for a single claim is $3,000. This is the maximum amount you will pay out-of-pocket for a single covered incident, after which your insurance covers 100% of the remaining costs for that specific claim.

**Auto Repair Costs:** Total Car Repair Cost: $15,000

1.  Pay the deductible first:
    
    -   For the first $1,000 of your car repair expenses, you pay 100%. After paying this amount, your deductible is met.
    -   Remaining balance of car repair after deductible: $15,000 - $1,000 = $14,000.
2.  Apply coinsurance:
    
    -   You pay 10% of the remaining $14,000 until you hit the OOPM. Your insurance covers the other 90%.
    -   Your coinsurance responsibility: $14,000 × 10% = $1,400.
3.  Check if you've reached the maximum OOPM:
    
    -   You've already paid $1,000 (deductible) + $1,400 (coinsurance) = $2,400.
    -   Your plan's OOPM is $3,000. Since $2,400 is less than $3,000, you haven't yet reached your maximum out-of-pocket for this claim. You would continue paying your coinsurance until you hit $3,000.
    -   Amount remaining to reach OOPM: $3,000 - $2,400 = $600.
    -   However, in this specific example, your calculated coinsurance ($1,400) didn't exceed the OOPM when added to your deductible. So, in this instance, the full coinsurance would be paid, and your total out-of-pocket would be $2,400.
    
    Your total contribution so far is $1,000 (deductible) + $1,400 (coinsurance) = $2,400.
    
4.  Total amount you pay out-of-pocket for this claim:
    
    -   Deductible: $1,000
    -   Coinsurance: $1,400
    -   Total out-of-pocket costs for this single claim: $2,400.
5.  If the coverage limit matches or exceeds the remaining amount of $12,600, the insurance covers the amount.
    
    -   Coverage limit: $15,000
        
    -   Your total car repair cost was $15,000.
        
    -   You paid $2,400.
        
    -   Remaining amount: $15,000 - $2,400 = $12,600
        
    -   Insurance covers the remaining: $15,000 - $2,400 = $12,600
        
6.  If the coverage limit is less than the remaining amount of $12,600, say $10,000, the insurance covers only up to the limit.
    
    -   Coverage limit: $10,000
        
    -   Your total car repair cost was $15,000.
        
    -   You paid $2,400.
        
    -   Remaining amount: $15,000 - $2,400 = $12,600
        
    -   Insurance covers up to the coverage limit: $10,000
        

[](https://help.salesforce.com/s?language=en_US)

## Process Policy Limits API

The Process Policy Limits API processes the policy limits for the loss item in a claim. It verifies the available limits against a policy coverage across various scopes for the Limit-Currency and Limit-Unit Count categories. The API response indicates whether the limit is exceeded and the excess currency amount or unit count. Based on this information, claim adjusters can stop payments or make reserve adjustments. By using an expression set for precise calculations and supporting custom data queries and complex calculations, the API ensures compliance, reduces manual errors, and improves financial accuracy. The API invokes the Get Current Standings API to retrieve the current consumption of the policy limits and then processes the policy limits.

The API uses a prebuilt file based executable expression set template for all default calculations of policy coverages. Customers can also use custom calculations for specific policy coverages. The Process Policy Limits API supports extensibility for processing the limits. Admin users can configure custom calculations via an expression set or an integration procedure. There are two options for extensibility.

There are two options for extensibility:

-   Extend the executable template with your own expression set and calculations.
    -   You can modify the calculation steps in the default expression set template and save it as a new custom expression set.
    -   This custom expression set can be used for any policy coverage, provided it's configured in the payment processing setup.
    -   Only one expression set can be active for a specific coverage product.
-   Use integration procedures to:
    -   Extend beyond the expression set
    -   Incorporate data for entities other than CCPD, IPL, and IPLT. This includes claimant or account data, such as age, region, or employer group.
    -   Implement advanced obligation logic, such as age-based coinsurance rebates.

When an incoming claim coverage is received, the system identifies the coverage product and the processing limit component configured in the payment processing setup at design time. Based on this information, the API uses either an integration procedure or an expression set. If nothing is configured, the default expression set is used for calculation. The expression set uses the Policy Limit Context during the calculation. The output from the Get Current Standings API is stored in this context and is then used to calculate the process limits.

[](https://help.salesforce.com/s?language=en_US)

## Create Claim Coverage Payment Detail API

For loss items, the Create Claim Coverage Payment Detail (CCPD) API creates the CCPD records by using a set of user inputs such as the claimed amount, the adjusted amount, and coverage payment type. The API invokes the Get Current Standings API to retrieve the current consumption of the policy limits and validates adjustment amount sent as input. In addition, it creates Insurance Policy Limit Tracking and Claim Coverage Payment Adjustment records. For expense items, the API only creates the CCPD record based on the inputs provided.

[](https://help.salesforce.com/s?language=en_US)

## Edit Claim Coverage Payment Detail API

For a claim coverage payment detail record with a Draft status, the API enables an adjuster to update information such as the claimed amount, adjusted amount, description, recipient, limit count, and additional fields. For expense items, the API updates the claim coverage payment detail record based on the user input. For loss items, if the claimed amount is modified, the API calls the Recalculate Adjustments API with the user input to reverse policy limit consumption and recalculate limits and adjustments. Based on the Recalculate Adjustments API output, the API creates insurance policy limit tracking records to roll back previous consumption and to track the revised consumption for a full audit trail. Then, the API deactivates previously created claim coverage payment adjustment records and creates new records to capture the recalculated adjustments. Finally, the API updates the claim coverage payment detail record. If the claimed amount isn’t modified, the API doesn’t call the Recalculate Adjustments API and updates details such as description, recipient, limit count, or additional fields.

## Recalculate Adjustments API

The API recalculates the adjustment and limit consumption for a loss item when an adjuster edits the claim coverage payment detail record to update the claimed amount. The API returns the recalculated adjusted amount and reason, and the details to create new insurance policy limit tracking and claim coverage payment adjustment records.

[](https://help.salesforce.com/s?language=en_US)

## Cancel Claim Coverage Payment Detail API

The Cancel Claim Coverage Payment Detail (CCPD) API cancels the payment for a claim coverage payment detail record. For Loss type claims, it also reverses the insurance policy limit tracking data to roll back the policy limit consumption. In addition to this, the API also deactivates any Claim Coverage Payment Adjustment (CCPA) records created due to the initial adjustments. Claim Adjusters use this API to cancel payments due to changes in claim validity, coverage adjustments, or processing errors. The API ensures that policy consumptions are accurately restored and financial records remain precise.

[](https://help.salesforce.com/s?language=en_US)

## Delete Claim Coverage Payment Detail API

The Delete Claim Coverage Payment Detail (CCPD) API removes the unpaid claim coverage payment details by updating the CCPD record status to Deleted. It also reverses the insurance policy limit tracking data to roll back consumption for the type Loss. In addition to this, the API also deactivates any CCPAs created due to the initial adjustments. Claim Adjusters use this API to soft-delete unpaid CCPD records from the system, ensuring data accuracy and proper limit management.

[](https://help.salesforce.com/s?language=en_US)

## Pay Claim Coverage Payment Detail API

The Pay Claim Coverage Payment Detail (CCPD) API handles the processing of payments for CCPD records. It updates the CCPD status to Paid and checks policy limits to ensure the adjusted amount doesn't exceed the available limits. If the limits are within the threshold, the API processes the payment, creates Insurance Policy Limit Tracking records to account for limit consumption, and updates the payment summary. If any limit-based attribute is exceeded, the system blocks the payment.

## Pay Ex Gratia API

For loss items, the API enables an adjuster to authorize exceptional payments that exceed the policy limits. The API creates insurance policy limit tracking records to track limit consumption up to the allowed threshold. In the claim coverage payment detail record, the API captures the excess amount or units authorized and the reason that the adjuster provides, and sets the status of the record to Paid Ex Gratia.

#### See Also

-   [Insurance Claims Business APIs](https://developer.salesforce.com/docs/atlas.en-us.insurance_developer_guide.meta/insurance_developer_guide/insurance_claim_business_api_overview.htm)

Did this article solve your issue?

Let us know so we can improve!

YesNo