---
title: "Prerequisites for Setting Up the Insurance Agent Console"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_prerequisites_for_setting_up_the_insurance_agent_console_.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Prerequisites for Setting Up the Insurance Agent Console

Prerequisites for Setting Up the Insurance Agent Console[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Prerequisites for Setting Up the Insurance Agent Console

Review these prerequisites and considerations to set up and use the Service Console for Insurance customers.

OrgPref

Get the OrgPref for Service Excellence for Insurance to get access to the Service Console for Insurance. For more information, see [Get Access to Insurance Agent Console](https://help.salesforce.com/s/articleView?id=ind.insurance_get_access_insurance_agent_console.htm&language=en_US&type=5 "To access the service console, enable the Service Excellence for Insurance setting for your org.").

Timeline

To use the Timeline component in the console, enable Timeline in Setup. The Insurance Agent console has a preconfigured Insurance Timeline component that shows the engagement interaction records for an insurance customer.

To create a custom timeline that shows other insurance object records, configure the Timeline component included with Industries Service Excellence, and add the component to the Service Excellence account record page. To learn how a timeline works, see [View Events Using Timeline in Salesforce](https://help.salesforce.com/s/articleView?id=ind.timeline_client_information.htm&language=en_US&type=5).

Record Alerts

Configure record alerts that meet your business needs. Insurance Agent Console has preconfigured alerts for these scenarios:

-   New claims
    
-   Policy renewal
    
-   Payment due
    

Actions

File Upload

File Upload action triggers an OmniScript to upload files to different objects. Since it is configured on the Account object, the uploaded file is attached to the Account object and can be found in the Notes and attachments. All the file extension types are supported.

You can configure actions that meet your business needs. See [Create Actions & Recommendations Deployment](https://help.salesforce.com/s/articleView?id=service.console_lex_guided_action_deployment.htm&language=en_US&type=5).

Identity Verification

To use Identity Verification with the console, use the preconfigured Insurance: Verify Caller Identity Flow. To add the flow to your component, from the Setup menu (the gear icon), click **Edit Page**. Select the flow, and then activate the page. You can also clone and customize the flow to meet your business requirements. To learn more, see [How Identity Verification Works in Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_how_identity_verification_works_in_insurance.htm&language=en_US&type=5 "How a call center agent verifies a caller’s identity depends on whether you want the agent to verify just the caller or both the caller and the person they represent.").

Engagement Interaction Records

To integrate computer-telephony with the Insurance Agent Console, configure computer-telephony integration (CTI) systems. You can set up a softphone using Service Cloud’s CTI integration, and the identity verification flow and the engagement data model work seamlessly with Service Cloud’s CTI process. Then, use the Engagement Connect APIs to configure the link between the softphone and an Engagement Interaction record. This ensures that an Engagement Interaction record is automatically created when an inbound call comes in.

To configure CTI, see [Salesforce Open CTI](https://help.salesforce.com/s/articleView?id=service.cloud_cti_api_overview.htm&language=en_US&type=5). To use the Connect APIs, see [Engagement Connect APIs](https://developer.salesforce.com/docs/atlas.en-us.246.0.industries_reference.meta/industries_reference/engagement_connect_apis.htm).

Did this article solve your issue?

Let us know so we can improve!

YesNo