---
title: "Customize FlexCard-Based Claim 360 Using Data Mappers"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_customize_flexcardbased_claim_360_using_datamappers.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize FlexCard-Based Claim 360 Using Data Mappers

Customize FlexCard-Based Claim 360 Using Data Mappers[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize FlexCard-Based Claim 360 Using Data Mappers

If you want to include policy and claim details from a third-party system, get your developer to create an Apex class that makes the data available to FlexCard-based Claim 360. Then, customize the Omnistudio Data Mappers to reference the Apex class.

You can customize these Data Mappers as needed:

-   InsuranceFSCISEDismissAlert
    
-   InsuranceFSCISEGetPaginatedClaimsForHousehold
    
-   InsuranceFSCISEGetPaginatedClaimsForNonHousehold
    
-   InsuranceFSCISEReadClaimHouseholdKPI
    
-   InsuranceFSCISEReadClaimHouseholdType
    
-   InsuranceFSCISEReadHouseholdTypesForFlyout
    
-   InsuranceFSCISEReadClaimItemsByClaimId
    
-   InsuranceFSCISEReadClaimNonHouseholdKPI
    
-   InsuranceFSCISEReadClaimNonHouseholdSearch
    
-   InsuranceFSCISEReadClaimNonHouseholdType
    
-   InsuranceFSCISEReadClaimNonHouseholdTypesForFlyout
    
-   InsuranceFSCISEReadClaimsByInsuredId
    
-   InsuranceFSCISEReadCoveragesByClaimId
    
-   InsuranceFSCISEReadHouseholdAccClaimSearch
    
-   InsuranceFSCISEReadHouseholdClaimsByInsuredId
    
-   InsuranceFSCISEReadParticipantsByClaimId
    
-   InsuranceFSCISEReadPaymentSummaryByClaimId
    
-   InsuranceFSCISEReadRecordAlertsByClaimId
    
-   InsuranceFSCISESnoozeAlerts
    

To customize a Data Mapper:

1.  In the OmniStudio app, from the navigation bar, select **Omnistudio Data Mappers**.
    
2.  Select the Data Mapper that you want to customize.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo