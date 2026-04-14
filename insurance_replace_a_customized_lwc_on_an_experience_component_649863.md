---
title: "Replace a Customized LWC on an Experience Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_replace_a_customized_lwc_on_an_experience_component_649863.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Replace a Customized LWC on an Experience Component

Replace a Customized LWC on an Experience Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Replace a Customized LWC on an Experience Component

Some Experience components call Lightning Web Components (LWCs). If the LWC is actually part of another experience component you customized, you need to remove the old LWC and add the customized one to the FlexCard of the component you're working on.

Here's where you are in the process of customizing your Experience component:

Before You Begin:

-   Deactivate and customize the FlexCard that corresponds to the Custom LWC you need. To learn how, see [Customize a Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_customize_a_component_649791.htm&language=en_US&type=5 "To customize an Experience component, you can make changes to the FlexCard for that component. Changes can include adding elements, making changes to the existing element, and removing elements.").
    
-   Reactivate the FlexCard so it generates a new Custom LWC.
    

1.  On the card you're working with, click **Deactivate**.
2.  On the left pane, select the **Custom LWC** element.
    
    [](https://help.salesforce.com/s?language=en_US)The designer automatically shifts the right pane to the **Properties** tab.
    
3.  In **Custom LWC Name**, click the dropdown arrow and select the LWC you want to use.
4.  Under **Attributes**, click **\+ Add** to add any key/value pairs for attributes the LWC will use.
5.  Click **Activate**.

[](https://help.salesforce.com/s?language=en_US)

As the component activates, a new LWC is generated.

[](https://help.salesforce.com/s?language=en_US)

[Add Customized Components to the Site](https://help.salesforce.com/s/articleView?id=ind.insurance_add_customized_components_to_the_site_649927.htm&language=en_US&type=5 "When you customize Experience components (or create new ones), you need to add them to your experience site so your end users can see them.")

Did this article solve your issue?

Let us know so we can improve!

YesNo