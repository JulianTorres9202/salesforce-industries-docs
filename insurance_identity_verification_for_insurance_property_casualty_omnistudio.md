---
title: "Identity Verification for Insurance Property & Casualty"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_identity_verification_for_insurance_property_casualty_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Identity Verification for Insurance Property & Casualty

Identity Verification for Insurance Property & Casualty[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Identity Verification for Insurance Property & Casualty

The Identity Verification feature gives you the ability to verify the identity of a caller before you share any sensitive information with them. How you verify the identity of a caller depends on how your admin has configured the process.

With the default configuration, agents can verify a caller’s account name, birth date, phone number, and postal code.

-   Text-based search is performed on Account records.
    
-   Account name, birth date, and phone number are shown in search results.
    
-   Account name and birth date appear as required verifying questions.
    
-   Phone number and postal code appear as optional verifying questions.
    
-   The agent must check at least one optional question.
    

**Flow of Identity Verification**

1.  Components of Identity Verification
    
    The Identity Verification feature consists of Identity Verification objects, Engagement Interaction objects, and identity verification flows.
    
2.  How Identity Verification Works
    
    How a call center agent verifies a caller’s identity depends on the identity verification flow template used to configure the process. You may be required to verify the caller’s identity. Or your identity verification flow may also store interaction details. Finally, if someone is calling on another person’s behalf, you must verify two identities.
    
3.  Define the Link between Identity Verification Process Configuration and Flow
    
    The Identity Verification Process Definition object links the identity verification process configuration to the identity verification flow. It also defines the layout of the search screen. To pass the configuration information to the flow, create a process definition record.
    
4.  Set Up Search for Identity Verification
    
    When an agent receives a call, the first thing they do is search for the caller. To set up how the search works, such as whether the search is text-based or object-based, the data source to query, and more, create an Identity Verification Process Detail record. You can also specify the minimum number of additional verifying questions to ask a caller.
    
5.  Set Up Fields for Search and Verification
    
    The Identity Verification Process Field object enables you to determine what an agent sees, such as which fields appear in search results or which fields must be verified. Create an Identity Verification Process Field record for each field that is part of your identity verification process.
    
6.  Create an Identity Verification Flow with the Verify Customer Identity Flow Template
    
    Depending on the kind of identity verification your organization requires, create a flow using either the Verify Caller Identity or the Verify Customer Identity flow template.
    
7.  Make the Identity Verification Flow Available to Agents
    
    To enable your call center agents to perform identity verification, make the flow available to them.
    
8.  Use External Data for Identity Verification
    
    If the data required to verify a caller resides outside of Salesforce, configure the identity verification process to use data from an external source.
    
9.  Verify Identity
    

-   **[Components of Identity Verification](https://help.salesforce.com/s/articleView?id=ind.insurance_components_of_identity_verification_omnistudio.htm&language=en_US&type=5)**  
    The Identity Verification feature consists of Identity Verification objects, Engagement Interaction objects, and identity verification flows.
-   **[How Identity Verification Works](https://help.salesforce.com/s/articleView?id=ind.insurance_how_identity_verification_works_omnistudio.htm&language=en_US&type=5)**  
    How a call center agent verifies a caller’s identity depends on whether you want the agent to verify just the caller or both the caller and the person they represent.
-   **[Define the Link Between Identity Verification Process Configuration and Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_define_the_link_between_identity_verification_process_configuration_and_flow_omnistudio.htm&language=en_US&type=5)**  
    The Identity Verification Process Definition object links the identity verification process configuration to the identity verification flow. It also defines the layout of the search screen. To pass the configuration information to the flow, create a process definition record.
-   **[Set Up Search for Identity Verification](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_search_for_identity_verification_omnistudio.htm&language=en_US&type=5)**  
    When an agent receives a call, the first thing they do is search for the caller. To set up how the search works, such as whether the search is text-based or object-based, the data source to query, and more, create an Identity Verification Process Detail record. You can also specify the minimum number of additional verifying questions to ask a caller.
-   **[Set Up Fields for Search and Verification](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_fields_for_search_and_verification_omnistudio.htm&language=en_US&type=5)**  
    The Identity Verification Process Field object enables you to determine what an agent sees, such as which fields appear in search results or which fields must be verified. Create an Identity Verification Process Field record for each field that is part of your identity verification process.
-   **[Create an Identity Verification Flow with the Verify Customer Identity Flow Template](https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_identity_verification_flow_with_the_verify_customer_identity_flow_template_omnistudio.htm&language=en_US&type=5)**  
    Depending on the kind of identity verification your organization requires, create a flow using either the Verify Caller Identity or the Verify Customer Identity flow template.
-   **[Make the Identity Verification Flow Available to Agents](https://help.salesforce.com/s/articleView?id=ind.insurance_make_the_identity_verification_flow_available_to_agents_omnistudio.htm&language=en_US&type=5)**  
    To enable your call center agents to perform identity verification, make the flow available to them. Create an Engagement Interaction Lightning record page and then add the flow to the Engagement Interaction Lightning record page.
-   **[Use External Data for Identity Verification](https://help.salesforce.com/s/articleView?id=ind.insurance_use_external_data_for_identity_verification_omnistudio.htm&language=en_US&type=5)**  
    If the data required to verify a caller resides outside of Salesforce, configure the identity verification process to use data from an external source.
-   **[Verify Identity](https://help.salesforce.com/s/articleView?id=ind.insurance_verify_identity_omnistudio.htm&language=en_US&type=5)**  
    How you verify the identity of a caller depends on how your admin has configured the process.

Did this article solve your issue?

Let us know so we can improve!

YesNo