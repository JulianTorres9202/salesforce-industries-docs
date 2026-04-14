---
title: "Digital Experience Site Component Customization"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_digital_experience_site_component_customization_overview_649514.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Digital Experience Site Component Customization

Digital Experience Site Component Customization[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Digital Experience Site Component Customization

We've provided out-of-the-box components for Insurance Experience sites, but we know you'll probably want to brand them with your logos, icons, colors, and fonts for your customers to see. You can also customize the data that's displayed.

Most of the components that come out-of-the-box are built using OmniStudio FlexCards. When you activate a FlexCard, it compiles an LWC. It's that LWC that you place in the Digital Experience site.

Think about customizing site components in three ways:

-   Look, feel, form, and organization
    
    In addition to customizing the look and feel of the components, you can change the placement of elements on the cards to create a different flow of information.
    
-   Data
    
    You can also add and remove data on cards. To do this, you may need to create new data sources (Omnistudio Data Mappers and Integration Procedures), or make changes to the existing out-of-the-box data sources used by the components.
    
-   New and different
    
    If the components we created don't meet all your needs, you can create your own. We recommend that you use FlexCards to build new components for your sites.
    

[](https://help.salesforce.com/s?language=en_US)

## Workflow for Configuring FlexCard-Based Digital Experience Site Components

The process for configuring most of the site components is a little bit complicated, but don't worry. You'll get the hang of it.

[](https://help.salesforce.com/s?language=en_US)

**Customizing Digital Experience Site Components Flow**

To customize FlexCard-based components, follow the flow diagram above. Each step in the diagram has its own topic:

1.  [Clone a Component's FlexCard](https://help.salesforce.com/s/articleView?id=ind.insurance_t_clone_a_component_s_flexcard_649602.htm&language=en_US&type=5 "When you want to customize a component for the Vlocity Insurance Broker or Policyholder Experience site, the first task is to clone the component's FlexCard.")
    
2.  [Manage the Data Source for an Experience Component](https://help.salesforce.com/s/articleView?id=ind.insurance_manage_the_data_source_for_an_experience_component_649647.htm&language=en_US&type=5 "Some Experience components use data sources to pull in information to display.")
    
3.  [Customize a Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_customize_a_component_649791.htm&language=en_US&type=5 "To customize an Experience component, you can make changes to the FlexCard for that component. Changes can include adding elements, making changes to the existing element, and removing elements.")
    
4.  [Replace a Customized LWC on an Experience Component](https://help.salesforce.com/s/articleView?id=ind.insurance_replace_a_customized_lwc_on_an_experience_component_649863.htm&language=en_US&type=5 "Some Experience components call Lightning Web Components (LWCs). If the LWC is actually part of another experience component you customized, you need to remove the old LWC and add the customized one to the FlexCard of the component you're working on.")
    
5.  [Add Customized Components to the Site](https://help.salesforce.com/s/articleView?id=ind.insurance_add_customized_components_to_the_site_649927.htm&language=en_US&type=5 "When you customize Experience components (or create new ones), you need to add them to your experience site so your end users can see them.")
    

[](https://help.salesforce.com/s?language=en_US)

## Non-FlexCard Based Components

A few components are not built using FlexCards. Instead, they are:

-   LWCs
    
    These components are used by other UIs as well as Experience sites.
    
    After you extend any of these components, you need to go through the same process to replace the out-of-the-box component with your extended component as you do with the components that use FlexCards for customization. [Add Customized Components to the Site](https://help.salesforce.com/s/articleView?id=ind.insurance_add_customized_components_to_the_site_649927.htm&language=en_US&type=5 "When you customize Experience components (or create new ones), you need to add them to your experience site so your end users can see them.") tells you how.
    
-   Classic card-based components
    
    Use the same process to customize these components as you use for the FlexCard components, but use the Vlocity Cards designer to customize the cards.
    

-   **[Clone a Component's FlexCard](https://help.salesforce.com/s/articleView?id=ind.insurance_t_clone_a_component_s_flexcard_649602.htm&language=en_US&type=5)**  
    When you want to customize a component for the Vlocity Insurance Broker or Policyholder Experience site, the first task is to clone the component's FlexCard.
-   **[Manage the Data Source for an Experience Component](https://help.salesforce.com/s/articleView?id=ind.insurance_manage_the_data_source_for_an_experience_component_649647.htm&language=en_US&type=5)**  
    Some Experience components use data sources to pull in information to display.
-   **[Customize a Component](https://help.salesforce.com/s/articleView?id=ind.insurance_t_customize_a_component_649791.htm&language=en_US&type=5)**  
    To customize an Experience component, you can make changes to the FlexCard for that component. Changes can include adding elements, making changes to the existing element, and removing elements.
-   **[Replace a Customized LWC on an Experience Component](https://help.salesforce.com/s/articleView?id=ind.insurance_replace_a_customized_lwc_on_an_experience_component_649863.htm&language=en_US&type=5)**  
    Some Experience components call Lightning Web Components (LWCs). If the LWC is actually part of another experience component you customized, you need to remove the old LWC and add the customized one to the FlexCard of the component you're working on.
-   **[Add Customized Components to the Site](https://help.salesforce.com/s/articleView?id=ind.insurance_add_customized_components_to_the_site_649927.htm&language=en_US&type=5)**  
    When you customize Experience components (or create new ones), you need to add them to your experience site so your end users can see them.

Did this article solve your issue?

Let us know so we can improve!

YesNo