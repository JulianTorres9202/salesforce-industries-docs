---
title: "Insurance Quoting"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quoting_611024.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Quoting

Insurance Quoting[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Quoting

To estimate how much a policy would cost, you use a quote. Create a quote by selecting products offered by the provider and using information supplied by the customer to calculate the estimate. The Insurance quoting solution brings everything you need right to your fingertips and does all of the heavy lifting for you.

Insurance issues policies from quotes. Think of a quote as the foundation on which you build the policy.

Three key aspects of quoting are addressed by corresponding Insurance components: product modeling, rating, and quoting processes. All three play a role to deliver the full quoting solution.

[](https://help.salesforce.com/s?language=en_US)

## Product Modeling

Product Modeling (part of Product Management) supports defining the product or plan to offer, its characteristics, and the details that affect the rating calculation.

When you generate a quote, it pulls the data and configurations from the product model into the quote record. The product model is where you configure what attribute values a user sees. When creating a quote, users can select and modify values of attributes based on the configurations set on the product model.

[Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_rules_606729.htm&language=en_US&type=5 "Rules define the way Insurance products behave when those products are quoted, sold, and serviced.") and taxes and fees are also set up on the product model.

See [Build Insurance Product Models](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_product_models_603786.htm&language=en_US&type=5 "An insurance product model is a structured definition of a product that a company sells, then services. A product model acts as a blueprint for an insurance product.") to learn more.

[](https://help.salesforce.com/s?language=en_US)

## Rating

A rating is a risk-based calculation of a premium based on a set of input characteristics. For example, in an auto insurance policy, rating input characteristics include the type of vehicle, number of miles driven annually, and safety features of the car. Ratings determine the cost a customer needs to pay in order for the insurance carrier to take on the risk of that customer.

The rating procedure prices the product(s), then sends the prices to the quote for the user to see. Every coverage price, insured item price, and total premium comes from the rating procedure.

See [Learn About Rating Procedures](https://help.salesforce.com/s/articleView?id=ind.insurance_rating_procedures.htm&language=en_US&type=5 "Rating procedures are the backbone of insurance pricing. Learn how services, product models, and rating procedures work together to price insurance products.") to learn more.

[](https://help.salesforce.com/s?language=en_US)

## Quoting Processes

Product modeling and rating work together for the quoting processes and create the final quote. Quoting processes use services to find products and rate them.

Here's the basic flow a quoting process follows:

1.  [](https://help.salesforce.com/s?language=en_US)The user enters information about who and what needs insurance coverage.
    
2.  [](https://help.salesforce.com/s?language=en_US)The system uses the `getRatedProducts` service to find, rate, and display applicable product(s) and the prices for those products.
    
3.  The user chooses one or more insurance products.
    
4.  The system creates the initial quote record.
    
5.  The user customizes attributes, chooses optional coverages, and makes any other available modifications.
    
6.  The system updates the quote record and runs rules, then confirms the final quote to the user.
    

You can build quoting processes for your users in two ways: Lightning web components and OmniScripts. Lightning web components make up the processes that your internal users can use to create quotes for your customers. Use OmniScripts to create processes to guide your external users (like customers and partners). LWCs and OmniScripts both use [services](https://help.salesforce.com/s/articleView?id=ind.insurance_insurance_and_health_insurance_services_catalog.htm&language=en_US&type=5 "Get quote, policy, and claims systems up and running by using an extensive catalog of Digital Insurance Platform services. The services are methods of Apex classes that carry out common actions for insurance companies and health plans. They help you build end-to-end business processes faster by reducing or eliminating the need for custom programming.") to pull product and rating information into the quoting process.

[](https://help.salesforce.com/s?language=en_US)

## Bringing It All Together

Check out [Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_quote_business_process_omnistudio.htm&language=en_US&type=5 "We've created a bunch of business processes for you to examine, use as examples, and extend to create your own business processes for auto insurance in Vlocity.") as an example of an auto quoting business process (from our Insurance Property and Casualty Application Suite) to see OmniScripts and the Quote LWC in action.

[](https://help.salesforce.com/s?language=en_US)

## Next Steps

Want to see another quoting example? Check out [Property Quote Business Process](https://help.salesforce.com/s/articleView?id=ind.insurance_property_quote_business_process_517662.htm&language=en_US&type=5 "We've created a quote business process for Homeowners and Renters insurance for you to examine, use as examples, and extend to create your own business processes for property insurance in Vlocity.").

Ready to try quoting for yourself? See [Single Root Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_single_root_quoting_612298.htm&language=en_US&type=5 "You can configure quotes directly in the Quote object, without any need to go through an OmniScript flow.") and [Multi-Root Quoting](https://help.salesforce.com/s/articleView?id=ind.insurance_multi_root_quoting_613315.htm&language=en_US&type=5 "Configure, navigate, and reprice complex quotes with multi-level insured item relationships and coverages with Vlocity Insurance multi-root quoting.") to learn more.

-   **[Insurance Quoting Processes](https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insurance_quoting_processes_611091.htm&language=en_US&type=5)**  
    You can build quoting processes for your users in two ways: Lightning web components and OmniScripts. Lightning web components make up the processes that your internal users can use to create quotes for your customers. Use OmniScripts to create processes to guide your external users (like customers and partners).

Did this article solve your issue?

Let us know so we can improve!

YesNo