---
title: "Extend the insRecordEditor Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_extend_the_insrecordeditor_lightning_web_component_614149.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Extend the insRecordEditor Lightning Web Component

Extend the insRecordEditor Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Extend the insRecordEditor Lightning Web Component

The `insRecordEditor` Lightning web component is one of the Lightning web components the Quote UI uses to display the window for adding and modifying an insured item on a quote. To get `insRecordEditor` to find and use the OmniScript that adds and modifies insured items, you need to extend this component.

1.  Open the cloned copy of the Lightning web component in Salesforce DX.
2.  Follow the steps in [Extend OmniStudio Vlocity Lightning Web Components](https://help.salesforce.com/s/articleView?id=xcloud.os_extend_omnistudio_lightning_web_components_58224.htm&language=en_US&type=5) to extend the component correctly, including replacing the `<c>` namespace instances.  to extend the component correctly, including replacing the `<c>` namespace instances.
3.  Open the HTML file in your extended component.
4.  Locate this section of the code:
    
    ```
    <template if:true={showEditorForm}>                        
        <!-- Remove error message below and replace with custom process-->                       
        <div class="slds-has-error slds-m-top_none slds-align_absolute-center">                           
            <div class="slds-form-element__help" {customLabels.InsQuoteCustomProcessMessage
            </div>                        
        </div>                    
    </template>
    ```
    
5.  Replace the error message with the OmniScript markup you copied to your clipboard in [Create an OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_omniscript_to_add_and_modify_insured_items_614121.htm&language=en_US&type=5 "Create a Lightning web component-based OmniScript for your users to use when they add and modify insured items to quotes.").
6.  Save the HTML file of your extended Lightning web component and [deploy](https://help.salesforce.com/s/articleView?id=xcloud.os_deploy_lightning_web_components.htm&language=en_US&type=5) it into your org.

Did this article solve your issue?

Let us know so we can improve!

YesNo