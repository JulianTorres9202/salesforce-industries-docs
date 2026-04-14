---
title: "First Notice of Loss"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_fnol.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# First Notice of Loss

First Notice of Loss[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# First Notice of Loss

When policyholders, brokers, or insurance reps first report a loss to an insurance carrier, they use the First Notice of Loss (FNOL) flow. Insurance carriers set up this FNOL flow by using Omniscripts. Omniscripts provide the interface that policyholders, insurance carrier brokers, or insurance reps use to file a claim. This FNOL flow starts the claims processing and supports the submission of documents to support the claim. On the backend, the flow uses the verifyPolicyCoverage API to confirm if the policyholder has an active coverage on the date of the loss. Then, it uses the createClaim API to create the initial claim record and the updateClaim API to update the claim details with additional information.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

## FNOL Workflow

Each FNOL flow typically performs distinct tasks that collectively aim to create and populate a claim record. Here are the essential building blocks that most FNOL flows include:

1.  **Verify Information About the Policy:** This step involves retrieving relevant details about the insurance policy, such as policy number, coverage limits, and policyholder information. This makes sure that the claim is associated with the correct policy.
2.  **Gather Data About the Loss:** In this phase, you collect comprehensive information about the incident or loss. This includes the date, time, location, and nature of the loss, as well as any other pertinent details that describe what happened.
3.  **Verify Whether the Loss is Covered:** Here, you assess whether the reported loss falls within the coverage parameters of the policy. This involves checking the policy's terms and conditions to determine if the claim is valid. The flow can invoke the verifyPolicyCoverage API to verify the policy.
4.  **Create the Claim Record:** After the loss is verified, you create a claim record in your system. This record serves as the central repository for all information related to the claim. The flow can invoke the createClaim API to create the claim.
5.  **Add More Details to the Claim:** Additional information is added to the claim record to provide a complete picture. This may include details about the claimant, witnesses, and any other relevant parties involved in the incident. The flow can use the updateClaim API to add the additional information to the claim.
6.  **Upload Supporting Photos and Documents:** To substantiate the claim, you upload any supporting evidence, such as photos of the damage, repair estimates, police reports, and other relevant documents.
7.  **Run Claim Workflow Rules:** Finally, you run predefined rules and checks to make sure that the claim meets all necessary criteria and complies with regulatory and company standards. This step helps in identifying any potential issues or discrepancies early in the process. The flow calls for the Insurance Invoke Underwriting Rule in this step.

Did this article solve your issue?

Let us know so we can improve!

YesNo