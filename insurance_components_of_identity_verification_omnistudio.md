---
title: "Components of Identity Verification"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_components_of_identity_verification_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Components of Identity Verification

Components of Identity Verification[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Components of Identity Verification

The Identity Verification feature consists of Identity Verification objects, Engagement Interaction objects, and identity verification flows.

Identity Verification is built on these objects:

-   Identity Verification Process Definition - Use this object to link the configuration to the flow.
-   Identity Verification Process Detail - Use this object to configure search function and to set the minimum number of additional verifying questions.
-   Identity Verification Process Field - Use this object to set up verifying questions.

An Identity Verification Process Field record looks up to an Identity Verification Process Details record, which in turn looks up to Identity Verification Process Definition record. Each process definition record can have multiple process detail records associated with it. Similarly, each process detail record can have multiple process field records. The flow templates derive their configuration from these objects.

The Engagement Interaction, Engagement Attendee, and Engagement Topic objects are required with the Verify Customer Identity and the Verify Linked Caller Identity flow templates. These objects store details of an interaction between a call center agent and a customer.

Did this article solve your issue?

Let us know so we can improve!

YesNo