---
title: "Update the Flow to Call the Apex Class"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_update_flow_to_call_apex_class.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Update the Flow to Call the Apex Class

Update the Flow to Call the Apex Class[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Update the Flow to Call the Apex Class

Update the Send Email with Attachment To Policy Holder action in the Flow to call the Apex class to send an email with attachment to the policyholder when a case is closed.

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To set up the Request Insurance Proof service process:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Industries Service Process, Industry Service Excellence, Omnistudio, Case, Service Catalog Request objects Read, Create, Edit, Delete, View All Records</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">FSC Insurance</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">Financial Services Cloud Extension OR FSC Sales</p><p lwc-3eigj2skqo3="">OR</p><p lwc-3eigj2skqo3="">Financial Services Cloud Basic</p><p lwc-3eigj2skqo3="">OR</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Financial Services Cloud Standard</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To use Request Insurance Proof service process:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Industries Service Process, Industry Service Excellence, Omnistudio, Case, Service Catalog Request objects Read, Create, Edit, Delete, View All Records</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">FSC Insurance</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">Financial Services Cloud Extension OR FSC Sales</p><p lwc-3eigj2skqo3="">OR</p><p lwc-3eigj2skqo3="">Financial Services Cloud Basic</p><p lwc-3eigj2skqo3="">OR</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Financial Services Cloud Standard</p></td></tr></tbody></table>

1.  Open the cloned orchestration that you created.
2.  Select **Notify Account and Close Case**.
3.  Click **Open Flow in Flow Builder**.
4.  Click **Send Email with Attachment To Policy Holder**.
5.  Click the plus symbol between the Send Email with Attachment to Policy Holder action and the Is Email Sent with Attachment decision element.
6.  Click **Action**.
7.  Search for and select the **Send Email to user with attachment** apex action.
8.  Enter these details:
    
    | FIELD NAME | VALUE |
    | --- | --- |
    | Label | Send Email with Attachment To Policy Holder |
    | API Name | SendEmailWithAttachmentToPolicyHolder |
    | Description | Calls an action that sends an email with attachment to the policy holder when a case is closed. |
    |   |
    | Store Output Values (Show advanced options) |
    | output | emailAttachmentStatus |
    |   |
    | Set Input Values for the Selected Action |
    | CaseId | caseId |
    | Email Body | ClosureEmailBodyTextTemplate |
    | Email Subject | ClosureEmailSubjectTextTemplate |
    | Send To Email Id | accountEmail |
    |   |
    | Show advanced options |
    | Manually assign variables | Select |
    
9.  Save the flow.

Did this article solve your issue?

Let us know so we can improve!

YesNo