---
title: "Update the Experience Site CSS"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_update_the_experience_site_css_650113.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Update the Experience Site CSS

Update the Experience Site CSS[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Update the Experience Site CSS

Update the Experience site CSS to ensure that buttons and links display correctly.

The highlighted area in this flow shows where you are in the process of setting up your Experience site:

1.  On the Experience Builder page, click the **Theme** button on the left side of the screen.
2.  Select **</> Edit CSS** from the dropdown menu.
3.  Click **Use Overrides** in the **Override CSS?** window.
4.  Paste this custom CSS into the **Edit CSS** window:
    
    ```
    .via-nds .nds-communities-policy-card .nds-communities-billing .nds-button_brand .nds-action_text {
    	 color: white;
    }
    .via-nds .nds-communities-policy-card .nds-communities-policy-table .nds-text-title_caps{
    	font-size: .75rem;
        color: #706E6B;
    }
    .via-nds .nds-communities-policy-card .nds-communities-policy-table .nds-text-title_caps:hover{
        text-decoration: none;
        cursor:default
    }
    ```
    
5.  Click **Save**.

[](https://help.salesforce.com/s?language=en_US)

[Hide or Show Components for Mobile](https://help.salesforce.com/s/articleView?id=ind.insurance_hide_or_show_components_for_mobile_650158.htm&language=en_US&type=5 "Some components are designed specifically for mobile devices. To ensure a seamless experience for your desktop and mobile users, choose to hide or show components depending on the type of device they are using.")

Did this article solve your issue?

Let us know so we can improve!

YesNo