---
title: "Create a Request Insurance Proof Action"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_request_insurance_proof_action.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Request Insurance Proof Action

Create a Request Insurance Proof Action[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Request Insurance Proof Action

To give your users quick access to the Request Insurance Proof Omniscript, create an action launcher deployment that uses the service process template. If you have an existing action launcher deployment, add the Request Insurance Proof Omniscript to it.

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To set up the Request Insurance Proof service process:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Industries Service Process, Industry Service Excellence, Omnistudio, Case, Service Catalog Request objects Read, Create, Edit, Delete, View All Records</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">FSC Insurance</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">Financial Services Cloud Extension OR FSC Sales</p><p lwc-3eigj2skqo3="">OR</p><p lwc-3eigj2skqo3="">Financial Services Cloud Basic</p><p lwc-3eigj2skqo3="">OR</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Financial Services Cloud Standard</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To use Request Insurance Proof service process:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Industries Service Process, Industry Service Excellence, Omnistudio, Case, Service Catalog Request objects Read, Create, Edit, Delete, View All Records</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">FSC Insurance</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">Financial Services Cloud Extension OR FSC Sales</p><p lwc-3eigj2skqo3="">OR</p><p lwc-3eigj2skqo3="">Financial Services Cloud Basic</p><p lwc-3eigj2skqo3="">OR</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Financial Services Cloud Standard</p></td></tr></tbody></table>

1.  In Setup, in the Quick Find box, enter Action Launcher, then click **Action Launcher**. If you can't see Action Launcher, you need the Industries Service Excellence permission set. Contact your Salesforce Admin for help.
2.  Click **New Deployment**.
3.  Click **Next**.
4.  Enter a label and an API name.
5.  In Guidance to Show, select **OmniScripts**.
6.  Click **Next**.
7.  In the Available Objects list, select **Account** and move it to the Selected Objects list. The selected objects determine the objects where you can show the action.
8.  Click **Next**.
9.  In Select actions to add, select **Request Insurance Proof** action.
    
    The Omniscript must be activated to see it in the list. If you created a unique Omniscript with a different name, select your customized Omniscript.
    
10.  To add the Omniscript to the action launcher, click the + sign.
11.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo