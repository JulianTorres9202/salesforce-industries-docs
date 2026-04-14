---
title: "Issue Policy OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_issue_policy_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Issue Policy OmniScript

Issue Policy OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Issue Policy OmniScript

You can launch the Issue Policy OmniScript from the following applications, where it can be accessed by the types of users described.

[](https://help.salesforce.com/s?language=en_US)

-   Broker Portal (Newport)
    
    Brokers and agents
    
-   Interaction Console (Lightning)
    
    Internal insurance agents and call center reps
    
-   Vlocity Admin Lightning Experience (Newport)
    
    -   Internal insurance agents
        
    -   Vlocity admins
        

[](https://help.salesforce.com/s?language=en_US)These OmniScripts now write to the native Financial Services Cloud Insurance Policy object instead of the Asset object. For more information, see [Financial Services Cloud Integration](https://docs.vlocity.com/en/financial-services-catalog-integration.html).

Now let's go through the Issue Policy OmniScript step by step.

First, the OmniScript takes a quote Id and uses the [InsQuoteService:](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.") getQuoteDetailservice to retrieve the data for the quote the user wants to issue a policy for.

It then displays information about the quote, including the premium price and the term of the insurance policy to be purchased.

Depending on which payment option the user chooses, the step tree on the right changes. The steps a user takes to create payment information changes based on the choices they make. In the following example, the user chose Payment Plan.

After the user chooses Payment Plan and clicks Next, this OmniScript calls another Omniscript named ins/SetupPaymentPlan PaymentPlanSetup1. The PaymentPlanSetup1 OmniScript takes the user through the forms and choices necessary to set up all their payment information for the policy.

Note

To make it easy to test this functionality, we use a Lightning Web Component built to integrate with Braintree. Braintree lets us either add testable credit card numbers or click Next. The OmniScript sees the payment inputs as valid and lets the user go on to the next step.

You can remove or modify the Braintree Lightning Web Component if you clone and use this OmniScript in a production environment.

After the payment is authorized, the IssuePolicy OmniScript calls the [InsPolicyService: createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.") service to create the policy record.

An Omnistudio Data Mapper Extract action reads the policy record, and the OmniScript displays a confirmation that the policy is active.

**Now let's go through the same flow, with the user making different choices.**

In the same Confirm Quote Details page at the beginning of the previous flow, the user chooses Pay in Full.

Then the user chooses the Electronic Check option as their payment method. This OmniScript calls another Omniscript named ins/IssuePayment1. The IssuePayment1 OmniScript takes the user through the forms and choices necessary to get all their payment information to pay for the policy right now.

The user can choose Credit Card or Electronic Check. In this example, the user chose Electronic Check.

The IssuePayment1 OmniScript integrates with an ACH system to take the customer's bank account information and authorize the payment.

Note

The achAuthorization step in the IssuePayment1 OmniScript is set up to accept and authorize test data.

You can modify this step in the OmniScript you create or extend.

After the payment is authorized, the IssuePolicy OmniScript calls the [InsPolicyService: createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.") service to create the policy record.

A Data Mapper Extract action reads the policy record, and the OmniScript displays a confirmation that the policy is active.

Did this article solve your issue?

Let us know so we can improve!

YesNo