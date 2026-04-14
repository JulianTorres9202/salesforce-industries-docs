---
title: "Business Owners Policy Overview"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_policy_overview_519688.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Business Owners Policy Overview

Business Owners Policy Overview[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Business Owners Policy Overview

The Business Owners line of business gives you a fully functional example of Economy Business, and Superior Business product models, rating procedures, and business processes for quoting and issuing policies.

[](https://help.salesforce.com/s?language=en_US)

You can use this application for reference or as a base to develop your own product models and business processes.

[](https://help.salesforce.com/s?language=en_US)

## Product Models and Rating Procedures

These product models and the rating procedures that calculate prices for Business Owners products at runtime underpin all the business processes in this line of business:

-   Product Model: Economy Business
    
    Rating Procedure: BusinessOwnersPolicy
    
-   Product Model: Superior Business
    
    Rating Procedure: BusinessOwnersPolicy
    

The product model provides the structure for the data JSON that moves through the business processes. Both the Economy and Superior product models are single-instance, which means that we intend customers to insure only one business per policy. All coverages have been designed to be configured at the policy level.

To learn more about these product models, see [Business Owners Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_product_model_519730.htm&language=en_US&type=5 "To understand how the Business Owners' application works, you need to figure out how it's built. Read on to understand the Business Owners' product model.").

The rating procedures take information from the prospective customer (that becomes attribute values in the data JSON) during quoting business processes. The procedures calculate the prices for coverages, then the product model rating simulation rolls up those prices and calculates the total premium.

To learn more about these rating procedures, see [Business Owners Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_rating_520335.htm&language=en_US&type=5 "When we quote and endorse the Business Owners Policy products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:").

[](https://help.salesforce.com/s?language=en_US)

## Business Processes

These processes guide prospective customers (and agents and brokers helping those prospects) to get a rated quote for a business product, to issue a policy for that quote, and to cancel a policy:

-   [Quote PolicyBusiness Owners Quote OmniScript Flow](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_quote_omniscript_flow_520472.htm&language=en_US&type=5 "The quoting flow for Business Owners' insurance is run by the BOP Quote OmniScript. Depending on the user, this OmniScript from be launched from different applications.")
    
-   [Issue Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_issue_policy_business_processes.htm&language=en_US&type=5 "We've created an Issue Policy business process that takes a quote and issues an insurance policy. This business process is reused across multiple lines of business.")
    
-   [Cancel Policy](https://help.salesforce.com/s/articleView?id=ind.insurance_cancel_policy_business_process.htm&language=en_US&type=5 "The policy cancelation business process lets brokers and policyholders cancel an in-force policy. The policyholder receives a refund for the unutilized premium on the policy, which is calculated based on the policy effective date and the effective date of the cancelation transaction.")
    

These processes guide prospective customers (and agents and brokers helping those prospects) to get a rated quote for a business product, to issue a policy for that quote, and to cancel a policy.

The Business Owners Quote business process includes several sub-processes that help make it work and add functionality, such as the ability to email quote documents to a prospect.

[](https://help.salesforce.com/s?language=en_US)

## What's Next

Now that you've got a high-level intro to Business Owners Policy, take a look at the [Business Owners Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_product_model_519730.htm&language=en_US&type=5 "To understand how the Business Owners' application works, you need to figure out how it's built. Read on to understand the Business Owners' product model.").

-   **[Business Owners Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_product_model_519730.htm&language=en_US&type=5)**  
    To understand how the Business Owners' application works, you need to figure out how it's built. Read on to understand the Business Owners' product model.
-   **[Business Owners Rating](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_rating_520335.htm&language=en_US&type=5)**  
    When we quote and endorse the Business Owners Policy products, our pricing services use the product model data, product rating procedure, and pricing formulas. The services use these components to price the coverages. The services do the following:
-   **[Business Owners Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_business_owners_quote_business_process_520457.htm&language=en_US&type=5)**  
    We've created a quote business process for Business Owners for you to examine, use as examples, and extend to create your own business processes for business insurance in Vlocity.

Did this article solve your issue?

Let us know so we can improve!

YesNo