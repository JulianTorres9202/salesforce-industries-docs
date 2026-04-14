---
title: "Customize FlexCard-Based Claim 360 by Using Integration Procedures"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_customize_flexcardbased_claim_360_by_using_integration_procedures.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize FlexCard-Based Claim 360 by Using Integration Procedures

Customize FlexCard-Based Claim 360 by Using Integration Procedures[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize FlexCard-Based Claim 360 by Using Integration Procedures

Customize integration procedures in OmniStudio.

OmniStudio Integration Procedures are declarative, server-side processes that run multiple actions in a single-server call. Integration procedures can read and write data from Salesforce and external systems using REST API calls and call Apex code.

You can customize these integration procedures:

-   InsuranceFSCISE\_GetConsolidatedClaimsCount\_Procedure
    
    -   Customize the claim consolidation behavior, such as read, count, and merge claims for household and non-household accounts.
        
-   InsuranceFSCISE\_ReadAccountClaims\_Procedure
    
    -   Customize the claim count and claim filtering options based on the claim status.
        
-   InsuranceFSCISE\_ReadAllClaimsForConsolidatedView\_Procedure
    
    -   Customize the pagination behavior when you plan to show a consolidated view of all claims.
        
-   InsuranceFSCISE\_ReadClaimKPIdetails\_Procedure
    
    -   Customize the grouping and merging criteria for claims based on the claim status.
        
-   InsuranceFSCISE\_ReadClaimsForHouseholdAccount\_Procedure
    
    -   Customize the criteria to retrieve claims and assets related to household accounts.
        
-   InsuranceFSCISE\_ReadClaimsForNonHouseholdAccount\_Procedure
    
    -   Customize the criteria to retrieve claims and assets related to non-household accounts.
        
-   InsuranceFSCISE\_ReadClaimsTypesFromAccount\_Procedure
    
    -   Customize the criteria to show the types of claims that are available for user accounts.
        
-   InsuranceFSCISE\_ReadRecordAlertsDismiss\_Procedure
    
    -   Customize the criteria to dismiss record alerts.
        
-   InsuranceFSCISE\_ReadRecordAlertsSnooze\_Procedure
    
    -   Customize the criteria to snooze record alerts.
        

To customize an integration procedure:

1.  From the App Launcher, find and select **OmniStudio**.
    
2.  In the OmniStudio app, from the navigation bar, select **OmniStudio Integration Procedures**.
    
3.  To customize an integration procedure, click **Procedure**.
    

## See Also

[OmniStudio Integration Procedures](https://help.salesforce.com/s/articleView?id=xcloud.os_omnistudio_integration_procedures_48334.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo