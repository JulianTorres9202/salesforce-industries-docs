---
title: "Add Namespace to Images on Header Components"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_add_namespace_to_images_on_header_components_649816.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Add Namespace to Images on Header Components

Add Namespace to Images on Header Components[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Add Namespace to Images on Header Components

For components that include background images, such as Policyholder site Header components, you need to add your namespace to the FlexCard to make the images show up. Here's how:

1.  On the FlexCard, click **Deactivate**.
2.  Select the **Block** element that contains the image.
3.  On the right pane, click **Style**.
4.  Scroll down to the **Appearance** section and go to the **Background Image Url** field.
    
    The URL for the image looks something like this:
    
    .../.../.../resource/InsNewportPortalImages/insHomeHeaderDesktop.png
    
5.  Add the namespace of your org to the URL.
    
    For example:
    
    .../.../.../resource/vlocity\_ins\_\_InsNewportPortalImages/insHomeHeaderDesktop.png
    

[](https://help.salesforce.com/s?language=en_US)

[](https://help.salesforce.com/s?language=en_US)As the card activates, a message tells you that the system is compiling an LWC.

[](https://help.salesforce.com/s?language=en_US)This is the LWC you replace the out-of-the-box LWC with in the Experience builder, so that users can take advantage of your customizations.

Did this article solve your issue?

Let us know so we can improve!

YesNo