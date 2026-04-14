---
title: "Default Configuration and Customization for Proof of Insurance Omniscript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_default_config_and_cust_for_proof_of_insurance_omniscript.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Default Configuration and Customization for Proof of Insurance Omniscript

Default Configuration and Customization for Proof of Insurance Omniscript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Default Configuration and Customization for Proof of Insurance Omniscript

Understand the default configuration for Proof of Insurance Omniscript and customize it according to your business requirement.

Create an Omniscript that walks users through requesting proof of insurance. To edit the Process Insurance Proof Request flow, open the Omnistudio app, go to the OmniScripts page, expand the FSCIns/RequestInsuranceProof Omniscript, and open the latest version.

The table lists the typical steps in a Proof of Insurance Omniscript.

| Component Name | Component Type | What it does | What it calls |
| --- | --- | --- | --- |
| SetServiceProcessAccountContext | Integration Procedure Action | Sets context ID and community base URL. Determines if the user is a community service user or an agent. | FSCInsSelfService\_SetServiceProcessAccountContext |
| FSCIns\_ServiceProcessGetAccountDetails | Integration Procedure Action | Retrieves the details related to the AccountId/ContextId. | FSCInsRqstinsPrf\_FetchPolicies |
| SelectPolicy | Step | Shows insurance policies of the policyholder and prompts the user to select a policy that the user wants to request the proof of Insurance for. | NA |
| SetNoPolicySelected | SetValues | If no policy is selected in the SelectPolicy step, then this value is set. | NA |
| SetNoPolicySelectedError | SetErrors | If no policy is selected in the SelectPolicy step, this error validation is set. When the user clicks the Next button, this error is shown to the user. | NA |
| FetchAssetsorParticipants | Integration Procedure Action | Fetches the asset and participant details related to the selected policy. | IntegrationProcedure: FSCinsRastinsPrf\_FetchAssetsorParticipants |
| ResetSelectedAssetsorParticipants | Set Values | Resets the selected assets of participants. | NA |
| SelectAssetorParticipant | Step | With this, customer agent or policyholder selects the asset or participant that proof of insurance is needed for. | NA |
| SetSelectionIndicator | Set Values | Defines whether an asset or participant is selected in the SelectAssetorParticipant step. | NA |
| SetNoAssetSelectedError | Set Errors | Defines the error when no asset is selected in the SelectAssetorParticipant step. | NA |
| SetNoParticipantSelectedError | Set Errors | Defines the error when no participant is selected in the SelectAssetorParticipant step. | NA |
| SetSummaryScreenValues | Set Values | Sets the values required in the View summary steps. | NA |
| Review Summary | Step | Shows the selected policy details, assets or participants, and presents a Submit button for the user to confirm the insurance proof request. Additionally, it shows a call script for the customer case agent persona to read out to the policy holder. | NA |
| GetSelectedPolicyDetails | Integration Procedure Action | Retrieves the policy coverage details related to the selected policy. | IntegrationProcedure: FSCInsRgstinsPrf\_GetSelectedPolicyDetails |
| CreateCase | Remote Action | Creates a case for Request Insurance Proof process. | ApexClass: FSCinsRqstinsPrfHelperFunction AND Method: callCreateCaseApi |
| SetCreateCaseConfirmation | Set Values | Sets whether case creation is successful. | NA |
| SetCreateCaseConfirmationError | Set Errors | Sets the error message if case creation fails. | NA |
| CreateAttachment | PDF Action | Creates a PDF document for the selected Asset/Participant record | Uses the FSCinsRqstinsPrfAttachmentTemplate document template and merges the merge field values and then generates a PDF document that gets attached to the new case. |
| SetCaseConfirmationDetails | Set Values | Set the case details (case number and URL). | NA |
| View Summary | Step | Shows the summary that the case is created. Also renders the case that's created as a link that leads to the case record page. | NA |

Did this article solve your issue?

Let us know so we can improve!

YesNo