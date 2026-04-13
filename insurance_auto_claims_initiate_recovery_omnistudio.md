---
title: "Auto Claims Initiate Recovery"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_initiate_recovery_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Auto Claims Initiate Recovery

Auto Claims Initiate Recovery[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Auto Claims Initiate Recovery

Claims adjusters have the responsibility of deciding how much money can be given for each claim. With the Claim Adjuster App, users can now quickly create a recovery record from the claim record.

[](https://help.salesforce.com/s?language=en_US)

1.  Navigate to the **Financials** tab of the claim record.
2.  Click **Initiate Recovery**.
3.  Select the coverages to initiate recovery and click **Next**.
4.  Select the coverage to add recovery details, and click **Save**. When you're done, click **Next**.
5.  That's it! The recovery is initiated and you see a confirmation.
6.  Now navigate to the **Related** on the claim record and scroll down to **Claim Recoveries**.
7.  Select the claim recovery record you just created and click the pencil icon in the **Recovered Amount** field.
8.  Enter the recovered amount and click **Save**.
9.  If the recovered amount is equal to the estimated amount, the Status changes to **Accepted Recovery**.
    
    If the recovered amount is less than the estimated amount, the Status changes to **Accepted with Additional Pursuit**.
    
    The system automatically creates a new record for the amount that still needs to be recovered. You can edit this record again to enter the recovered amount and update the status.
    

-   **[How Auto Claims Initiate Recovery Works](https://help.salesforce.com/s/articleView?id=ind.insurance_how_auto_claims_initiate_recovery_works_omnistudio.htm&language=en_US&type=5)**  
    The claim recovery workflow is built using the ClaimRecovery OmniScript. You can find this OmniScript in OmniStudio OmniScripts under Type/Subtype: ins/ClaimRecovery and OmniScript Name: ClaimRecovery.

Did this article solve your issue?

Let us know so we can improve!

YesNo