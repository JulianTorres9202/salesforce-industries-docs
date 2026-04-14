---
title: "Child Specs in Context"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_child_specs_in_context_605004.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Child Specs in Context

Child Specs in Context[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Child Specs in Context

Use child specs to create insurance products, health plans, and claim products. Insurance products and health plans can contain one or more child specs. Make sure that part of your planning includes deciding what types of child specs go into your root product specs.

[](https://help.salesforce.com/s?language=en_US)

For example:

-   Almost all insurance products and health plans include at least one coverage spec.
    
-   Most insurance products include insured item specs.
    
-   Group health plans often need rating fact specs because the people being insured are typically stored in the Census object in Salesforce.
    

[](https://help.salesforce.com/s?language=en_US)Some child specs are used in OmniScript flows that your customers see and interact with. Some child specs are used to rate products and to generate and organize data on objects like Quote and Policy (Asset).

Child specs contain two major parts:

-   Details
    
-   Attributes
    

Details provide identifying data.

Attributes define the child spec functionally. The attributes you use to build each child spec will be used by the insurance product or health plan. They're often displayed to users through OmniScript templates. Users enter values and choose values for attributes as they go through insurance flows.

For example, in this auto insurance quote flow, a user can choose a deductible from a picklist for their collision coverage:

Collision is the coverage spec you created.

Deductible is an attribute you added to the coverage spec.

The values available for Deductible are a picklist you set up on the attribute in the coverage spec.

[](https://help.salesforce.com/s?language=en_US)

## Types of Child Specs

The child specs that can be part of insurance products and health plans are:

-   Coverage Spec
    
    Coverage specs are templates for coverages that you attach to insurance products or health plans. They define what is covered by the insurance quote or policy. Some coverages in an auto insurance policy can be Comprehensive, Collision, Uninsured Motorist, and Rental Car. Coverages on a typical health plan can be Office Visit, Ambulance Service, Outpatient Surgery, and Hospital Stay.
    
-   Insured Item Spec
    
    Insured item specs are templates for items that you attach to insurance products. They define an item that is insured by the insurance quote or policy, or is related to the quote or policy. In an auto insurance policy, the insured item is the car.
    
-   Insured Party Spec
    
    Insured party specs are templates for people that you attach to insurance products or health plans. They define a person who is associated with the insurance policy or health plan. For an auto insurance policy, an insured party can be the Driver. For a life insurance policy, an insured party can be a Beneficiary.
    
-   Rating Fact Spec
    
    Rating fact specs contain mappings to data that exists in other objects in Salesforce or a third-party system that will be used by Insurance to rate products. For a group health plan, rating facts include mappings to a census and census members.
    

Looking for info about how to create claim products? See [Create Claim Product Models](https://help.salesforce.com/s/articleView?id=ind.insurance_create_claim_product_models_617529.htm&language=en_US&type=5 "A claim product model describes a claim that an insurance policyholder can file against an insurance policy.").

[](https://help.salesforce.com/s?language=en_US)

## Attributes on Child Specs

Most child specs include at least one attribute. When you add attributes to a child spec, you also configure them with controls and values. All the data about an attribute and its configuration is stored on the attribute assignment record.

Note

Insured item specs and insured party specs don't usually include attributes with default values. Keep this in mind as you configure the attributes for these child specs.

During the planning process, determine the function of each attribute and how users interact with it.

**Do you show the attribute to users as they go through a quote or policy purchase flow?**

Decide whether an attribute is something a user needs to see on the spec. Hidden attributes aren't shown to customers at all but may be included in rating. Attributes are visible by default.

**Do users select or enter a value for this attribute?**

If not, you can have the field appear blank or pre-populated with a value that users can't change. If so, you can make the attribute configurable and let users enter or select a value for this attribute.

**Can users enter any value they want, or do they select from a set of preconfigured options?**

If you let users select or enter a value, choose from a menu of controls for this attribute's value.

**Does Insurance use this attribute's value to rate the product this child spec is attached to?**

If you use this attribute for rating, follow the instructions in [Mapping Ratings to Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_mapping_ratings_to_product_spec_610341.htm&language=en_US&type=5 "After you configure rating procedures, map ratings to your product specs. Complete this task for all your product specs, including insured item specs, insured party specs, and root product specs. OmniScripts and other components use services that read the mappings and formulas, and then return premium prices to your users.") to map your rating information correctly.

**Does Insurance use this attribute's value to rate a tax or fee for either this child spec or for the root product this child spec is attached to?**

If so, select the Tax and Fee Rating Attribute option.

**Does this attribute enforce policy terms such as limits or deductibles in claims?**

If so, plan to use power attributes. Power attributes are used to configure policy terms such as limits, deductibles, copays, and coinsurance. These attributes have specific definitions that allow claims to enforce the policy term.

If an attribute is configured as a power attribute, a lightning bolt appears next to its name when you add it to a child spec.

Power attributes can be configured on root products and coverage specs. So how do you decide where in the product model to configure a power attribute? Consider the scope of the policy term: whether it applies to the entire policy, each claim, or specific coverages.

| 
Model

 | 

Power Attribute Scope

 | 

How It Works

 |
| --- | --- | --- |
| 

Root product

 | 

Policy

 | 

Policy Term applies across all claims created for that Insurance Policy.

Example: A policy deductible

 |
| 

Root product

 | 

Claim

 | 

Policy Term applies to each claim created on that Insurance Policy.

Example: Per claim limit

 |
| 

Coverage spec

 | 

Policy

 | 

Policy Term applies across all Claim Coverages created on all Insurance Policy Coverages that use that Coverage Spec on the same Insurance Policy.

Example: A per policy limit on a specific coverage spec such as Outpatient Coverage, to be shared across all Insurance Policy Participants on the Insurance Policy

 |
| 

Coverage spec

 | 

Claim

 | 

Policy Term applies to all Claim Coverages on a Claim that was created on that Insurance Policy.

Example: A per claim limit on a specific coverage spec such as Bodily Injury

 |
| 

Coverage spec

 | 

Claim coverage

 | 

[](https://help.salesforce.com/s?language=en_US)Policy Term applies to each Claim Coverage that is open on a claim that was created on that Insurance Policy.

[](https://help.salesforce.com/s?language=en_US)Example: A per person limit on a specific coverage spec such as Bodily Injury

 |
| 

Coverage spec

 | 

Policy coverage

 | 

Policy Term applies to each instance of an Insurance Policy Coverage on the policy.

Example: Each Insurance Policy Participant on the Insurance Policy has their own limit for a specific coverage spec

 |

To learn more about planning power attributes, see [Policy Terms as Power Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_terms_as_power_attributes_617749.htm&language=en_US&type=5 "Enforce policy terms such as limits and deductibles by using power attributes. The \"power\" in power attributes comes from the extra metadata that you can configure for them. Insurance uses this metadata to track attributes as policy terms, from the product model to the policy record, and then on to claims against the policy."). To create power attributes, see [Product Attributes in Product Specs](https://help.salesforce.com/s/articleView?id=ind.insurance_product_attributes_in_product_specs.htm&language=en_US&type=5 "Product attributes are key pieces of the whole Vlocity Insurance and Vlocity Health platform. They define coverages, insured items, and other parts of insurance products and health plans. They correspond to anything that's important to quoting, rating, and writing an insurance policy. Attributes include inputs to rating (pricing), and characteristics that define claims.").

**Does this attribute require one or more rules to govern its use on this child spec?**

See [Attribute Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_attribute_rules_607965.htm&language=en_US&type=5 "Show users and customers exactly the right product attributes and attribute values for the insurance products that you quote, sell, and service.").

[](https://help.salesforce.com/s?language=en_US)Note

You can create child specs without attributes attached if you have a business need, although this is rare. For example, you can create a coverage spec with a fixed premium and no attributes.

[](https://help.salesforce.com/s?language=en_US)

## Coverage Spec Guidelines

A coverage spec you create and attach to a product becomes a coverage that your users interact within quote and policy purchase flows.

For many Insurance lines of business, your users will need to interact with coverages in quote and policy flows. For example, it's pretty common for auto insurance customers to choose coverage limit amounts and deductibles.

To make this work and to create reusable coverage specs, configure customizable attributes with a selection of values users can choose from when they're going through flows.

Insurance uses coverage specs to create quote line items when a user completes a quote flow, and it uses coverage specs to create policy data when a user buys a policy.

Here's an example of how Insurance displays data from a coverage spec in an OmniScript, in this case a quote flow:

Here's an example of how Insurance stores coverage data on a quote:

Here's an example of how Insurance stores coverage data on a quote line item:

Here's an example of how Insurance stores coverage data on a policy:

[](https://help.salesforce.com/s?language=en_US)

## Insured Item Spec Guidelines

An insured item is what it sounds like—an item that is insured by a policy. For auto insurance, the insured item is the car. Most health plans don't use insured item specs.

The attributes you put into an insured item spec define that insured item. For example, a car insured item probably includes the Make, Model, Year, Color, and Annual Mileage Driven as just a few of the attributes that define it.

Insurance uses the insured item spec to create quote line items for each insured item when a user completes an OmniScript quote flow. It uses insured item specs to create policy data when a user buys a policy.

Here's an example of how Insurance displays data from an insured item spec in an OmniScript, in this case a quote flow:

Here's an example of how Insurance stores insured item data on a quote:

Here's an example of how Insurance stores insured item data on a quote line item:

Here's an example of how Insurance stores insured item data on a policy:

[](https://help.salesforce.com/s?language=en_US)

## Insured Party Spec Guidelines

Insured Party Specs describe people (sometimes corporate entities if they are the insured party) who are either insured by a policy or are beneficiaries of a policy. For a life insurance product, insured parties include the insured person and the beneficiaries. For an auto insurance product, the insured parties are the drivers of the cars.

The attributes you put into an insured party spec define that insured party. For example, a car driver insured party probably includes Name, Birth Date, Gender, Accident Points, and Driver's License Number as just a few of the attributes that define it.

Although you set up an insured party spec the same way you set up other child specs, Insurance displays insured parties differently than it displays insured items. Data for insured parties is stored differently than insured items.

In policies that include both insured parties and insured items, Insurance creates a hierarchical many-to-many relationship between insured items and insured parties. The insured item is the parent, and the insured party is the child in this relationship.

One insured item can have many insured parties as its children.

One insured party can be a child to many insured items.

[](https://help.salesforce.com/s?language=en_US)

## Rating Fact Spec Guidelines

You may have some attributes that you need to include when rating products, but you don't want saved or stored on objects (like quotes or policies). You can set up a Rating Fact Spec that includes these attributes. You set up rating fact specs the same way you set up all other child specs.

Insurance does not store the data generated from rating facts when they're used by services to rate products.

Did this article solve your issue?

Let us know so we can improve!

YesNo