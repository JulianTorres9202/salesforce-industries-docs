---
title: "How Does Property Claims Initiate Recovery Work"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_how_does_property_claims_initiate_recovery_work_519555.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# How Does Property Claims Initiate Recovery Work

How Does Property Claims Initiate Recovery Work[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How Does Property Claims Initiate Recovery Work

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

1.  Navigate to the **Financials** tab of the claim record.
2.  Click **Initiate Recovery**.
3.  Select the coverages to initiate recovery and click **Next**.
4.  Select the coverage to add recovery details.
5.  Enter the details and click **Save**. When you're done, click **Next**.
6.  That's it! The recovery is initiated and you see a confirmation.
7.  Now navigate to the **Related** tab on the claim record and scroll down to **Claim Recoveries**.
8.  Open the claim recovery record you just created and click the pencil icon in the **Recovered Amount** field.
9.  Enter the recovered amount and click **Save**.
10.  If the recovered amount is equal to the estimated amount, the Status changes to **Accepted Recovery**.

Did this article solve your issue?

Let us know so we can improve!

YesNo