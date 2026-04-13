---
title: "Activation and Cloning of the Process Insurance Proof Request Flow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_activation_and_cloning_of_insurance_proof.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Activation and Cloning of the Process Insurance Proof Request Flow

Activation and Cloning of the Process Insurance Proof Request Flow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Activation and Cloning of the Process Insurance Proof Request Flow

Use the Process Insurance Proof Request Flow Orchestration to show your agents the step-by-step instructions to submit an insurance proof request for a user. You can customize the flow to meet your business needs.

Clone the Process Insurance Proof Request orchestration template and activate a new version in Salesforce. The orchestration provides a declarative process automation that contains a sequence of stages and steps. A stage contains interactive and background steps. Interactive steps have an assigned user and run a designated screen flow. Background steps launch a flow that's automatically run by the system and requires no user interaction. The interactive and background steps are required to fulfill the request for Proof of Insurance that is submitted.

The Process Insurance Proof Request orchestration is used by the user working on a case to review an Insurance Proof request, submit the request, and either update the case record or notify the case owner that the update failed. The orchestration contains these business stages:

-   Notify Account and Close Case: If the insurance proof can be created, email the policy holder that a request was made for proof of insurance and that the proof is available for download for a specified period of time. If the proof of insurance was created, the case associated with the request is closed.
-   Notify Case Owner of Failed Request: Assigns a work item to the service catalog request record owner that notifies them that the insurance proof request failed. To customize the failure information shown to the record owner, update the Display Service Request Status Screen element in the Service Process: Show Asynchronous Apex Action Callout Status flow.

-   **[Create and Activate the Orchestration Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_create_and_activate_orchestration_flow.htm&language=en_US&type=5)**  
    Create an orchestration flow that creates an insurance proof for an account, notifies them that the proof is downloadable, and closes the case associated with the request.
-   **[Create an Apex Class](https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_apex_class.htm&language=en_US&type=5)**  
    Create an Apex class to send an email with attachment to the user who requests insurance proof.
-   **[Update the Flow to Call the Apex Class](https://help.salesforce.com/s/articleView?id=ind.insurance_update_flow_to_call_apex_class.htm&language=en_US&type=5)**  
    Update the Send Email with Attachment To Policy Holder action in the Flow to call the Apex class to send an email with attachment to the policyholder when a case is closed.

Did this article solve your issue?

Let us know so we can improve!

YesNo