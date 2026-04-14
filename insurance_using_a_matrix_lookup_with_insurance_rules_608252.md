---
title: "Using a Matrix Lookup with Insurance Rules"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_using_a_matrix_lookup_with_insurance_rules_608252.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Using a Matrix Lookup with Insurance Rules

Using a Matrix Lookup with Insurance Rules[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Using a Matrix Lookup with Insurance Rules

You can use a matrix lookup when you create underwriting eligibility rules.

For example, your Watercraft Insurance product might not insure boats with specific hull types. You could create a calculation matrix with the different hull types and use a matrix lookup with your underwriting rule to determine if the hull type is allowed.

For an example of a completed eligibility rule using a Matrix Lookup, see the image below:

The **Applicable Type** would be Quote, the **Transition Name** would be from Submit > Decline, and the **Action** would be Decline Quote. The expression to look up a matrix would use the following syntax: `LookupMatrix('Matrix Name', INPUT('Matrix Input Variable Name', Input Data), 'Matrix Output Variable Name') = 'Returned Value'`

The expression for the underwriting rule when used would appear as follows:

```
LookupMatrix('HullTypeUnderwriting', INPUT('Watercraft Hull Type', WC.wcHullType), 'hullApproval') = 'Decline' 
```

If you have an Insurance Product that is only available in a specific state, you could use an eligibility rule to determine whether the applicant is in the relevant state before displaying the product. You can use matrix lookup function to look for the state based on the zip code. The eligibility rule in this instance would appear as follows:

```
EXIST(LookupMatrix('ZipcodeStateLookup',INPUT('zipcode', zipcode),'state'), 'CA') 
```

Note Underwriting (workflow) and eligibility rules don't support the use of decision matrices in Business Rules Engine.

Did this article solve your issue?

Let us know so we can improve!

YesNo