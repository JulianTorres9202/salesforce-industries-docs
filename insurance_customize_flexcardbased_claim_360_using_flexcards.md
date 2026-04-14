---
title: "Customize FlexCard-Based Claim 360 Using FlexCards"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_customize_flexcardbased_claim_360_using_flexcards.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize FlexCard-Based Claim 360 Using FlexCards

Customize FlexCard-Based Claim 360 Using FlexCards[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize FlexCard-Based Claim 360 Using FlexCards

To show claim information with clickable actions that change based on the information entered, customize the FlexCard components that you want to add to the record pages.

FlexCard Designer is a declarative tool that you can use to build Lightning web components easily without code. Build a FlexCard by dragging the elements onto the Lightning page canvas. You can create UI components with FlexCards by sourcing the data and showing and organizing the output in a meaningful way.

Clone and customize these FlexCards:

Parent FlexCards

-   InsuranceFSCISEClaim360
    
-   InsuranceFSCISEClaimTypeContainer
    
-   InsuranceFSCISEClaimContainer
    
-   InsuranceFSCISEClaimChild
    

Child FlexCards

-   FlexCards for Consolidated View
    
    -   InsuranceFSCISEConsolidatedViewChild
        
-   FlexCards for Claim Overview
    
    -   InsuranceFSCISEClamOverview
        
    -   InsuranceFSCISEOverviewClaimFlyout
        
    -   InsuranceFSCISEOverviewClaimOwnerChild
        
-   FlexCards for Claim Record Alerts
    
    -   InsuranceFSCISEClaimRecordAlertContainer
        
    -   InsuranceFSCISEClaimRecordAlertCard
        
-   FlexCards for Claim Items
    
    -   InsuranceFSCISEClaimItemsContainer
        
    -   InsuranceFSCISEClaimItemsChild
        
-   FlexCards for Claim Participants
    
    -   InsuranceFSCISEClaimParticipantsContainer
        
    -   InsuranceFSCISEClaimParticipantsChild
        
-   FlexCards for Claim Coverages
    
    -   InsuranceFSCISEClaimCoveragesContainer
        
    -   InsuranceFSCISEClaimCoveragesChild
        
-   FlexCard for Claim Payment Summary
    
    -   InsuranceFSCISEClaimPaymentSummaryChild
        
    -   InsuranceFSCISEClaimPaymentSummaryContainer
        

To customize a FlexCard

1.  From the App Launcher, find and select **OmniStudio**.
    
2.  In the OmniStudio app, from the navigation bar, select **OmniStudio FlexCards**.
    
3.  Select and clone a card.
    
4.  Customize and save the card.
    
5.  Activate the card.
    
    Important Before you embed a child FlexCard in a parent FlexCard, always activate the child card.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo