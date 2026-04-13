---
title: "Auto Claims Product Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_product_model_512978.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Auto Claims Product Model

Auto Claims Product Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Auto Claims Product Model

The auto claim business processes uses the Auto Claim product model when creating, updating, and adjudicating claims.

[](https://help.salesforce.com/s?language=en_US)

The auto claims business processes use the Auto Claim claim product model to structure the data in a claim.

The Auto Claims product also includes [Claim Workflow Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_product_model_512978.htm&language=en_US&type=5 "The auto claim business processes uses the Auto Claim product model when creating, updating, and adjudicating claims.") that are important to the processing of claims.

[](https://help.salesforce.com/s?language=en_US)

Let's dig in!

[](https://help.salesforce.com/s?language=en_US)

## Involved Property Spec: Claim Involved Vehicle

The involved property spec attached to the claim product is:

-   Name: **Claim Involved Vehicle**
    
-   Code: **autoClaimInvolvedVehicle**
    

It contains attributes from the following attribute categories:

-   Auto Vehicle
    
-   Claim Item
    

The Claim Item attribute values are gathered by the Claim FNOL OmniScript.

## Claimant Spec

This spec describes people involved in the claim who suffered a loss and are seeking coverage for that loss.

The Claimant involved party spec has the following name and code:

-   Name: **Claimant**
    
-   Code: **claimClaimantPerson**
    

Claimant includes attributes from the following attribute categories:

-   Claim Item
    
-   Claim Party
    
-   Person
    

Values for these attributes get collected by the Claim FNOL flow or are pulled from other objects, such as the Policies (Asset) object or the Account object. Some values for the Claimant may not be entered until later in the claims adjudication on the Claims Adjuster Workbench.

Each attribute is configured for this involved party spec on the right pane of this page. Click each attribute name to see its configuration on the right pane.

## Claim Participant Spec

This spec is used by claims to describe people involved in the claim who are participants in the claim, but not claimants who suffered a loss.

The Claim Participant claim injury spec has the following name and code:

-   Name: Claim Participant
    
-   Product Code: claimParticipantPerson
    

Claim Participant includes attributes from the following attribute categories:

-   Claim Party
    
-   Person
    

Values for these attributes get collected by the Claim FNOL flow. Some values for the Claim Participant may not be entered until later in the claims adjudication on the Claims Adjuster Workbench.

Each attribute is configured for this involved party spec on the right pane of this page. Click each attribute name to see its configuration on the right pane.

[](https://help.salesforce.com/s?language=en_US)

## Coverages

Coverage specs define the coverages that can be handled by this claim product. On the Product page, the Product Record Type at the top left of the page = Coverage Spec.

All the coverage specs on the Auto Claims product model are the same as those on the [Auto Product Model](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_product_model_510402.htm&language=en_US&type=5 "The product model underpins all the business processes used in the Auto line of business. This line of business offers two products namely Multi Auto and Commercial Auto.").

| 
Coverage Spec Name

 | 

Product Code

 | 

Configuration

 |
| --- | --- | --- |
| 

Collision

 | 

autoCollision

 | 

Contains the Collision Deductible power attribute, configured with **Currency Dropdown** values.

 |
| 

Comprehensive

 | 

autoComp

 | 

Contains the Comp Deductible power attribute, configured with **Currency Dropdown** values.

 |
| 

Medical Payments

 | 

autoMedical

 | 

Contains the Med Pay Person Limit power attribute, configured with **Currency Dropdown** values.

 |
| 

Uninsured Motorist

 | 

autoUM

 | 

Contains the UM Limit power attribute, configured as a **Picklist Dropdown**.

 |
| 

Rental Car

 | 

autoRental

 | 

Contains the Rental Limit power attribute with a **Currency** value set to 2000.

Contains the Number of Days power attribute with a **Number** value set to 30.

 |
| 

Bodily Injury & Property Damage

 | 

autoBIPD

 | 

Contains the BIPD Limit power attribute, set up as a **Multivalue Picklist** with a list of split-limit values.

 |

[](https://help.salesforce.com/s?language=en_US)

## Attributes

All the attributes used in the Auto claim product and the claim item spec, claim injury spec, and coverage specs are defined in the Vlocity Attribute Designer. Attributes are arranged into Attribute Categories.

Want to see a complete list of the attributes used in the Auto Claim product model? Visit the \[claims attribute catalog\] and the [Auto Attribute Catalog](https://help.salesforce.com/s/articleView?id=ind.insurance_auto_attribute_catalog.htm&language=en_US&type=5 "In this catalog, all attributes used for the Auto line of business are listed by Attribute Category. Each Attribute Category has its own table, which includes attribute codes and the product specs the attributes are used by.").

In the Vlocity Attribute Designer, basic information is defined for all attributes, such as name and attribute code.

For specific limit and deductible attributes that we use to describe policy terms, more information is defined:

-   Attribute Class
    
-   Attribute Scope
    
-   Applicable Actions
    
-   Applicable Item
    
-   Value Type
    

Attributes that have these fields set are called power attributes. Power attributes are defined for policy terms so that the claims system can track them.

To learn more about power attributes, including when to use them and how to set them up, see [Policy Terms as Power Attributes](https://help.salesforce.com/s/articleView?id=ind.insurance_policy_terms_as_power_attributes_617749.htm&language=en_US&type=5 "Enforce policy terms such as limits and deductibles by using power attributes. The \"power\" in power attributes comes from the extra metadata that you can configure for them. Insurance uses this metadata to track attributes as policy terms, from the product model to the policy record, and then on to claims against the policy.").

The attribute's Value Data Type, available values, default selected value, rating status, and other specifics are configured on the insured item spec, insured party spec, coverage spec, or root product spec.

A common attribute configuration used in auto coverage specs is the split limit attribute. This attribute type is used when several policy terms need to be displayed and selected together by customers. But Vlocity needs to access and act on each attribute independently for rating, rules, and claims.

The Uninsured Motorist coverage contains a Limit attribute that's got a split limit.

To configure this split limit attribute, we selected Multiselect Picklist for the Value Data Type and created a Value Decoder to help Vlocity work with the split limit attribute values.

[](https://help.salesforce.com/s?language=en_US)

## Claim Workflow Rules

In this Application Suite, Claim workflow rules (which are created in the Underwriting Rules section of the Rules tab on the root product spec) automate some of the tasks for creating a claim record at runtime. These rules tell the system to open claim coverages and open claim line items on those claim coverages.

The Auto Claim workflow rules use the Claim Processing state model. This state model includes the Vlocity Actions and states used by these rules.

Here's what the rules look like on the Rules tab in the product model:

Let's take a look at each of these rules and what it does:

1.  Open Collision Coverage First Party Vehicle
    
    If the in-force policy includes Collision coverage and one of the insured vehicles is damaged, this rule evaluates to true.
    
    When this rule evaluates to true, two things happen:
    
    -   The Action specified opens a claim coverage against the Collision coverage.
        
    -   The state transition specified moves this claim from Draft state to Adjuster Review State. This transition makes this claim available on the Adjuster Workbench.
        
2.  New Policy
    
    Looks at the claim date and the policy effective date. If the claim is filed less than 60 days after the policy effective date, the rule evaluates to true.
    
    When the rule evaluates to true
    
    [](https://help.salesforce.com/s?language=en_US)
    -   The Action specified refers the claim to a claims adjuster.
        
    -   The state transition specified moves this claim from Draft state to Adjuster Review State. This transition makes this claim available on the Adjuster Workbench.
        
3.  Open Property Damage Third Party
    
    Looks to see if a car (or other property) that's reported as damaged in the claim is or isn't an insured item on the in-force policy.
    
    When the rule evaluates to true (which actually means that the vehicle or property is not an insured item on the policy), two things happen:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   The Action specified opens a claim coverage against the Bodily Injury & Property Damage coverage.
        
    -   The state transition specified moves this claim from Draft state to Adjuster Review State. This transition makes this claim available on the Adjuster Workbench.
        
4.  Open Bodily Injury Third Party Driver
    
    Looks at an involved party to determine if they were injured in the accident, and whether they are a claimant on the claim.
    
    When this rule evaluates to true (yes the person was injured but no they're not an insured party), two things happen:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   The Action specified opens a claim coverage against the Bodily Injury & Property Damage coverage.
        
    -   The state transition specified moves this claim from Draft state to Adjuster Review State. This transition makes this claim available on the Adjuster Workbench.
        
5.  Open Rental Car Coverage
    
    Looks at whether the damaged vehicle that's insured by the in-force policy is driveable or not.
    
    When this rule evaluates to true (car's not driveable), two things happen:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   The Action specified opens a claim coverage against the Rental Car coverage.
        
    -   The state transition specified moves this claim from Draft state to Adjuster Review State. This transition makes this claim available on the Adjuster Workbench.
        
6.  Open Med Pay Coverage
    
    Looks at whether the involved person is injured, and whether the involved person is a claimant on the claim.
    
    When this rule evaluates to true (the involved person is injured and a claimant), two things happen:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   The Action specified opens a claim coverage against the Medical Payment coverage.
        
    -   The state transition specified moves this claim from Draft state to Adjuster Review State. This transition makes this claim available on the Adjuster Workbench.
        
7.  Open Bodily Injury Third Party
    
    Looks to see how severely a claimant has been injured in the accident.
    
    When the rule evaluates to true (severity of the injury is moderate), two things happen
    
    [](https://help.salesforce.com/s?language=en_US)
    -   The Action specified opens a claim coverage against the Bodily Injury & Property Damage coverage.
        
    -   The state transition specified moves this claim from Draft state to Adjuster Review State. This transition makes this claim available on the Adjuster Workbench.
        

The claim workflow rules set up on the Auto Claim product run near the end of the Auto claim FNOL OmniScript. After the claim record has been created and updated with information about the claim, the rules run and any that evaluate to true open claim coverages and create claim line items.

The OmniScript calls the InsClaimService:invokeProductRules service to run the rules.

Did this article solve your issue?

Let us know so we can improve!

YesNo