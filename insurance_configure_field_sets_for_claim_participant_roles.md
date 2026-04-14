---
title: "Configure Field Sets for Claim Participant Roles"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_configure_field_sets_for_claim_participant_roles.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Configure Field Sets for Claim Participant Roles

Configure Field Sets for Claim Participant Roles[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Configure Field Sets for Claim Participant Roles

Show claims adjusters exactly the right information for each claim participant, nothing extra. For example, configure separate field sets to show different information for first-party claimants, third-party claimants, and auto body shops.

Users who process claims see the fields from the appropriate field set when they review details about each claim participant. If a claim participant has multiple roles, the Claim Participant card shows unique fields from each role.

1.  From Setup, in Object Manager, find and select the **Claim Participant** object. Go to **Field Sets**, and then click **New**.
    
    Create a field set for each claim participant role. For example, create a field set called `FieldsetWitness` with **Account Name**, **Phone**, **Email**, and other key fields for witnesses.
    
2.  From Setup, in the Quick Find box, enter Custom Settings, and then select **Custom Settings**.
3.  Next to **Insurance Configuration Setup**, click **Manage**.
4.  Click **New**.
5.  Configure a custom setting that corresponds to each participant role field set.
    
    -   For **Name**, enter Role: followed by a Claim Participant role value. For example, enter Role:Witness.
    -   For **Setup Value**, enter the name of the field set you created for this role.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo