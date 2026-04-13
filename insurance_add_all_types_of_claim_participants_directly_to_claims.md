---
title: "Add All Types of Claim Participants Directly to Claims"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_all_types_of_claim_participants_directly_to_claims.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add All Types of Claim Participants Directly to Claims

Add All Types of Claim Participants Directly to Claims[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add All Types of Claim Participants Directly to Claims

Add any claim participant to a claim regardless of the participant’s role or involvement. This includes auto body shops, physicians, and other claim participants that aren’t associated with any of the claim’s involved items. Add these claim participants using the same service you use to create and update claims.

This applies to the Salesforce FSC Claim object, not the Vlocity InsuranceClaim object.

[](https://help.salesforce.com/s?language=en_US)**Where:** Available in Summer '22 and later releases.

**How:** Specify participant details in the `additionalClaimParticipants` node in input JSON for the `InsClaimService: createUpdateClaim` service.

## See Also

[InsClaimService:createUpdateClaim](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservicecreateupdateclaim_630113.htm&language=en_US&type=5 "Use this service to create or update a claim.")

Did this article solve your issue?

Let us know so we can improve!

YesNo