---
title: "How Does Auto Claims Initiate Recovery Work"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_how_does_auto_claims_initiate_recovery_work.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# How Does Auto Claims Initiate Recovery Work

How Does Auto Claims Initiate Recovery Work[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How Does Auto Claims Initiate Recovery Work

The claim recovery workflow is built using the ClaimRecovery OmniScript. You can find this OmniScript in OmniStudio OmniScripts under:

-   Type/Subtype: ins/ClaimRecovery
    
-   OmniScript Name: ClaimRecovery
    

Here's a look at each component in the OmniScript:

| 
Component Name

 | 

Component Type

 | 

What It Does

 | 

What It Calls

 |
| --- | --- | --- | --- |
| 

getClaimId

 | 

DataRaptor Extract Action

 | 

It extracts details of the claim payment.

 | 

ins\_ClaimDataRecoveryExtract

 |
| 

SelectionBlock

 | 

Step

 | 

Displays the screen to select coverage items to initiate recovery.

 | 

None

 |
| 

getRecoveryData

 | 

DataRaptor Transform Action

 | 

Transforms the claim data into a more suitable format.

 | 

insTransformRecoveryData

 |
| 

RecoveryData

 | 

Step

 | 

[](https://help.salesforce.com/s?language=en_US)Displays the screen to enter recovery details.

 | 

None

 |
| 

AccountProcessing

 | 

Integration Procedure

 | 

Gets payment details, creates a new account (if required), and transforms the data into a condensed format.

 | 

ins\_AccountProcessing

 |
| 

StepConfirmation

 | 

Step

 | 

Displays the confirmation screen with the details of the recovery record initiated.

 | 

None

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo