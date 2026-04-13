---
title: "Understand Impact on Existing Quotes"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_advanced_configurator_impact.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Understand Impact on Existing Quotes

Understand Impact on Existing Quotes[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Understand Impact on Existing Quotes

Before you enable Constraint Rules Engine, review how it affects quotes created before and after enablement.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong lwc-3eigj2skqo3="">Developer</strong>, <strong lwc-3eigj2skqo3="">Enterprise</strong>, and <strong lwc-3eigj2skqo3="">Unlimited</strong> Editions of Revenue Cloud where Product Configurator is enabled</td></tr></tbody></table>

When you enable Constraint Rules Engine (CRE) in Revenue Settings, Product Configurator begins using CRE to process configuration rules on new quotes. Quotes created before CRE was enabled don’t run CRE rules unless you migrate those rules to CML.

Best Practices

-   Because Constraint Rules Engine is in beta, validate the features with your product model in a sandbox before enabling in production.
-   After testing, migrate existing dynamic rules to CML and then enable Constraint Rules Engine for production use.

What to expect after enabling Constraint Rules Engine with dynamic rules

-   If Advanced Configurator is set as the default engine, all new quotes automatically use a Transaction Processing Type (TPT) with Advanced Configurator as the default rule engine. These quotes will use the constraint engine for rule processing.
-   If TPT with Standard Configurator is created and Standard Configurator is set as the default engine, both existing quotes and new quotes use Business Rules Engine for rule processing.

Did this article solve your issue?

Let us know so we can improve!

YesNo