---
title: "Handle Custom Fields During an Out-of-Sequence Endorsement"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_manage_custom_fields_during_an_out-of-sequence_endorsement.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Handle Custom Fields During an Out-of-Sequence Endorsement

Handle Custom Fields During an Out-of-Sequence Endorsement[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Handle Custom Fields During an Out-of-Sequence Endorsement

Use the enhanced InsPolicyService:createOutOfSequencePolicyVersion service to configure and copy custom fields from canceled policy versions to new policy versions. This update makes sure that there's data consistency across policy versions for the out-of-sequence endorsement transaction.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package and the Insurance Industries Extension managed package.

**How:** Configure the OutOfSequenceEndorsementCustomFields field set to include custom fields that need to be copied from the canceled policy to the new policy versions during an out-of-sequence endorsement.

SEE ALSO

[InsPolicyService:createOutOfSequencePolicyVersion](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createoutofsequencepolicyversion.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo