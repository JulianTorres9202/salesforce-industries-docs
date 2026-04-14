---
title: "Property Overview"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_property_overview_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Property Overview

Property Overview[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Property Overview

The Property line of business provides a fully functional example of Homeowners and Renters product models, rating procedures, and business processes for quoting, issuing, modifying, and canceling policies.

This line of business application can be used for reference or as the base for the development of product models and business processes.

This guide will orient you to the contents of the org and the business process for personal property insurance.

[](https://help.salesforce.com/s?language=en_US)

## Product Models and Rating Procedures

The product models and rating procedures Property are:

-   Product Model: Homeowners (HO3)
    
    Rating Procedure: propHO3RatingProcedure
    
-   Product Model: Renters (HO4)
    
    Rating Procedure: propHO4RatingProcedure
    

These product models and the rating procedures that calculate prices for these products at runtime underpin all the business processes in this line of business.

The product model provides the structure for the data JSON that moves through the business processes. Both the Homeowners and Renters product models are single-instance, which means that we intend customers to insure only one home per policy.

Both Homeowners and Renters also include a Scheduled Items child insured item under the Home insured item. This creates a parent > child > grandchild product structure.

To learn more about these product models, see [Property Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_property_product_model_516441.htm&language=en_US&type=5 "The product models underpin all the business processes used in the Property line of business. The name of these product models are:").

The rating procedures take information from the prospective customer (that becomes attribute values in the data JSON) during quoting business processes. The procedures calculate the prices for coverages, then the product model rating simulation rolls up those prices and calculates the total premium.

To learn more about these rating procedures, see [Property Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_property_rating_517293.htm&language=en_US&type=5 "When we quote and endorse the Homeowners and Renters products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The service does the following:").

We hope that by looking deeply at the product models and rating procedures in this line of business, you'll get ideas of how we built them that will help you when it's time to build your own property products.

[](https://help.salesforce.com/s?language=en_US)

## Business Processes

These processes guide prospective customers (and agents and brokers helping those prospects) to get a rated quote for a property product, to issue a policy for that quote, and to cancel a policy.

-   [Homeowners Quote](https://help.salesforce.com/s/articleView?id=ind.insurance_property_quote_business_process_517662.htm&language=en_US&type=5 "We've created a quote business process for Homeowners and Renters insurance for you to examine, use as examples, and extend to create your own business processes for property insurance in Vlocity.")
    
-   [Issue Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_policy_business_processes.htm&language=en_US&type=5 "We've created an Issue Policy business process that takes a quote and issues an insurance policy. This business process is reused across multiple lines of business.")
    
-   [Cancel Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_cancel_policy_business_process.htm&language=en_US&type=5 "The policy cancelation business process lets brokers and policyholders cancel an in-force policy. The policyholder receives a refund for the unutilized premium on the policy, which is calculated based on the policy effective date and the effective date of the cancelation transaction.")
    

The Homeowners Quote business process includes several sub-processes that help make it work and add functionality, such as the ability to email quote documents to a prospect.

[](https://help.salesforce.com/s?language=en_US)

## What's Next

Now that you've got a high-level intro to Property, take a look at the [Property Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_property_product_model_516441.htm&language=en_US&type=5 "The product models underpin all the business processes used in the Property line of business. The name of these product models are:").

-   **[Property Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_property_product_model_omnistudio.htm&language=en_US&type=5)**  
    The product models underpin all the business processes used in the Property line of business. The name of these product models are:
-   **[Property Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_property_attribute_catalog_omnistudio.htm&language=en_US&type=5)**  
    We use a whole lot of attributes to build the products for this Application. In this catalog, each Attribute Category has a table, with all its attributes listed.
-   **[Property Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_property_rating_omnistudio.htm&language=en_US&type=5)**  
    When we quote and endorse the Homeowners and Renters products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The service does the following:
-   **[State Models](https://help.salesforce.com/s/articleView?id=ind.insurance_state_models_omnistudio.htm&language=en_US&type=5)**  
    All Property & Casualty Application Suite lines of business use state models to underpin their workflow and claim (underwriting) rules. Vlocity Insurance uses state models to transition a quote, a policy, or a claim from one state to another when a rule evaluates to true.
-   **[Property Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_property_quote_business_process_omnistudio.htm&language=en_US&type=5)**  
    We've created a quote business process for Homeowners and Renters insurance for you to examine, use as examples, and extend to create your own business processes for property insurance in Vlocity.
-   **[Issue Policy Business Processes](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_policy_business_processes_omnistudio.htm&language=en_US&type=5)**  
    We've created an Issue Policy business process that takes a quote and issues an insurance policy. This business process is reused across multiple lines of business.
-   **[Renew Policy Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_renew_policy_business_process_omnistudio.htm&language=en_US&type=5)**  
    When it's time to renew your policy, you get an email with a renewal link. Then all you have to do is enter some details for the renewal and it's all done. It's that simple! Carry on reading to find out details of this process.
-   **[Cancel Policy Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_cancel_policy_business_process_omnistudio.htm&language=en_US&type=5)**  
    The policy cancelation business process lets brokers and policyholders cancel an in-force policy. The policyholder receives a refund for the unutilized premium on the policy, which is calculated based on the policy effective date and the effective date of the cancelation transaction.
-   **[Direct Billing and Auto Pay](https://help.salesforce.com/s/articleView?id=ind.insurance_direct_billing_and_auto_pay_omnistudio.htm&language=en_US&type=5)**  
    Policyholder, agents, and admin users can set up the option of either automatic payments for their insurance premiums or they can have bills sent directly to them and take responsibility of paying it on time.
-   **[One-Time Payment for Policy Premium](https://help.salesforce.com/s/articleView?id=ind.insurance_one_time_payment_for_policy_premium_omnistudio.htm&language=en_US&type=5)**  
    Policyholder and admin users can now pay monthly or quarterly premiums directly from the policy in the Lex Console. Read on for instructions on how to make a one-time payment.

Did this article solve your issue?

Let us know so we can improve!

YesNo