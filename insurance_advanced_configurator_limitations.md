---
title: "Limitations and Known Issues"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_limitations.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Limitations and Known Issues

Limitations and Known Issues[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Limitations and Known Issues

Understand the current limitations and known issues when using Constraint Rules Engine for insurance product modeling.

-   If admins don’t explicitly set the Rule Engine on the Transaction Processing Type, Constraint Rules Engine is used by default when it's enabled. This can cause constraint rules to trigger even in quotes that are intended for Standard Configurator.
-   Writing a constraint in CML that references attributes from child products across different classifications (e.g., Driver and Rider) can unintentionally cause the engine to auto-add a new instance of one of the child products (e.g., Driver). This occurs even when the referenced instances already exist in the quote.
-   In PCM, attribute names can contain spaces, but constraints require these names to be used as variable names, which can't include spaces.
-   If two different types define relationships with the same name, the relationship association record is overwritten.
-   Complex constraints with nested bundle filtering and unused variables or attributes in the model can cause performance issues.
-   If an int attribute isn't used in any constraint during tax rule evaluation, a NullPointerException occurs and the quote creation fails. To avoid this, either remove unused attributes and variables or use the attribute in a constraint.
-   The constraint engine may backtrack during evaluation. The @abort=true annotation prevents the engine from backtracking by triggering the user-defined error message. However, this leads to another known limitation, which is that the constraint engine returns errors one by one (because it stops on the first error it encounters).
-   A constraint or variable that references multiple optional child instances will fail if any of those instances are not present under the parent. Even when conditional checks are used, the constraint engine treats the missing reference as unbound. This expression will fail if either normalEquipment or electricalEquipment isn’t included under the parent product.
    
    ```
    int equipmentLimit = normalEquipment[Equipment].limit + electricalEquipment[Equipment].limit;
    ```
    
-   You may encounter the following exception when using the Create or Update Quote API on a quote line item that has both active tax rules and active configuration rules (CML-based auto-add or exclude logic):
    
    ```
    "code": "UNKNOWN_EXCEPTION",
    "message": "Something went wrong while pricing the transaction. : industries.insurance.foundation.impl.exception.InsFoundationException: SF-0007-0001"
    ```
    
    To fix this error:
    
    -   Remove unused attributes on the quote line item.
    -   Mark configurable=false if that attribute is not supposed to be changed by the engine.
    -   Define a domain (range or possible values) for all numeric attributes.

Did this article solve your issue?

Let us know so we can improve!

YesNo