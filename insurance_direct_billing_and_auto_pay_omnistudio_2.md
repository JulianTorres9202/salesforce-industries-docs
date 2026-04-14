---
title: "Direct Billing and Auto Pay"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_direct_billing_and_auto_pay_omnistudio_2.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Direct Billing and Auto Pay

Direct Billing and Auto Pay[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Direct Billing and Auto Pay

Policyholder, agents, and admin users can set up the option of either automatic payments for their insurance premiums or they can have bills sent directly to them and take responsibility of paying them on time.

## Direct Billing and Auto Pay OmniScript

The direct billing and auto pay OmniScript are available in the OmniStudio OmniScript Designer under Type/Subtype: insFSC/setUpDirectBilling and Version: SetUpDirectBilling.

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

Retrieves date from InsPolicy and Policy. It then converts the data so that it can be displayed to the user.

 | 

InsGetPolicyDetails

 |
| 

getAccountInformation

 | 

Data Mapper Extract Action

 | 

Extracts data from Account and converts it to JSON output.

 | 

Ins\_ReadAccountDetails\_PaymentPlanOS

 |
| 

billingOptionsSetUp

 | 

Step

 | 

Displays the form for the user to select a billing option.

 | 

None

 |
| 

billMethod

 | 

Step

 | 

Displays the form for the user to select a payment method.

 | 

None

 |
| 

setUpPaymentMethods

 | 

Step

 | 

Displays the form for the user to enter more information about the payment method.

 | 

OneTimePayment

 |
| 

createPaymentMethod

 | 

Data Mapper Post Action

 | 

Takes the user data and assigns it to fields in setUpPaymentMethods.

 | 

Ins\_PostPaymentMethod\_FSCPaymentPlansOS

 |
| 

setUpPaymentMode

 | 

Step

 | 

Displays the form to select a payment frequency.

 | 

None

 |
| 

createBillingAccountAutoPay

 | 

Data Mapper Post Action

 | 

If the user selected Auto pay, this component takes the user data and assigns it to fields in billMethod and setUpPaymentMode.

 | 

Ins\_PostFSCBillingAccount\_PaymentPlanOS

 |
| 

createBillingAccountDirectBill

 | 

Data Mapper Post Action

 | 

If the user selected direct billing, this component takes the user data and assigns it to fields in billMethod and setUpPaymentMode.

 | 

ns\_PostFSCDirectBillingAccount\_PaymentPlanOS

 |
| 

updatePolicyBillingDetails

 | 

Data Mapper Post Action

 | 

Assigns values to the payment due date and frequency.

 | 

updatePolicyDetails\_BillingSetUpOS

 |
| 

transformForConfirmation

 | 

Data Mapper Transform Action

 | 

Retrieves details from policydetails and converts it to JSON to be displayed in the confirmation FlexCard.

 | 

transForConfirmation\_DirectBillingOS

 |
| 

confirmationStep

 | 

Step

 | 

Displays a payment confirmation message to the user.

 | 

None

 |

-   **[Set Up Direct Billing](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_direct_billing_omnistudio.htm&language=en_US&type=5)**  
    Policyholders, agents, and admin users can set up direct billing from the Lex Console.
-   **[Set Up Auto Pay](https://help.salesforce.com/s/articleView?id=ind.insurance_set_up_auto_pay_omnistudio.htm&language=en_US&type=5)**  
    Policyholders, agents, and admin users can set up automatic payments from the Lex Console.

Did this article solve your issue?

Let us know so we can improve!

YesNo