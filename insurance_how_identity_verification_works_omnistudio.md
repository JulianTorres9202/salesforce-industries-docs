---
title: "How Identity Verification Works"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_how_identity_verification_works_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# How Identity Verification Works

How Identity Verification Works[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How Identity Verification Works

How a call center agent verifies a caller’s identity depends on whether you want the agent to verify just the caller or both the caller and the person they represent.

Verify Customer Identity verifies the identity of a caller before their request can be processed by a contact center agent (CCA) and logs the details of an interaction between a customer or authorized representative and a CCA. Derives its configuration from the default Identity Verification Process Definition record, SampleVerificationFlow, and the default Identity Verification Process Detail record, SampleAccountSearch. The Verify Customer Identity flow template stores interaction details in these objects:

[](https://help.salesforce.com/s?language=en_US)

-   [Engagement Interaction](https://developer.salesforce.com/docs/atlas.en-us.health_cloud_object_reference.meta/health_cloud_object_reference/sforce_api_objects_engagementinteraction.htm)—Stores details such as communication channel, start and end dates, and time of the call.
    
-   [Engagement Attendee](https://developer.salesforce.com/docs/atlas.en-us.health_cloud_object_reference.meta/health_cloud_object_reference/sforce_api_objects_engagementattendee.htm)—Stores details about the people participating in the interaction.
    
-   [Engagement Topic](https://developer.salesforce.com/docs/atlas.en-us.health_cloud_object_reference.meta/health_cloud_object_reference/sforce_api_objects_engagementtopic.htm)—Stores details about the reason for the call.
    

When a CCA accepts a call, an Engagement Interaction record page opens. After successful verification:

-   The interaction record is auto-updated with details such as the channel of communication and the start and end date and time of the call.
    
-   An Engagement Attendee record is created to store details about persons who attended the call.
    
-   An Engagement Topic record is created to store details about what the call was about.
    

No matter the template, with the default configuration, a CCA can verify a caller’s account name, birth date, phone number, and postal code.

[](https://help.salesforce.com/s?language=en_US)

-   Text-based search is performed on Account records.
    
-   Account name, birth date, and phone number are shown in search results.
    
-   Account name and birth date appear as required verifying questions.
    
-   Phone number and postal code appear as optional verifying questions.
    
-   The agent must check at least one optional question.
    

[](https://help.salesforce.com/s?language=en_US)Create your own identity verification process definition, process detail, and process field records to customize the configuration.

[](https://help.salesforce.com/s?language=en_US)The Verify Customer Identity flow template also includes a subflow, Verify Linked Caller Identity, that you must use to perform a second level of verification if, for example, you must verify the identities of a customer and their authorized representative. The default configuration isn’t enough to configure the secondary verification. For that, you must have at least two Identity Verification Process Detail records such that one is linked to the other.

Now that you're familiar with the components of Identity Verification, you're ready to start customizing the verification process to meet your specific business needs and legal requirements. Head over to the Identity Verification settings page in Setup to take advantage of the setup assistant.

Did this article solve your issue?

Let us know so we can improve!

YesNo