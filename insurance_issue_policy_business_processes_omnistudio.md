---
title: "Issue Policy Business Processes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_issue_policy_business_processes_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Issue Policy Business Processes

Issue Policy Business Processes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Issue Policy Business Processes

We've created an Issue Policy business process that takes a quote and issues an insurance policy. This business process is reused across multiple lines of business.

[](https://help.salesforce.com/s?language=en_US)

All our screenshots are currently in Lightning style. Your spin may look different because it's using the Newport style in the Broker Portal and Customer Portal.

[](https://help.salesforce.com/s?language=en_US)

## Issue Policy OmniScript

You can launch this OmniScript from the following applications, where it can be accessed by the types of users described:

[](https://help.salesforce.com/s?language=en_US)

-   Broker Portal (Newport)
    
    Brokers and agents
    
-   Interaction Console (Lightning)
    
    Internal insurance agents and call center reps
    
-   Vlocity Admin Lightning Experience (Newport)
    
    -   Internal insurance agents
        
    -   Vlocity admins
        

[](https://help.salesforce.com/s?language=en_US)These OmniScripts now write to the native Financial Services Cloud Insurance Policy object instead of the Asset object.

Now let's go through the Issue Policy OmniScript step by step.

First, the OmniScript takes a quote Id and uses the [InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.") service to retrieve the data for the quote the user wants to issue a policy for.

It then displays information about the quote, including the premium price and the term of the insurance policy to be purchased.

Depending on which payment option the user chooses, the step tree on the right changes. The steps a user takes to create payment information changes based on the choices they make. In the following example, the user chose Payment Plan.

After the user chooses Payment Plan and clicks Next, this OmniScript calls another Omniscript named ins/SetupPaymentPlan PaymentPlanSetup1. The PaymentPlanSetup1 OmniScript takes the user through the forms and choices necessary to set up all their payment information for the policy.

Note

To make it easy to test this functionality, we use a Lightning Web Component built to integrate with Braintree. Braintree lets us either add testable credit card numbers or click Next. The OmniScript sees the payment inputs as valid and lets the user go on to the next step.

You can remove or modify the Braintree Lightning Web Component if you clone and use this OmniScript in a production environment.

After the payment is authorized, the IssuePolicy OmniScript calls the [InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.") service to create the policy record.

An Omnistudio Data Mapper Extract action reads the policy record, and the OmniScript displays a confirmation that the policy is active.

Now let's go through the same flow, with the user making different choices.

In the same Confirm Quote Details page at the beginning of the previous flow, the user chooses Pay in Full.

Then the user chooses the Electronic Check option as their payment method. This OmniScript calls another Omniscript named ins/IssuePayment1. The IssuePayment1 OmniScript takes the user through the forms and choices necessary to get all their payment information to pay for the policy right now.

The user can choose Credit Card or Electronic Check. In this example, the user chose Electronic Check.

The IssuePayment1 OmniScript integrates with an ACH system to take the customer's bank account information and authorize the payment.

Note

The achAuthorization step in the IssuePayment1 OmniScript is set up to accept and authorize test data.

You can modify this step in the OmniScript you create or extend.

After the payment is authorized, the IssuePolicy OmniScript calls the [InsPolicyService:createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.") service to create the policy record.

A Data Mapper Extract action reads the policy record, and the OmniScript displays a confirmation that the policy is active.

[](https://help.salesforce.com/s?language=en_US)

## What's In It

Here's what the steps look like in the OmniScript Designer:

1.  getQuoteDetails
    
    -   Component type: Remote Action
        
    -   What it does: Fetches the data for the quote specified by the quote Id.
        
    -   Calls: [InsQuoteService:getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")
        
2.  getQuoteInformation
    
    -   Component type: Data Mapper Extract Action
        
    -   What it does: Extracts product and account information from the quote.
        
    -   Calls: Ins\_ExtrQuoteDetails\_IssueOS
        
3.  setQuoteInformation
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Set Values
        
    -   What it does: Sets values for a number of quote elements
        
    -   Calls: None
        
4.  quoteDetails
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Step
        
    -   What it does: Includes the following subcomponents:
        
        -   quoteNumber
            
        -   quoteEffectiveDate
            
        -   quotePremium
            
        -   quoteTerm
            
        -   billType
            
    -   Calls: None
        
5.  paymentPlanSetUp1
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: OmniScript
        
    -   What it does: Calls another OmniScript that lets the user set up a payment plan.
        
    -   Calls: ins/SetupPaymentPlan OmniScript
        
6.  setPaymentAmount
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Set Values
        
    -   What it does: Sets values for a number of billing elements.
        
    -   Calls: None
        
7.  IssuePayment1
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: OmniScript
        
    -   What it does: Lets a user pay their premium in real time.
        
    -   Calls: ins/IssuePayment OmniScript
        
8.  createUpdatePolicy
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Integration Procedure Action
        
    -   What it does: Creates a policy record.
        
    -   Calls: Insurance\_CreatePolicy Integration Procedure
        
9.  applyPremiumPayment
    
    [](https://help.salesforce.com/s?language=en_US)
    -   Component type: Integration Procedure Action
        
    -   What it does: Applies a premium paid via the IssuePayment OmniScript in step 7 to the policy record.
        
    -   Calls: Insurance\_IssuePayment
        
10.  readPolicyforconfirmation
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Data Mapper Extract Action
         
     -   What it does: Extracts data about the policy, the product, and the payment.
         
     -   Calls: readPolicyLwc
         
11.  UpdateQuoteStatus
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Data Mapper Post Action
         
     -   What it does: Updates the quote status.
         
     -   Calls: UpdateQuoteStatus
         
12.  CreatePolicyParties
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Integration Procedure Action
         
     -   What it does: Creates a record of the policyholder as a party.
         
     -   Calls: PolicyholderParty\_Create Integration Procedure
         
13.  CreateProducerParty
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Integration Procedure Action
         
     -   What it does: Creates a party record for the broker who sold the insurance policy.
         
     -   Calls: ProducerParty\_Create
         
14.  policyConfirmation
     
     [](https://help.salesforce.com/s?language=en_US)
     -   Component type: Step
         
     -   What it does: Contains the following subcomponents:
         
         1.  Congrats: A Text Block that congratulates the user on purchasing the policy.
             
         2.  CustomLWC1
             
             -   Component type: Custom LWC
                 
             -   What it does: Displays confirmation of the policy purchase, with purchase data.
                 
             -   Calls: vlocity\_ins\_\_insOsConfirmation
                 
         3.  textBlock2: A Text Block that includes contact information for the insurer.
             
         4.  viewPolicy
             
             -   Component type: Navigate Action
                 
             -   What it does: Provides navigation
                 
     -   Calls: None
         

[](https://help.salesforce.com/s?language=en_US)

## Issue Policy from the Quote UI

A customer service rep or internal insurance agent with access to the Quote UI can issue policies from that UI. This example shows policies issued from the Quote UI using out-of-the-box LWC-based components from an existing quote.

Here's what it looks like step by step:

Start on the Quote list page. Choose the quote you want to issue a policy for.

On the Quote UI, click Issue Policy - Native.

On the Issue Policy window, make any changes you want and click Create.

Vlocity creates the policy and displays a success message on the Quote UI.

You can also launch the OmniScript described in the previous section from the Quote UI. Click Issue Policy to launch this OmniScript.

Did this article solve your issue?

Let us know so we can improve!

YesNo