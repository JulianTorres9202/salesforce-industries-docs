---
title: "Create an Identity Verification Flow with the Verify Customer Identity Flow Template"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_identity_verification_flow_with_the_verify_customer_identity_flow_template_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create an Identity Verification Flow with the Verify Customer Identity Flow Template

Create an Identity Verification Flow with the Verify Customer Identity Flow Template[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create an Identity Verification Flow with the Verify Customer Identity Flow Template

Depending on the kind of identity verification your organization requires, create a flow using either the Verify Caller Identity or the Verify Customer Identity flow template.

Create a custom identity verification process configuration using the Verify Customer Identity flow template. Specify the names of the relevant Identity Verification Process Definition and Identity Verification Process Detail records as the values of the `IdVerfProcessDefinition` and the `IdVerfProcessDetail` constants.

To verify a caller who is pre-identified, set the value of the `IdVerfProcessDetail` constant. As the name suggests, `IdVerfProcessDetail` refers to the relevant Identity Verification Process Detail record name. Set this value to indicate to the flow the process detail record to be used to verify a pre-identified caller. You must set the `IdVerfProcessDetail` value even if there’s only one process detail record for a process definition record.

Note

Create two separate flows, one for primary verification and the other for both primary and secondary verifications.

When using the Verify Customer Identity flow template to create a flow for identity verification, use the [Salesforce Open CTI](https://help.salesforce.com/s/articleView?id=service.cti_channel.htm&language=en_US&type=5) to integrate third-party computer-telephony integration (CTI) systems with Salesforce. When your users accept a call from the customer, Salesforce creates an Engagement Interaction record to store details of the interaction. If the call’s from a registered number, the `InitiatingAttendee` field in the record is auto-populated with the name associated with the number.

1.  In the Identity Verification admin setup assistant, click **Create Flow**.
    
2.  Click **New Flow**.
    
3.  In the New Flow window, on the All + Templates tab, select **Verify Customer Identity** and click **Create**.
    
4.  Click **Save**.
    
5.  Enter the flow label and API name, and save the flow.
    
6.  In Resources, edit `IdVerfProcessDefinition` and enter the relevant Identity Verification Process Definition record name as the value.
    
7.  In Resources, edit `IdVerfProcessDetail` and enter the relevant Identity Verification Process Detail record name as the value.
    
8.  Click **Done**.
    
9.  Save and activate the flow.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo