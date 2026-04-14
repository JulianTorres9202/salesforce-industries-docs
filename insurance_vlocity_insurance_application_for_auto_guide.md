---
title: "Insurance Application for Auto Guide"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_application_for_auto_guide.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Application for Auto Guide

Insurance Application for Auto Guide[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Application for Auto Guide

The Insurance Application for Property & Casualty includes a fully functioning policy administration and claims system for multi-auto, multi-driver auto insurance.

[](https://help.salesforce.com/s?language=en_US)

This Application can be used for reference or as the base for the development of product models and business processes.

This guide will orient you to the contents of the org and the business process for auto insurance.

[](https://help.salesforce.com/s?language=en_US)

## Product Modeling, Rating, and Business Processes

The first major task a user does in Vlocity Insurance is product modeling. The product models you create define all the products you sell and service, and how Vlocity handles those products.

The next task is creating rating procedures to price the products you've modeled, then connecting those rating procedures to your products.

In the Vlocity Insurance Application for Property & Casualty, we've created several product models and rating procedures to price them. In this document, we'll be using the Multi Auto product model.

Now comes the fun part: Using the product models and rating procedures to create business processes to quote, sell, and service your insurance products.

Here are business processes available in the Vlocity Insurance Application for Property & Casualty that appear in this guide:

-   Quote
    
    Users can configure, price (rate), underwrite, and present quotes to end customers.
    
-   Issue Policy
    
    Users can choose payment schedules and methods, enter payment information, and issue an insurance policy.
    
-   Modify Policy (Add Endorsements/MTAs)
    
    Users can add endorsements to in-force policies by doing one or more of the following:
    
    -   Modify Coverages
        
    -   Add Vehicle
        
    -   Remove Vehicle
        
    -   Add Driver
        
    -   Remove Driver
        
-   Cancel Policy
    
    Users can cancel in-force policies and issue refunds to end customers as needed.
    

In addition to the business processes described in this guide, the Vlocity Insurance Application for Property & Casualty includes business processes for:

-   Renewing a policy
    
-   Filing a claim against a policy
    
-   Managing claims through the complete claims lifecycle
    

-   **[Auto Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_product_model_510402.htm&language=en_US&type=5)**  
    The product model underpins all the business processes used in the Auto line of business. This line of business offers two products namely **Multi Auto** and **Commercial Auto**.
-   **[Auto Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_attribute_catalog.htm&language=en_US&type=5)**  
    In this catalog, all attributes used for the Auto line of business are listed by Attribute Category. Each Attribute Category has its own table, which includes attribute codes and the product specs the attributes are used by.
-   **[Auto Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_rating_511129.htm&language=en_US&type=5)**  
    When we quote and endorse Auto products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages, vehicles, and total premium.  The service does the following to price the product:
-   **[State Models](https://help.salesforce.com/s/articleView?id=ind.insurance_state_models.htm&language=en_US&type=5)**  
    All Property & Casualty Application Suite lines of business use state models to underpin their workflow and claim (underwriting) rules. Vlocity Insurance uses state models to transition a quote, a policy, or a claim from one state to another when a rule evaluates to true.
-   **[Issue Policy Business Processes](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_policy_business_processes.htm&language=en_US&type=5)**  
    We've created an Issue Policy business process that takes a quote and issues an insurance policy. This business process is reused across multiple lines of business.
-   **[Renew Policy Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_renew_policy_business_process.htm&language=en_US&type=5)**  
    When it's time to renew your policy, you get an email with a renewal link. Then all you have to do is enter some details for the renewal and it's all done. It's that simple! Carry on reading to find out details of this process.
-   **[Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_business_process_omnistudio.htm&language=en_US&type=5)**  
    We've created a bunch of business processes for you to examine, use as examples, and extend to create your own business processes for auto insurance in Vlocity.
-   **[Endorsements/MTAs for Auto Business Processes](https://help.salesforce.com/s/articleView?id=ind.insurance_endorsements_mtas_for_auto_business_processes.htm&language=en_US&type=5)**  
    We've created a bunch of policy endorsement/MTA business processes for you to examine, use as examples, and extend to create your own endorsement/MTA business processes for auto insurance in Vlocity.
-   **[Cancel Policy Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_cancel_policy_business_process.htm&language=en_US&type=5)**  
    The policy cancelation business process lets brokers and policyholders cancel an in-force policy. The policyholder receives a refund for the unutilized premium on the policy, which is calculated based on the policy effective date and the effective date of the cancelation transaction.
-   **[Auto Claims Overview](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_overview_512944.htm&language=en_US&type=5)**  
    The Auto Application includes a suite of claims functionality that lets an insurer take in First Notice of Loss (FNOL) data, create and update claim records, and adjudicate claims.
-   **[Direct Billing and Auto Pay](https://help.salesforce.com/s/articleView?id=ind.insurance_direct_billing_and_auto_pay.htm&language=en_US&type=5)**  
    Policyholder, agents, and admin users can set up the option of either automatic payments for their insurance premiums or they can have bills sent directly to them and take responsibility of paying it on time.
-   **[One-Time Payment for Policy Premium](https://help.salesforce.com/s/articleView?id=ind.insurance_one_time_payment_for_policy_premium.htm&language=en_US&type=5)**  
    Policyholder and admin users can now pay monthly or quarterly premiums directly from the policy in the Lex Console. Read on for instructions on how to make a one-time payment.

Did this article solve your issue?

Let us know so we can improve!

YesNo