---
title: "Create Claim Product Models"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_claim_product_models_617529.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create Claim Product Models

Create Claim Product Models[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Claim Product Models

A claim product model describes a claim that an insurance policyholder can file against an insurance policy.

The structure defined by this product model is used by the [InsClaimService: createUpdateClaim](https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservicecreateupdateclaim_630113.htm&language=en_US&type=5 "Use this service to create or update a claim.") service. The claim product model defines the structure of the input JSON used by this service to create and update a claim.

[](https://help.salesforce.com/s?language=en_US)

## Plan Your Claim Product Model

When you plan your claim product models, think of them in terms of claim types. Each claim type will define the structure of the claim and include a set of rules to handle that type of claim. Product modeling is part art and part science, so there is no one-size-fits-all structure to recommend. Instead, you can take several different approaches for any given claim type.

[](https://help.salesforce.com/s?language=en_US)Important

These examples illustrate just a few valid configurations. Your actual business requirements may differ.

| 
Method

 | 

Example

 |
| --- | --- |
| 

Unique claim product per root product

 | 

Homeowners, Renters, Personal Auto, and Watercraft claims can be structured and handled differently enough to warrant distinct root product and claim product definitions for each one.

 |
| 

Single claim product for multiple root products

 | 

Personal Auto and Commercial Auto can be unique root products because of the different selling and rating processes inherent in these two lines of business. But the types of claims made for these root products can be similar enough to handle through a single Auto claim product.

 |
| 

Multiple claim products for a single root product

 | 

You can sell an Identity Protection coverage under a Homeowners root product along with standard Dwelling and Contents coverages. But the claim handling structure and rules for claims made against the Identity Protection coverage are probably nothing like those used for Dwelling and Contents coverages. An Identity Protection claim product, distinct from a Homeowners claim product, is a way to segment the structure and rules for handling Identity Protection claims separately from standard Homeowners claims.

 |

[](https://help.salesforce.com/s?language=en_US)

## What's in a Claim Product

A claim product can include one or more claim injury specs and claim property specs. It also includes coverage specs—the same coverage specs attached to the insurance product model(s) that this claim product relates to.

[](https://help.salesforce.com/s?language=en_US)Claim products, claim injury specs, and claim property specs are built using attributes, which can be the same attributes that root product specs and child product specs are built from, and attributes created specifically for claim products.

[](https://help.salesforce.com/s?language=en_US)Tip

Vlocity recommends that you add all the coverage specs to a claim product model that exists on the insurance product model(s) this claim product relates to.

[](https://help.salesforce.com/s?language=en_US)A claim product can also include rules that define how a claim moves through state transitions (for example, from "new" to "open"), and how actions happen when a claim product is used by Vlocity at runtime to create or update a claim.

[](https://help.salesforce.com/s?language=en_US)Note

You'll create claim rules in the Underwriting Rules section of the Rules tab on your claim product models.

Despite the name on the UI, these are not underwriting rules. They're claim rules.

[](https://help.salesforce.com/s?language=en_US)Here's an example of a basic structure of an Auto Claim Product model:

[](https://help.salesforce.com/s?language=en_US)In this structure:

[](https://help.salesforce.com/s?language=en_US)

-   The Claim Involved Vehicle spec is used at runtime for both the insured item (vehicle) on the policy that's involved in the claim, and for any third-party vehicles that are also part of the claim.
    
-   The Injury spec is used to define the injuries that are incurred by any person on the claim.
    

[](https://help.salesforce.com/s?language=en_US)Claim Property Specs are fairly straightforward in that if you're adding an involved property to a claim, it's sustained some damage, and that would be captured on the Claim Property Spec. On the other hand, if you're adding people to a claim, it’s less obvious if the Claim Product Model needs to be used.

[](https://help.salesforce.com/s?language=en_US)Most of the characteristics about people are actually stored in Accounts and Contacts, so these don't need to be captured in the Claim Product Model. And you don’t need to capture the roles for a person associated with a claim. All the “person” details are stored on the claim directly through the Claim Participant.

[](https://help.salesforce.com/s?language=en_US)Use of the Claim Product Model is necessary only when additional information needs to be captured about a person’s involvement in a specific claim, like if they have an injury as modeled in this P&C Auto Claim Product.

[](https://help.salesforce.com/s?language=en_US)

## Workflow for Claim Product Modeling

-   **[Create Claim Involved Injury Specs and Claim Involved Property Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_create_claim_involved_injury_specs_and_claim_involved_property_specs.htm&language=en_US&type=5)**  
    Claim injury specs and claim property specs are parts of a claim products.
-   **[Create a Claim Product Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_create_a_claim_product_spec.htm&language=en_US&type=5)**  
    A claim product spec describes the people and property that are involved in a claim. It also includes the rules that are used to automate aspects of claim processing
-   **[Create Claim Product Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_create_claim_product_rules_617684.htm&language=en_US&type=5)**  
    Rules on a claim product let you automate parts of creating a claim at runtime. For example, you can create rules that open claim coverages and set loss and expense reserves, or in some cases automatically pay and close the claim.

Did this article solve your issue?

Let us know so we can improve!

YesNo