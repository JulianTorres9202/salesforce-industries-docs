---
title: "Context Definitions for Insurance Claims"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_cxt_definitions.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Context Definitions for Insurance Claims

Context Definitions for Insurance Claims[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Context Definitions for Insurance Claims

Improve the efficiency of sharing and using business application data with Context Service. This service helps your business users boost application performance by optimizing data access and eliminating redundant inputs. When an application requests data, Context Service gathers all required information from the database and loads it. It then delivers the necessary data to the appropriate processes to meet the application's needs.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

Insurance Claims Management supports two prebuilt context definitions. A context definition defines the relationship between the nodes and the attributes within each node. Your users can use nodes and attributes to easily access the relevant data from the mapped data source. Both context definitions provide a structured extensible framework that maps relationships between various sObjects. The context service efficiently manages and interacts with Claim data, enabling services to access, save, and modify mapped source data during transactions. Users can extend these standard contexts to include specific details tailored to their unique business needs, providing flexibility and comprehensive data handling.

-   **Claims Context:** Within this context, the SalesTransaction context nodes are mapped to Claim, ClaimAttribute, ClaimItem, ClaimItemAttribute, and ClaimItemRelatedObject. The Standard Configurator searches for SalesTransaction context nodes during the execution of claim workflow rules. This context is used during business processes such as the FNOL process, creating, updating, and retrieving claims, as well as for claim workflow rules.
    
-   **Policy Limit Context:** This context maps relationships for the InsPlcyLimit and InsPlcyLimitTracking sObjects. This context is used during the execution of default expression sets to calculate claim adjustments and process limits.
    

-   **[Configure Claim Context Mapping](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_conf_cxt_mapping.htm&language=en_US&type=5)**  
    You can select only one active context definition for the configuration.

Did this article solve your issue?

Let us know so we can improve!

YesNo