---
title: "What's In Issue Policy OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_whats_in_issue_policy_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# What's In Issue Policy OmniScript

What's In Issue Policy OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# What's In Issue Policy OmniScript

In the OmniScript Designer, the Issue Policy OmniScript has steps to get quote and payment information, to set payment, and to update status.

1.  getQuoteDetails
    
    -   Component type: Remote Action
        
    -   What it does: Fetches the data for the quote specified by the quote Id.
        
    -   Calls: [InsQuoteService: getQuoteDetail](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__getquotedetail.htm&language=en_US&type=5 "Use this service to get all of the quote details as JSON.")
        
2.  getQuoteInformation
    
    -   Component type: Omnistudio Data Mapper Extract Action
        
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
         

Did this article solve your issue?

Let us know so we can improve!

YesNo