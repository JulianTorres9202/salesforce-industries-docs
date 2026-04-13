---
title: "Create Custom Context Definition and Mapping"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_create_custom_defintion_mapping.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Create Custom Context Definition and Mapping

Create Custom Context Definition and Mapping[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create Custom Context Definition and Mapping

Customise the InsBrokeragePolicyContext context definition to meet your business requirements.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

| User Permissions Needed |
| --- |
| To create custom context definitions and mappings: | Context Service Admin |

See [Context Definitions](https://help.salesforce.com/s/articleView?id=ind.context_service_context_definitions.htm&language=en_US&type=5) for more information on how to create, activate, extend, upgrade, and clone a context definition.

1.  In Setup, find and select **Context Definitions**.
2.  Click the action menu for InsBrokeragePolicyContext context definition and select **Extend**.
3.  Enter a name and save your changes.
    
    The context definition extension is an asynchronous process and may take some time to complete. The extended definition gets created and appears under the Custom Definitions, and it inherits the entire structure and mapping from the standard context definition.
    
4.  To add new context mapping, follow [these](https://help.salesforce.com/s/articleView?id=ind.context_service_add_context_mapping.htm&language=en_US&type=5) instructions.
    
    Deactivate the context definition before adding any mappings. Ensure not to select the Automatic Salesforce object mapping checkbox because the automatic mapping is not supported for Insurance Brokerage.
    
    Ensure that the Required fields are mapped during the manual mapping to avoid unknown errors when performing policy lifecycle operations.
    
5.  Activate the context definition.

Did this article solve your issue?

Let us know so we can improve!

YesNo