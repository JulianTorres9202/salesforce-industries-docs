---
title: "Constraint Rules Engine Adoption for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Constraint Rules Engine Adoption for Insurance

Constraint Rules Engine Adoption for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Constraint Rules Engine Adoption for Insurance

Adopt Constraint Rules Engine (CRE) for insurance quoting to validate complex product configurations with constraint-based logic. This feature is in beta and supports deeply nested bundles, cross-product dependencies, and multi-instance insurance scenarios. CRE ensures accurate quoting by preventing invalid selections while you transition from Business Rules Engine to a constraint-driven model.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Developer</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions of Revenue Cloud where Product Configurator is enabled</td></tr></tbody></table>

Product Configurator supports two modes for rule execution: Constraint Rules Engine (CRE) and Business Rules Engine (BRE). BRE (Business Rules Engine) executes rule-based logic for simpler validations. CRE (Constraint Rules Engine) evaluates constraint-based models for complex configuration logic across bundles, sibling products, and multi-instance relationships.

Note This feature is currently in beta and doesn't not support all production use cases.

This guide shows Insurance admins how to adopt Constraint Rules Engine for quoting. It gives the Insurance-specific setup steps you must follow, explains how CRE affects existing and new quotes, and shows how to build, associate, and test constraint models that enforce insurance business rules. The goal is to give you a complete, Insurance-focused path from setup to a working CRE model that validates Insurance product configurations during quoting.

What's Next

-   Review required permissions and how CRE impacts existing quotes.
-   Set up CRE by adding fields, updating context, and adjusting procedure plans.
-   Learn how to control which rule engine is used and when to switch between CRE and BRE.
-   Create and test constraints for insurance products using Constraint Builder.
-   Review current limitations and known issues.
-   Explore example constraint models for AutoSilver and Medical.

-   **[Constraint Rules Engine Permissions](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_permissions.htm&language=en_US&type=5)**  
    Assign permissions so that rule designers can create constraint rules and sales reps can use them during quoting.
-   **[Understand Impact on Existing Quotes](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_impact.htm&language=en_US&type=5)**  
    Before you enable Constraint Rules Engine, review how it affects quotes created before and after enablement.
-   **[Set Up Constraint Rules Engine](https://help.salesforce.com/s/articleView?id=ind.insurance_product_configurator_set_up_advanced_configurator.htm&language=en_US&type=5)**  
    Set up the Constraint Rules Engine rule engine by creating the ConstraintEngineNodeStatus custom field on Quote Line Item object, updating the InsuranceContext context definition to map the field, and adjusting your procedure plan definition so that Insurance quotes use Constraint Rules Engine.
-   **[Standard Configurator and Advanced Configurator](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_and_standard_configurator.htm&language=en_US&type=5)**  
    Product Configurator provides the Business Rules Engine and the Constraint Rules Engine. To use simple product configuration rules, use Standard Configurator. To use large and complex product configuration rules, use Advanced Configurator.
-   **[Specify Which Rule Engine to Use](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_specify_rule_engine.htm&language=en_US&type=5)**  
    Use the Transaction Type field in a quote to specify the rule engine to use for validating product configurations and executing configuration rules and constraints. Create Transaction Processing Type records based on your requirements, and then specify the default rule engine on the Revenue Settings page to validate product configurations and execute rules and constraints.
-   **[Use Constraint Builder With Constraint Rules Engine](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_constraint_builder.htm&language=en_US&type=5)**  
    Use Constraint Builder to create constraint models that manage complex configuration and validation for your products. Constraint models describe real-world entities and define their relationships with one another. Constraint Builder uses constraints in addition to if-then rules to customize complex products quickly and accurately.
-   **[Create and Test a Constraint in Constraint Rules Engine](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_create_constraint_model.htm&language=en_US&type=5)**  
    Create a constraint using the Constraint Builder and test it within the Configurator UI. The example defines constraints for default values based on a selected state and product structure.
-   **[Limitations and Known Issues](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_limitations.htm&language=en_US&type=5)**  
    Understand the current limitations and known issues when using Constraint Rules Engine for insurance product modeling.
-   **[Example Constraints for Insurance Product Models](https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configuration_usecases.htm&language=en_US&type=5)**  
    Explore constraint examples that demonstrate how to model insurance-specific logic using Advanced Configurator.

#### See Also

-   [Work With the Product Configurator in Revenue Cloud](https://help.salesforce.com/s/articleView?id=ind.product_configurator_work_with_product_configurator.htm&language=en_US&type=5)
-   [Set Up Configurator With Business Rules Engine](https://help.salesforce.com/s/articleView?id=ind.product_configurator_set_up_configuration_rules.htm&language=en_US&type=5)
-   [Set Up Configurator With Constraint Rules Engine](https://help.salesforce.com/s/articleView?id=ind.product_configurator_set_up_advanced_configurator.htm&language=en_US&type=5)
-   [Specify Which Rules Engine to Use](https://help.salesforce.com/s/articleView?id=ind.product_configurator_specify_which_rule_engine_to_use.htm&language=en_US&type=5)
-   [Business Rules Engine and Constraint Rules Engine](https://help.salesforce.com/s/articleView?id=ind.product_configurator_standard_and_advanced_configurators.htm&language=en_US&type=5)
-   [Use Constraint Builder With Constraint Rules Engine](https://help.salesforce.com/s/articleView?id=ind.product_configurator_constraint_builder.htm&language=en_US&type=5)
-   [Context Definitions](https://help.salesforce.com/s/articleView?id=ind.context_service_context_definitions.htm&language=en_US&type=5)

Did this article solve your issue?

Let us know so we can improve!

YesNo