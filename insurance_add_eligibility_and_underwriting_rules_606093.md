---
title: "Add Eligibility and Underwriting Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_eligibility_and_underwriting_rules_606093.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Eligibility and Underwriting Rules

Add Eligibility and Underwriting Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Eligibility and Underwriting Rules

Vlocity Insurance uses eligibility rules to filter a root product in or out of quotes at runtime. Underwriting (workflow) rules determine when a runtime quote for a root product can be automatically issued as a policy, when it must be sent to underwriting, and when a policy issue is automatically declined.

For example:

-   If an insurance product isn't available in Alaska, use a simple eligibility rule to exclude it from quotes for customers with an Alaska address.
    
-   Set up underwriting rules to automatically issue a homeowners product if the value of the building is under $500,000, to send the quote to underwriting for building values between $500,000 and $1 million, and to automatically decline policy issuance if the value is over $1 million.
    

[](https://help.salesforce.com/s?language=en_US)To learn how to add eligibility rules, see [Create Product Eligibility Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_create_product_eligibility_rules_607661.htm&language=en_US&type=5 "Insurance uses eligibility rules to help determine what insurance products and optional coverages a customer is eligible for. You can use eligibility rules in the quote process to screen out insurance products and optional coverages that a potential customer doesn't qualify for. For example, you can create an eligibility rule for a Medicare supplement insurance product that screens out anyone under the age of 65.").

[](https://help.salesforce.com/s?language=en_US)To learn how to add underwriting rules, see [Underwriting (Workflow) Rules](https://help.salesforce.com/s/articleView?id=ind.insurance_underwritingworkflowrules_607457.htm&language=en_US&type=5 "Underwriting (workflow) rules can help automate your business processes as quotes get issued as policies, when policies become eligible for mid-term adjustments (MTAs), when it's time to renew or cancel a policy, and for claims processing.").

Note

Additional rules may apply to all products that use a specific state model. If the state model a product uses has state transition rules, don't create underwriting rules that do the same things.

Did this article solve your issue?

Let us know so we can improve!

YesNo