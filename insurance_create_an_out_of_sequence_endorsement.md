---
title: "Manage an Out-of-Sequence Endorsement"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_out_of_sequence_endorsement.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Manage an Out-of-Sequence Endorsement

Manage an Out-of-Sequence Endorsement[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Manage an Out-of-Sequence Endorsement

An out-of-sequence endorsement is a modification to a policy with an effective date that is earlier than the effective date of another endorsement already bound on the policy. All the backdated changes are automatically applied on top of future policy versions within and across the policy terms.

For example, you issue a policy and add an endorsement 1 with an effective date of 7/1/2023. Now, if you create another endorsement transaction with an effective date of 3/1/2023, the transaction is out of sequence. 

Once an out of sequence is performed on a policy, all the future versions in the timeline of the policy are updated to reflect the change.

As part of the Out-of-Sequence Endorsement, you can:

-   Perform backdated modifications to a policy within and across (past and future) the policy term. For multi policy terms,
    
    -   Out-of-sequence endorsement can be performed for up to five years in the past and up to 15 policy versions.
        
    -   Out-of-sequence endorsement can be performed for up to one year in future and up to three future policy versions.
        
-   Apply the backdated changes automatically to future versions.
    
-   Enable out of sequence endorsement for internal agents using lightning web component.
    
-   Generate the Out-of-Sequence Changed/Endorsed transaction for the period impacted due to out-of-sequence endorsement.
    
-   Enable out-of-sequence endorsement for internal agents using the lightning web component.
    
-   Enable out-of-sequence endorsement for external agents, brokers, and policyholders using the [InsPolicyService:createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5 "Use this service to initiate an out-of-sequence endorsement for a given policy.") service.
    

Enable the out of sequence endorsement setting and modify the policy to create an out of sequence endorsement.

-   **[Prerequisites for Out-of-Sequence Endorsement](https://help.salesforce.com/s/articleView?id=ind.insurance_prerequisites_for_out-of-sequence_endorsement.htm&language=en_US&type=5)**  
    Review these prerequisites and considerations to set up and create an out-of-sequence endorsement.
-   **[Configure an Out-of-Sequence Endorsement](https://help.salesforce.com/s/articleView?id=ind.insurance_configure_out_of_sequence_endorsement.htm&language=en_US&type=5)**  
    Configure the custom setting that enables the out-of-sequence endorsement support in your Lightning Web Component.
-   **[Issue an Out-of-Sequence Endorsement Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_out_of_sequence_policy.htm&language=en_US&type=5)**  
    The workflow kicks off when users attempt to create an endorsement with an effective date that is before the effective date of another transaction already bound on the policy.
-   **[Subscribe to the InsAsyncJobStatusNotification Event](https://help.salesforce.com/s/articleView?id=ind.insurance_subscribe_to_the_insasyncjobstatusnotification__event.htm&language=en_US&type=5)**  
    Out-of-sequence endorsement works asynchronously after you initiate the policy issuance with the new modifications. After an out-of-sequence endorsement completes, an event is published. Subscribe to these events to support additional custom notification types, such as sending emails to the customers.
-   **[Get the Status of an Async Out-of-Sequence Endorsement](https://help.salesforce.com/s/articleView?id=ind.insurance_get_the_status_of_an_async_out-of-sequence_endorsement.htm&language=en_US&type=5)**  
    Use InsPolicyService:getOutOfSequenceEndorsementStatus to retrieve the current status of an out-of-sequence-endorsement async job.

Did this article solve your issue?

Let us know so we can improve!

YesNo