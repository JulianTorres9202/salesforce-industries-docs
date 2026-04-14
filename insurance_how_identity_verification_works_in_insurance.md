---
title: "How Identity Verification Works in Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_how_identity_verification_works_in_insurance.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# How Identity Verification Works in Insurance

How Identity Verification Works in Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How Identity Verification Works in Insurance

How a call center agent verifies a caller’s identity depends on whether you want the agent to verify just the caller or both the caller and the person they represent.

The preconfigured verification flows verifies the identity of a caller before their request can be processed by a contact center agent (CCA) and logs the details of an interaction between a caller or authorized representative and a CCA. The flow derives its configuration from the default Identity Verification Process Definition record, `SampleVerificationFlow`, and the default Identity Verification Process Detail record, `SampleAccountSearch`.

Here are the three flow templates that you can choose from for your identity verification process:

-   Insurance: Verify Caller Identity
    
    -   Authenticates either the identity of a customer or the identities of a representative and a customer before the customer's request can be processed by a contact center agent (CCA).
        
-   Insurance: Verify Producer
    
    -   Authenticates the identity of an unregistered caller before their request can be processed by a contact center agent.
        
-   Insurance: Verify Caller and Producer
    
    -   Authenticates the identity of an unregistered caller before their request can be processed by a contact center agent.
        

The verification flow templates store interaction details in these objects:

-   Engagement Interaction: Stores details such as communication channels, start and end dates, and time of the call.
    
-   Engagement Attendee: Stores details about the people participating in the interaction.
    
-   Engagement Topic: Stores details about the reason for the call.
    

When a CCA accepts a call, an Engagement Interaction record page opens. After successful verification:

-   The interaction record is auto-updated with details such as the channel of communication and the start and end date and time of the call.
    
-   An Engagement Attendee record is created to store details about persons who participated in the call.
    
-   An Engagement Topic record is created to store details about what the call was about.
    

No matter the template, with the default configuration, a CCA can verify a caller’s account name, birth date, phone number, and postal code.

-   Text-based search is performed on Account records.
    
-   Account name, birth date, and phone number are shown in search results.
    
-   Account name and birth date appear as required verifying questions.
    
-   Phone number and postal code appear as optional verifying questions.
    
-   The agent must check at least one optional question.
    

Create your own identity verification process definition, process detail, and process field records to customize the configuration.

Now that you're familiar with the components of Identity Verification, you're ready to start customizing the verification process to meet your specific business needs and legal requirements. Go to the Identity Verification Settings page in Setup and follow steps in the setup assistant to get up and running.

Did this article solve your issue?

Let us know so we can improve!

YesNo