---
title: "Make the Insurance Service Processes Visible to Your Portal Users"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_make_ins_service_processes_visible_to_your_portal_users.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Make the Insurance Service Processes Visible to Your Portal Users

Make the Insurance Service Processes Visible to Your Portal Users[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Make the Insurance Service Processes Visible to Your Portal Users

Show the actions to launch the prebuilt insurance service processes on the Insurance Client Portal so that your customer community users can easily create service requests without contacting your service agents.

-   Configure the required prebuilt insurance service processes in Salesforce.
-   Add the URL path name of your Experience Cloud portal in the Service Requests component to give your portal users access to view the details of their service requests. For more information, see [Update the URL Path Name](https://help.salesforce.com/s/articleView?id=ind.fsc_admin_update_the_url_path_name.htm&language=en_US&type=5).
    

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To customize and publish an Insurance client portal:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Be a member of the portal and have the Create and Set Up Experiences permission set</p><p lwc-3eigj2skqo3="">OR</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Be a member of the portal and be an experience admin or publisher in that portal</p></td></tr></tbody></table>

1.  To add the Omniscripts or intake forms of these service processes, create an Action Launcher deployment. See [Create an Action Launcher Deployment](https://help.salesforce.com/s/articleView?id=ind.create_an_action_launcher_deployment.htm&language=en_US&type=5).
    
    | SERVICE PROCESS | OMNISCRIPT |
    | --- | --- |
    | Request Insurance Proof | /FSCIns/RequestInsuranceProof/Multi-Language |
    
2.  From Setup, in the Quick Find box, enter Digital Experiences, and then select **All Sites**.
3.  Next to your Experience Cloud portal, click **Builder**.
4.  Click **Action Launcher**.
5.  Select the deployment that you created earlier.
6.  Preview and publish your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo