---
title: "Harmonized Auto FNOL Claims Process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_harmonized_auto_fnol_claims_process_4773.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Harmonized Auto FNOL Claims Process

Harmonized Auto FNOL Claims Process[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Harmonized Auto FNOL Claims Process

This business process writes to the harmonized Claims process which now supports both the existing Vlocity and FSC object model (custom objects in managed package) and the new Salesforce object model (standard Salesforce objects).

**Where:** This feature is available in the Insurance Application Suite under Property and Casualty Application. This harmonized workflows are available to anyone with a Salesforce FSC license.

[](https://help.salesforce.com/s?language=en_US)**Why:** The Claims object is now mapped to the new harmonized Claims object that supports both the existing Vlocity object model (custom objects in managed package) and the new Salesforce object model (standard Salesforce objects). For more information on the new harmonized claims object, see [Claims Harmonization](https://help.salesforce.com/s/articleView?id=ind.insurance_claims_harmonization_overview_600908.htm&language=en_US&type=5 "Claims harmonization involves moving claims data from custom objects in the Vlocity managed package object model to standard objects in the Salesforce object model. The Vlocity model supports the Asset → InsuranceClaim relationship between policies and claims. The Salesforce model supports the InsurancePolicy → Claim relationship between policies and claims. Services and LWCs are updated to work with claims data in the Salesforce data model.").

**How:** The Harmonized Auto FNOL Claims Process is built using an OmniScript. You can find the renew policy OmniScript in the OmniStudio OmniScript Designer under:

[](https://help.salesforce.com/s?language=en_US)

-   Type: **lwcauto**
    
-   Subtype: **FNOL**
    
-   Version name: **MultiAutoClaimFNOL**
    

Did this article solve your issue?

Let us know so we can improve!

YesNo