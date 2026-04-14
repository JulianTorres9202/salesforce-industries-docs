---
title: "Create a Request Insurance Proof Service Process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_create_request_insurance_proof_service_process.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Create a Request Insurance Proof Service Process

Create a Request Insurance Proof Service Process[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Create a Request Insurance Proof Service Process

Create a unique version of the Request Insurance Proof service process and enter the details.

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">REQUIRED EDITIONS</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Experience in <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and <strong class="uicontrol" lwc-3eigj2skqo3="">Unlimited</strong> editions where Financial Services Cloud license is enabled with FSC Insurance add-on.</td></tr></tbody></table>

<table class="slds-table slds-table_bordered slds-m-bottom_small" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""><col style="width:50%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" colspan="2" class="slds-cell-wrap" lwc-3eigj2skqo3=""><strong lwc-3eigj2skqo3="">USER PERMISSIONS NEEDED</strong></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To set up the Request Insurance Proof service process:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Industries Service Process, Industry Service Excellence, Omnistudio, Case, Service Catalog Request objects Read, Create, Edit, Delete, View All Records</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">FSC Insurance</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">Financial Services Cloud Extension OR FSC Sales</p><p lwc-3eigj2skqo3="">OR</p><p lwc-3eigj2skqo3="">Financial Services Cloud Basic</p><p lwc-3eigj2skqo3="">OR</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Financial Services Cloud Standard</p></td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">To use Request Insurance Proof service process:</td><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><p lwc-3eigj2skqo3="">Industries Service Process, Industry Service Excellence, Omnistudio, Case, Service Catalog Request objects Read, Create, Edit, Delete, View All Records</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">FSC Insurance</p><p lwc-3eigj2skqo3="">AND</p><p lwc-3eigj2skqo3="">Financial Services Cloud Extension OR FSC Sales</p><p lwc-3eigj2skqo3="">OR</p><p lwc-3eigj2skqo3="">Financial Services Cloud Basic</p><p lwc-3eigj2skqo3="">OR</p><p style="margin-bottom:0;" lwc-3eigj2skqo3="">Financial Services Cloud Standard</p></td></tr></tbody></table>

1.  In Setup, in the Quick Find box, enter Service Process Studio, and then select **Service Process Studio**.
2.  Click **New Service Process**, and then click **Create from Template**.
3.  Select **Request Insurance Proof**, and click **Save & Launch**.
4.  Enter a process name and a unique API name.
    
    Note Make a note of the API name. It is used in the Process Insurance Proof Request orchestration template. Here, we have FSCIns\_RequestInsuranceProof as the API name used for the new service process which is used in orchestration initiation conditions \[Record.SvcCatalogItemDefinition.DeveloperName in the image\].
    
5.  Update the short and long description.
6.  Save your changes.

Did this article solve your issue?

Let us know so we can improve!

YesNo