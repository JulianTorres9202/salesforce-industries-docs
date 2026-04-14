---
title: "Update the insRecordEditor Class Name in the insQuote Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_extend_the_insquote_lightning_web_component_614176.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Update the insRecordEditor Class Name in the insQuote Lightning Web Component

Update the insRecordEditor Class Name in the insQuote Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Update the insRecordEditor Class Name in the insQuote Lightning Web Component

After you extend the `insRecordEditor` Lightning web component for use with the OmniScript, add the name of your extended `insRecordEditor` to the `insQuote` Lightning web component HTML file.

1.  Clone the insQuote Lightning web component and give the clone a new name.
2.  Open the cloned version of the Lightning web component in Salesforce DX.
3.  Extend the insRecordEditor Lightning web component based on your business requirements. For guidance, see [Extend Vlocity Lightning Web Components](https://help.salesforce.com/s/articleView?id=xcloud.os_extend_vlocity_lightning_web_components.htm&language=en_US&type=5).
4.  Open the HTML file.
5.  In this line, replace all instances of `ins-record-editor` with the name of your custom extended record editor component:
    
    ```
    <c-ins-record-editor class="vloc-ins-record-editor" in-debug-mode={inDebugMode} rule-context={ruleContext} root-channel={rootChannel} title={recordEditorTitle} editor-config={editorConfig} record-id={recordId} theme={theme}></c-ins-record-editor> 
    ```
    
    Note
    
    Be sure to use kebab case because that's what HTML understands.
    
6.  Save the HTML file of your extended Lightning web component and [deploy](https://help.salesforce.com/s/articleView?id=xcloud.os_deploy_lightning_web_components.htm&language=en_US&type=5) it into your org.

Did this article solve your issue?

Let us know so we can improve!

YesNo