---
title: "Example: Claim Transition from Draft to Payment Processing"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_example_clm_transition.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Example: Claim Transition from Draft to Payment Processing

Example: Claim Transition from Draft to Payment Processing[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Example: Claim Transition from Draft to Payment Processing

This example demonstrates how a Product Admin can configure conditions to transition a claim from Draft to either Payment Processing or Under Review.

Scenario: A claim is filed for a damaged vehicle.

Condition: If the Claim Amount < $100, then open Rental Car Collision coverage and change status to 'Payment Processing', else open Rental Car Collision coverage and change status to 'Under Review'.

Automated Actions (if true):

-   Open a new claim coverage (Example: Rental Car Collision).
-   Send claim evaluation successful email notification.
-   Transition the claim's status from Draft to Payment Processing.

Automated Actions (if false):

-   Open a new claim coverage (Example: Rental Car Collision).
-   Send a claim under review email notification.
-   Transition the claim's status from Draft to Under Review.

To enable the transition from Draft to Payment Processing, the Product Admin sets up a rule with these conditions on the Rental Car product:

| Stage Transition | Product Criteria | Action |
| --- | --- | --- |
| Draft to Payment Processing | 
Claim amount < $100

 | 

True evaluation: Send Email

False evaluation: Move Claim to Under Review stage and send email about moving the claim to Under Review stage.

 |

When insurance reps trigger the claim workflow rule:

[](https://help.salesforce.com/s?language=en_US)

-   If the product meets the criteria and satisfies the rule group condition logic, the claim transitions to the Payment Processing stage. The rule triggers the confirmation email to users.
-   If the product doesn’t meet the criteria, the rule initiates a flow that transitions the claim to the Under Review stage. Also, the rule triggers an email to the user stating the claim stage change to Under Review.

Did this article solve your issue?

Let us know so we can improve!

YesNo