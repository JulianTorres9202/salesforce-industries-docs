---
title: "Issue an Out-of-Sequence Endorsement Policy"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_issue_out_of_sequence_policy.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Issue an Out-of-Sequence Endorsement Policy

Issue an Out-of-Sequence Endorsement Policy[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Issue an Out-of-Sequence Endorsement Policy

The workflow kicks off when users attempt to create an endorsement with an effective date that is before the effective date of another transaction already bound on the policy.

1.  On an **Insurance Policy** record, click **Modify Policy**.
2.  On the **Modify Policy** window, enter the Quote Name and Effective Date of the new version of the policy. For an out of sequence endorsement, the effective date is on or before the effective date of the existing policy versions.
3.  To notify you that an endorsement is out of sequence, the system shows a warning along with a list of future versions that are impacted by this transaction. You can still choose to move forward with the endorsement creation process.
4.  Click **Create** to generate an Endorsement quote.
5.  On the **Quote** record, add, remove, and edit insured items and coverages as needed. After you finish making changes to the quote, click **Issue Policy**.
    
    Important Out-of-Sequence Endorsement is supported from the out-of-the-box Issue Policy button.
    
6.  Edit the **Policy Name** field and click **Create** to issue the new version of the policy from the endorsement quote.
    
    -   Since out-of-sequence endorsement involves an asynchronous Apex job, you can proceed to perform other tasks after you initiate the out-of-sequence endorsement. While the async job is in progress, the Issue Policy button is disabled and the Quote page displays the message "_Issuing policies. We'll notify you after it's complete._" All the policy versions are locked and unavailable until the async job completes.
        
    -   To get the status of the out-of-sequence endorsement process, use the [InsPolicyService:getOutOfSequenceEndorsementStatus](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice_getoutofsequenceendorsementstatus.htm&language=en_US&type=5 "Use this service to retrieve the current status of the OutOfSequenceEndorsement async job. The service accepts jobId, policyId, or referencePolicyNumber as an input to fetch the out-of-sequence endorsement operation status.") service.
        
    -   After the endorsement is completed, you receive a bell notification about the successful policy issuance. If the process fails, you get a bell icon notification for failure and the policies are rolled back to the prior out-of-sequence endorsement state.
        
    
    -   After an out-of-sequence is performed on a policy, all the future versions in the timeline of the policy are impacted. The existing future versions are canceled and the corresponding new versions with the backdated changes are created. Also, the policy names of all the new versions with backdated changes are appended with a "+" sign. The new policy version has attributes inherited from the latest endorsement quote.
        
    -   Generates the Out-of-Sequence Changed/Endorsed transaction for the period impacted due to out-of-sequence endorsement. All the transactions are linked to the original policy of the term.
        
    
    You can also perform an out-of-sequence endorsement from [InsPolicyService:createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5 "Use this service to initiate an out-of-sequence endorsement for a given policy.").
    

Did this article solve your issue?

Let us know so we can improve!

YesNo