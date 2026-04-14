---
title: "Experience Cloud Site Setup Checklist for Insurance"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_experience_cloud_site_setup_checklist__for_fsc_insurance.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Experience Cloud Site Setup Checklist for Insurance

Experience Cloud Site Setup Checklist for Insurance[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Experience Cloud Site Setup Checklist for Insurance

Use this checklist as a guide to perform Experience Cloud site setup tasks, to brand the home page and to update component properties.

## Before You Begin

_Gather your branding assets_

-   High-resolution image of your company logo
-   Color scheme (or an image to upload to automatically generate one)
-   Image to use as a compact header
-   Thumbnail images (385x385 pixels), if you're using [Featured Topics](https://help.salesforce.com/s/articleView?id=experience.networks_topics_featured.htm&language=en_US&type=5) in Salesforce Knowledge.

_Configure the internal Salesforce org_

-   Create a domain for the Financial Services Policyholder Portal. To setup the domain, see [Enable Digital Experiences](https://help.salesforce.com/s/articleView?id=experience.networks_enable.htm&language=en_US&type=5).
-   Choose a unique URL that works for your business, because you can't change it after it's been set.
-   Obtain a license for and enable Salesforce Knowledge.

## Launch the Financial Services Template

-   Under All Sites, click **New** and select **Financial Services**.
-   On the Financial Services page, click **Get Started** .
-   On the Enter a Name page, enter a name for your portal and click **Create**. If you're creating multiple sites, differentiate the beginning of the site name. Site are truncated in the global header dropdown menu. Users can see up to 32 characters of the name, and names include the status. Make sure that the visible part of the name allows users to distinguish between multiple sites.
-   Enter a URL for your site and click **Create**. This name is appended to the domain that you created when you [enabled digital experiences](https://help.salesforce.com/s/articleView?id=experience.networks_enable.htm&language=en_US&type=5) for this org.
    
-   [Specify object-level permissions](https://help.salesforce.com/s/articleView?id=analytics.bi_security_salesforce_object_field_levels_control_access.htm&language=en_US&type=5), For example, add Read access to Accounts, Contacts, Cases, Documents, Problems, and Goals.
    

## Perform General Configuration Steps in Setup

_Perform the following setup tasks from the Digital Experiences node in Setup._

-   [Add members](https://help.salesforce.com/s/articleView?id=platform.networks_customize_members.htm&language=en_US&type=5). Use profiles and permission sets to manage site membership during the setup process.
    
-   [Manage contributors](https://help.salesforce.com/s/articleView?id=experience.networks_access_control_overview.htm&language=en_US&type=5). Create roles, as needed, for the contributors who create, edit, review, and publish your site. Assign role-based access appropriate to each contributor's purview.
-   [Configure field level security](https://help.salesforce.com/s/articleView?id=platform.users_profiles_field_perms.htm&language=en_US&type=5). Assign security to control access to sensitive data in the site. Field permissions specify the access (view or edit) level for each field in a record.
-   [Configure login preferences](https://help.salesforce.com/s/articleView?id=experience.networks_customize_login.htm&language=en_US&type=5). Configure the default login, log out, password management, and self-registration options for your site.
-   Enable Change Data Capture to receive notification of changes to mortgage records. Prompt notification of changes to financial records can help speed approval of loan applications and support a responsive customer relationship culture. In Setup for your site, enter change data capture, select and shuttle mortgage objects from the Available Entities to the Selected Entities panel, and click **Save**. Then [subscribe to change notifications](https://developer.salesforce.com/docs/atlas.en-us.248.0.change_data_capture.meta/change_data_capture/cdc_subscribe.htm).

## Perform Configuration Steps in Experience Builder

-   From Setup, in the Quick Find box, enter Digital Experiences, and then select **All Sites**.
-   Brand your site. Add your logo and use Experience Builder tools to efficiently apply color and style to your landing page, its menus, and component flow tiles.
-   Edit Experience Builder pages. Remove unwanted default pages from the template and create more pages, as needed. To allow access the new pages you create, be sure to update the navigation menu.
-   Update component properties. Review and update the properties for the My Policies page, My Claims page, Policy Record page, Claim Record page and any other components that you add or use.
-   Add the URL path name of your Experience Cloud portal in the My Policies and My Claims components to give your portal users access to view the details of their policies and claims.
    
-   [Work with CMS Workspaces](https://help.salesforce.com/s/articleView?id=experience.networks_topics_overview.htm&language=en_US&type=5) to author and configure Salesforce Knowledge topics. to author and configure Salesforce Knowledge topics.
-   [Work with Moderation Workspaces](https://help.salesforce.com/s/articleView?id=experience.networks_moderation_overview.htm&language=en_US&type=5) to manage pre-configured moderation rules, to enable site members to flag inappropriate contributors and content, and to track and manage flagged site discussions.
-   [Activate your site](https://help.salesforce.com/s/articleView?id=experience.networks_publish.htm&language=en_US&type=5) to make it accessible to members.
    
-   Preview, test, and publish your site. Look at your site in a desktop browser window and on mobile devices. When you're happy with your changes, click **Activate** in the toolbar.

Did this article solve your issue?

Let us know so we can improve!

YesNo