---
title: "Set Up Out Of Sequence Endorsement Flows"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_out_of_sequence_endorsement_set_up_flow.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Set Up Out Of Sequence Endorsement Flows

Set Up Out Of Sequence Endorsement Flows[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Set Up Out Of Sequence Endorsement Flows

Configure flows to support Out-of-Sequence Endorsements (OOSE). Create a Modify Policy flow to show impacted policy versions before generating an endorsement quote, and update the Endorse Policy flow so it calls the correct invocable action depending on whether the endorsement is normal or OOSE.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Enterprise</strong>, <strong lwc-3eigj2skqo3="">Unlimited</strong>, and <strong lwc-3eigj2skqo3="">Developer</strong> Editions of Digital Insurance Platform</td></tr></tbody></table>

[](https://help.salesforce.com/s?language=en_US)

## Configure the Modify Policy Flow

Build a flow that shows impacted policies before creating an endorsement quote.

1.  In Setup, find and select **Flows**.
2.  Click **New Flow** and select **Screen Flow**.
3.  Add a Get Records element to fetch the policy from which the endorsement quote will be created (for example, policyV2).
4.  Use these conditions to fetch all impacted policies.
    
    | field | operator | value |
    | --- | --- | --- |
    | Reference Policy Number | Equals | policyV2.ReferencePolicyNumber |
    | Effective From Date | Greater Than or Equal | Create Quote > Effective Date |
    | isValidDate | Equals | True |
    
5.  Add a Screen element with a Data Table component to display the impacted policies.
6.  Add an Action element to call the createQuote invocable action to create the endorsement quote.
7.  Save and activate the flow.

[](https://help.salesforce.com/s?language=en_US)

## Configure the Endorse Policy Flow

Update the endorsement flow so it calls the correct invocable action depending on the type of endorsement.

1.  In Setup, find and select **Flows**.
2.  Create a new flow or edit an existing Endorse Policy flow.
3.  Add a Decision element to check whether the endorsement is out-of-sequence.
    1.  Use a custom checkbox field, such as isOOSE, on the quote.
    2.  Update this field when you create the quote.
4.  If isOOSE = false, call the endorsePolicy invocable action.
5.  If isOOSE = true, call the createOOSE IA.
    1.  Fetch the policyId required for OOSE from the sourceInsurancePolicy field.
    2.  Create an Apex-Defined Variable of type OutOfSequencePolicyEndorsementInputRep.
    3.  Create variables to pass required and optional values.
6.  Assign the variables to the input rep and pass it to the createOOSE invocable action.
    
    | variable | description | required |
    | --- | --- | --- |
    | contextId | Context ID of the endorsement quote. | Yes |
    | policyId | ID of the active policy version. Fetch this from the sourceInsurancePolicy field. | Yes |
    | effectiveDate | Effective date of the endorsement in YYYY-MM-DD format. Ensure the flow validates the format before passing it. | Yes |
    | insurancePolicy.policyName | Custom policy name for the endorsed version. | No |
    | insurancePolicy.policyNumber | Custom policy number for the endorsed version. | No |
    | transactionRecord.name | Custom name for the OOSE transaction record. | No |
    | fieldSetIds.policyFieldSetId | Field set ID for InsurancePolicy. | No |
    | fieldSetIds.assetFieldSetId | Field set ID for InsurancePolicyAsset. | No |
    | fieldSetIds.coverageFieldSetId | Field set ID for InsurancePolicyCoverage. | No |
    | fieldSetIds.participantFieldSetId | Field set ID for InsurancePolicyParticipant. | No |
    
    Note The Out-of-Sequence Policy Endorsement invocable action accepts the effectiveDate only in YYYY-MM-DD format. Make sure the flow validates and converts the date to this format before passing it.
    
7.  Save and activate the flow.
8.  Review the sample request payload for Create Out of Sequence Policy Endorsement invocable action.
    
    ```
    {
      "inputs": [
        {
          "outOfSequencePolicyEndorsementInputRep": {
            "contextId": "0000000i18tq18g00291756887529235fa93a78767224150998f3da85fa50e14",
            "policyId": "0YTZM0000004Cs34AE",
            "effectiveDate": "2025-06-01",
            "insurancePolicy": {
              "policyName": "New OOSE Policy",
              "policyNumber": "New OOSE Policy"
            },
            "transactionRecord": {
              "name": "OOSE transaction"
            },
            "fieldSetIds": {
              "policyFieldSetId": "xxx",
              "assetFieldSetId": "xxx",
              "participantFieldSetId": "xxx",
              "coverageFieldSetId": "xxx"
            }
          }
        }
      ]
    }
    ```

Did this article solve your issue?

Let us know so we can improve!

YesNo