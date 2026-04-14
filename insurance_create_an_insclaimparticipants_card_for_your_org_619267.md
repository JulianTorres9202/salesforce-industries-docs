---
title: "Create an insClaimParticipants Card for Your Org"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_insclaimparticipants_card_for_your_org_619267.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create an insClaimParticipants Card for Your Org

Create an insClaimParticipants Card for Your Org[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create an insClaimParticipants Card for Your Org

The Vlocity Claim Participants Lightning web component (LWC) that underlies the Claim Participant UI is wrapped in the insClaimParticipants card. Create a copy of the insClaimParticipants card for use with your org. You can use this version of the card as is, or you can create your own OmniScript to launch from the Claim Participant UI and then associate that OmniScript to the card.

Before You Begin

-   Make sure the insClaimParticipantsCard is imported and activated in your org:
    
    -   From the App Launcher, find and select **Vlocity Flex Cards**.
        
    -   Verify that **insClaimParticipantCard** is in the list of cards.
        
    
    If the insClaimParticipantCard isn't there, you need to install it.
    
-   Create OmniScripts with the following types, subtypes, and purposes:
    
    -   Type: Claim, Subtype: Participant Add, Purpose: Add a new participant to a claim
        
    -   Type: Claim, Subtype: Participant Edit, Purpose: Edit an existing participant on a claim
        

[](https://help.salesforce.com/s?language=en_US)The Vlocity Claim Participant LWC contains all the UI elements claims adjusters see when they're working on participants and involved items on a claim.

[](https://help.salesforce.com/s?language=en_US)The insClaimParticipantsCard flex card contains only one element, which is configured with these properties:

[](https://help.salesforce.com/s?language=en_US)

-   Element Name: Custom LWC\_0
    
-   Custom Lwc Name: insClaimParticipants
    
-   Attribute/Value pair:
    
    -   Attribute: `recordId`
        
    -   Value: `{recordId}`
        

1.  From the App Launcher, find and select **Vlocity Flex Cards**.
2.  Scroll or search for **insClaimParticipantsCards**, then click the title in the list to see the versions.
3.  Open the version of insClaimParticipantsCards you want to base your customized card on.
4.  Click **Clone** to clone this card.
    1.  Give the cloned card a new **Card Name**.
    2.  (Optional but Recommended) Give the cloned card a new **Card Title**.
    3.  (Optional) Enter a description of this card that lets other administrators know what this card is and how to use it.
5.  (Optional) If you're using OmniScripts with different types and subtypes than the ones already mapped to the event listeners on the card, enter your OmniScripts into the **Event Listener** section.

[](https://help.salesforce.com/s?language=en_US)

-   [Add the Vlocity Claim Participants LWC to the Claim Record Page](https://help.salesforce.com/s/articleView?id=ind.insurance_add_the_vlocity_claim_participants_lwc_to_the_claimrecord_page_619353.htm&language=en_US&type=5 "After administrators configure the Vlocity Claim Participants LWC, they can add it to the Claim record page. Users can also add the Vlocity Claim Participants LWC to the page.")
    

Did this article solve your issue?

Let us know so we can improve!

YesNo