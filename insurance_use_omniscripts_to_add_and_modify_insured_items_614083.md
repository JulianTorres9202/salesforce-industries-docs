---
title: "Use OmniScripts to Add and Modify Insured Items"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_use_omniscripts_to_add_and_modify_insured_items_614083.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Use OmniScripts to Add and Modify Insured Items

Use OmniScripts to Add and Modify Insured Items[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Use OmniScripts to Add and Modify Insured Items

Vlocity Insurance offers an out-of-the-box form your users can use to add and modify insured items on the Quote UI. However, this form isn't customizable. If you want to use your own styles or add functionality to these processes, you can create an OmniScript and hook up that OmniScript to the Quote UI.

Before You Begin

Before you start creating this OmniScript, take a look at the form Vlocity provides for adding and modifying insured items to quotes.

-   On the Quote UI, open any quote.
    
-   Click the **Add** Item button. The out-of-the-box form appears.
    

If this form fulfills your business needs, you can stop here.

To configure the Quote UI to run OmniScripts you've created to add insured items and insured parties to quotes, complete these tasks.

1.  [Create an OmniScript to Add and Modify Insured Items](https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_omniscript_to_add_and_modify_insured_items_614121.htm&language=en_US&type=5 "Create a Lightning web component-based OmniScript for your users to use when they add and modify insured items to quotes.")
2.  [Extend the insRecordEditor Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_extend_the_insrecordeditor_lightning_web_component_614149.htm&language=en_US&type=5 "The insRecordEditor Lightning web component is one of the Lightning web components the Quote UI uses to display the window for adding and modifying an insured item on a quote. To get insRecordEditor to find and use the OmniScript that adds and modifies insured items, you need to extend this component.")
3.  [Update the insRecordEditor Class Name in the insQuote Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_extend_the_insquote_lightning_web_component_614176.htm&language=en_US&type=5 "After you extend the insRecordEditor Lightning web component for use with the OmniScript, add the name of your extended insRecordEditor to the insQuote Lightning web component HTML file.")
4.  [Set the Custom Attributes Process Option on Products](https://help.salesforce.com/s/articleView?id=ind.insurance_set_the_custom_attributes_process_option_on_products_614207.htm&language=en_US&type=5 "Expose the Custom Attributes Process on the Products page (if it's not already available on the page). This option tells the Quote UI that it should use the OmniScript rather than the out-of-the-box form to add and modify insured items to a quote.")
5.  [Use Add Item or Add Party on the Quote UI](https://help.salesforce.com/s/articleView?id=ind.insurance_use_add_item_or_add_party_on_the_quote_ui_614234.htm&language=en_US&type=5 "After you create an OmniScript, extend Lightning web components, and set the Custom Attributes Process option on the Products page, a user can complete processes in the Quote UI.")

-   **[Create an OmniScript to Add and Modify Insured Items](https://help.salesforce.com/s/articleView?id=ind.insurance_create_an_omniscript_to_add_and_modify_insured_items_614121.htm&language=en_US&type=5)**  
    Create a Lightning web component-based OmniScript for your users to use when they add and modify insured items to quotes.
-   **[Extend the insRecordEditor Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_extend_the_insrecordeditor_lightning_web_component_614149.htm&language=en_US&type=5)**  
    The `insRecordEditor` Lightning web component is one of the Lightning web components the Quote UI uses to display the window for adding and modifying an insured item on a quote. To get `insRecordEditor` to find and use the OmniScript that adds and modifies insured items, you need to extend this component.
-   **[Update the insRecordEditor Class Name in the insQuote Lightning Web Component](https://help.salesforce.com/s/articleView?id=ind.insurance_extend_the_insquote_lightning_web_component_614176.htm&language=en_US&type=5)**  
    After you extend the `insRecordEditor` Lightning web component for use with the OmniScript, add the name of your extended `insRecordEditor` to the `insQuote` Lightning web component HTML file.
-   **[Set the Custom Attributes Process Option on Products](https://help.salesforce.com/s/articleView?id=ind.insurance_set_the_custom_attributes_process_option_on_products_614207.htm&language=en_US&type=5)**  
    Expose the Custom Attributes Process on the Products page (if it's not already available on the page). This option tells the Quote UI that it should use the OmniScript rather than the out-of-the-box form to add and modify insured items to a quote.
-   **[Use Add Item or Add Party on the Quote UI](https://help.salesforce.com/s/articleView?id=ind.insurance_use_add_item_or_add_party_on_the_quote_ui_614234.htm&language=en_US&type=5)**  
    After you create an OmniScript, extend Lightning web components, and set the Custom Attributes Process option on the Products page, a user can complete processes in the Quote UI.

Did this article solve your issue?

Let us know so we can improve!

YesNo