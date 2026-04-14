---
title: "Components of Identity Verification in Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_components_of_identity_verification_in_insurance.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Components of Identity Verification in Insurance

Components of Identity Verification in Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Components of Identity Verification in Insurance

The Identity Verification feature consists of Identity Verification objects, Engagement Interaction objects, and Identity Verification flows.

Identity Verification is built on these objects:

-   Identity Verification Process Definition: Use this object to link the configuration to the flow.
    
-   Identity Verification Process Detail: Use this object to configure the search function and to set the minimum number of additional verifying questions.
    
-   Identity Verification Process Field: Use this object to set up verifying questions.
    

An Identity Verification Process Field record looks up to an Identity Verification Process Details record, which in turn looks up to an Identity Verification Process Definition record. Each process definition record can have multiple process detail records associated with it. Similarly, each process detail record can have multiple process field records. The flow templates derive their configuration from these objects.

The Engagement Interaction, Engagement Attendee, and Engagement Topic objects are required with the Insurance: Verify Caller Identity Flow flow templates. These objects store details of an interaction between a call center agent and a customer.

For detailed setup and configuration steps, see [Identity Verification](https://help.salesforce.com/s/articleView?id=ind.fsc_identity_verification.htm&language=en_US&type=5) in the Common Features Guide.

Did this article solve your issue?

Let us know so we can improve!

YesNo