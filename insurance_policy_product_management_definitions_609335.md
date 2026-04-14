---
title: "Policy Product Management Definitions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_policy_product_management_definitions_609335.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Policy Product Management Definitions

Policy Product Management Definitions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Policy Product Management Definitions

Vlocity Insurance provides a robust administration environment to model and administer a wide range of insurance products. Correctly structuring products ensures consistent enforcement of pricing and rules throughout the policy lifecycle and reduces the effort of maintaining a large set of products.

The Vlocity Insurance product model is designed to reflect the reality of the insurance industry, while also maximizing the reuse of components across the products. The set-up and ongoing administration of the product is managed completely within the Salesforce Lightning Experience, with minimal need for custom coding.

The illustration below details the different components used in creating a product and how they interact.

The components of the model are described in the table below:

| 
Term

 | 

Definition

 | 

Example

 |
| --- | --- | --- |
| 

Insured Item Spec

 | 

The blueprint of the different types of objects that can be covered by the insurance product. See [Create Insured Item Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.").

 | 

For Watercraft Insurance, the insured items could refer to the vessel and the operator. For Pet Insurance, the insured item could refer to the eligible pet types, like dog, cat, or horse.

 |
| 

Coverage Spec

 | 

The type of coverage the insurance provides. See [Create Insurance Coverage Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_for_root_products.htm&language=en_US&type=5 "Child specs are key building blocks for your product models. They're components of the root product specs that Insurance rates, quotes, sells, and administers for your customers.").

 | 

For Watercraft Insurance, the coverage could include damage to the vessel along with liability insurance for the operator. For Pet Insurance, the coverage could include co-insurance, annual deductible, and annual benefit limit.

 |
| 

Products

 | 

A Product refers to an Insurance Product. It is composed of coverage and insured items, see [Root Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_root_product_specs_605705.htm&language=en_US&type=5 "Root product specs act as the product models that Vlocity uses at runtime to generate quotes and policies.")

 | 

A Watercraft Insurance product could be composed of the vessel and operator for Insured Items and damage and operator liability for Coverage. A Pet Insurance product could be composed of a Pet for the Insured Item and the coverage could consist of Annual Deductible and Co-Insurance.

 |
| 

Eligibility Rules

 | 

Eligibility Rules help determine the type of Insurance Products a user is eligible for based their information. See [Create Eligibility Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_create_product_eligibility_rules_607661.htm&language=en_US&type=5 "Insurance uses eligibility rules to help determine what insurance products and optional coverages a customer is eligible for. You can use eligibility rules in the quote process to screen out insurance products and optional coverages that a potential customer doesn't qualify for. For example, you can create an eligibility rule for a Medicare supplement insurance product that screens out anyone under the age of 65.").

 | 

If a user's age is greater than or equal to 65 they are eligible for Medicaid. If the user's age is less than 65, they are not eligible.

 |
| 

Underwriting Rules

 | 

Underwriting Rules can help you better automate progression through the quoting process. See [Creating Underwriting Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_underwritingworkflowrules_607457.htm&language=en_US&type=5 "Underwriting (workflow) rules can help automate your business processes as quotes get issued as policies, when policies become eligible for mid-term adjustments (MTAs), when it's time to renew or cancel a policy, and for claims processing.")

 | 

For Watercraft Insurance, you could create an underwriting rule that automatically declines applications where the vessel's age is over 25 years.

 |
| 

Calculation Matrix

 | 

Calculation Matrices are used in conjunction with Calculation Procedures to determine the insurance rates. See [Using a Matrix Lookup with Insurance Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_using_a_matrix_lookup_with_insurance_rules_608252.htm&language=en_US&type=5 "You can use a matrix lookup when you create underwriting eligibility rules.") .

 | 

For Watercraft Insurance, the hull material is a factor in the insurance price. For example, the WatercraftHullMaterial matrix may have an entry for Wood with a physical damage factor of 1.8 and liability factor of 1; an entry for Metal with physical damage factor of 1.05 and liability factor of 1.

 |
| 

Calculation Procedures

 | 

Calculation Procedures are used along with Calculation Matrix Lookup to determine the final price for an insurance quote, see [Declarative Calculation Procedures](https://help.salesforce.com/s/articleView?id=xcloud.os_declarative_calculation_procedures.htm&language=en_US&type=5).

 | 

A Calculation Procedure for Boat Insurance would have variables and constants along with the calculation steps. A variable would be WatercraftHullMaterial and a Constant would be baseLiability number that is always consistent. The calculation steps consist of matrix lookups and calculations.

 |
| 

Get Rated Products

 | 

The service used in the OmniScript to return the eligible priced products based on the end user's input.

 | 

See [InsProductService: getRatedProducts](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__getratedproducts.htm&language=en_US&type=5 "Use this service to get an array of one or more products, priced using rating procedures attached to those products. This service also includes extra features such as tax and fee calculations, filtering, and performance optimization.").

 |
| 

Reprice Product

 | 

The service used in the OmniScript to return the price of the product based on the end user's specifications.

 | 

See [InsPolicyService: repriceProduct](https://help.salesforce.com/s/articleView?id=ind.insurance_insproductservice__repriceproduct.htm&language=en_US&type=5 "Use this service to price one product using the rating procedure attached to that product. This service is usually called when a user selects a product and customizes its coverage.").

 |
| 

Create Update Quote

 | 

The service used in the OmniScript to create a new quote or update an existing quote.

 | 

See [InsQuoteService: createUpdateQuote](https://help.salesforce.com/s/articleView?id=ind.insurance_insquoteservice__createupdatequote.htm&language=en_US&type=5 "Use this service to create a quote for new business, update an existing quote with new information, or create an endorsement quote. For updates, the quoteId of the quote to be updated must be included in the remote options.").

 |
| 

Create Update Policy

 | 

The service used in the OmniScript to create a new policy or update an existing policy.

 | 

See [InsPolicyService: createUpdatePolicy](https://help.salesforce.com/s/articleView?id=ind.insurance_inspolicyservice__createupdatepolicy.htm&language=en_US&type=5 "Use this service to create a new insurance policy or to update an existing policy with new information.").

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo