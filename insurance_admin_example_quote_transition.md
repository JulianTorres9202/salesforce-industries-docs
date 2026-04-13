---
title: "Example: Quote Transition from Submitted to Approved"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_admin_example_quote_transition.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Example: Quote Transition from Submitted to Approved

Example: Quote Transition from Submitted to Approved[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Example: Quote Transition from Submitted to Approved

This example demonstrates how a Product Admin can configure conditions to transition a quote from Submitted to either Approved or Underwriter Review.

To enable the transition from Submitted to Approved, the Product Admin sets up a rule with these conditions on the Auto Vehicle product:

| Stage Transition | Product Criteria | Action |
| --- | --- | --- |
| Submitted to Approved | 
Driver Accidents Less than 3

AND

Risk Category Equals High

 | 

True evaluation: Send Email

False evaluation: Move quote to Underwriter Review stage.

 |

When insurance reps trigger the product underwriting rule:

[](https://help.salesforce.com/s?language=en_US)

-   If the product meets the criteria and satisfies the rule group condition logic, the quote transitions to the Approved stage. The rule triggers the confirmation email to users.
-   If the product doesn’t meet the criteria, the rule initiates a flow that transitions the quote to the Underwriter Review stage.

Did this article solve your issue?

Let us know so we can improve!

YesNo