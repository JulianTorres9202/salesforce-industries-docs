---
title: "One-Time Payment for Policy Premium"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_one-time_payment_for_policy_premium_reference_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# One-Time Payment for Policy Premium

One-Time Payment for Policy Premium[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# One-Time Payment for Policy Premium

Policyholder and admin users can now pay monthly or quarterly premiums directly from the policy in the Lex Console. Read on for instructions on how to make a one-time payment.

This option is not available for annual payments as that is handled in the [Issue Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_policy_business_processes_omnistudio_2.htm&language=en_US&type=5 "We've created an Issue Policy business process that takes a quote and issues an insurance policy. This business process is reused across multiple lines of business.") business process.

The one-time payment OmniScript is:

-   Type/Subtype: insFSC/policypayment
    
-   Version: LWC-PolicyPayment
    

The one-time payment option is visible on the Lex Console for policies where the paid-to date is earlier than today. This means that the tenure of the previous payment should have ended any time before the day you want to make the next payment.

Here's what's in OmniScript:

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

getPolicyDetails

 | 

Omnistudio Data Mapper Extract Action

 | 

Retrieves date from InsurancePolicy and converts it to data that can be displayed to the user.

 | 

Ins\_ExtFSCPolicyPaymentInfo\_billPayOS

 |
| 

policydetails

 | 

Step

 | 

Displays the policy details to the user along with payment options.

 | 

None

 |
| 

ach

 | 

Step

 | 

If selected by the user, displays a form to collect electronic check payment details.

 | 

None

 |
| 

CreditCard

 | 

Step

 | 

If selected by the user, displays a form to collect credit card details.

 | 

None

 |
| 

applyPayment

 | 

Integration Procedure Action

 | 

Creates a premium transaction and also reactivates a Pending Lapse policy if the premium paid is more than the requisite amount for that term.

 | 

OneTimePayment

 |
| 

transformForConfirmation

 | 

Data Mapper Transform Action

 | 

Retrieves details from policydetails and converts it to JSON to be displayed in the confirmation FlexCard.

 | 

ins\_transformForPaymentConfirmationOS

 |
| 

paymentConfirmation

 | 

Step

 | 

Displays a payment confirmation message to the user.

 | 

None

 |

-   **[Make a One-Time Payment for Policy Premium](https://help.salesforce.com/s/articleView?id=ind.insurance_make_a_one-time_payment_for_policy_premium_omnistudio.htm&language=en_US&type=5)**  
    Policyholders and admin users can perform the payment from the Lex Console:

Did this article solve your issue?

Let us know so we can improve!

YesNo