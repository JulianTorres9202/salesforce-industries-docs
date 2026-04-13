---
title: "Auto Claims Product Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_auto_claims_product_model_omnistudio.htm&language=en_US&type=5"
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

The auto claims business processes use the Auto Claim claim product model to structure the data in a claim.

The Auto Claims product also includes Claim Workflow Rules that are important to the processing of claims.

Let's dig in!

-   **[Involved Property Spec: Claim Involved Vehicle](https://help.salesforce.com/s/articleView?id=ind.insurance_involved_property_spec__claim_involved_vehicle_omnistudio.htm&language=en_US&type=5)**  
    The involved property spec attached to the claim product is:
-   **[Claimant Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_claimant_spec_omnistudio.htm&language=en_US&type=5)**  
    This spec describes people involved in the claim who suffered a loss and are seeking coverage for that loss.
-   **[Claim Participant Spec](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_participant_spec_omnistudio.htm&language=en_US&type=5)**  
    This spec is used by claims to describe people involved in the claim who are participants in the claim, but not claimants who suffered a loss.
-   **[Coverages in Auto Claims Products](https://help.salesforce.com/s/articleView?id=ind.insurance_coverages_in_auto_claims_products_omnistudio.htm&language=en_US&type=5)**  
    Coverage specs define the coverages that can be handled by this claim product. On the Product page, the Product Record Type at the top left of the page = Coverage Spec.
-   **[Attributes for Auto Claims Products](https://help.salesforce.com/s/articleView?id=ind.insurance_attributes_for_auto_claims_products_with_omnistudio.htm&language=en_US&type=5)**  
    All the attributes used in the Auto claim product and the claim item spec, claim injury spec, and coverage specs are defined in the Vlocity Attribute Designer. Attributes are arranged into Attribute Categories.
-   **[Claim Workflow Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_workflow_rules_omnistudio.htm&language=en_US&type=5)**  
    In this Application Suite, Claim workflow rules (which are created in the Underwriting Rules section of the Rules tab on the root product spec) automate some of the tasks for creating a claim record at runtime. These rules tell the system to open claim coverages and open claim line items on those claim coverages.

Did this article solve your issue?

Let us know so we can improve!

YesNo