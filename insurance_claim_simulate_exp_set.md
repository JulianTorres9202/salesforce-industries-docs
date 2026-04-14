---
title: "Simulate and Activate Your Expression Set Version"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_claim_simulate_exp_set.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Simulate and Activate Your Expression Set Version

Simulate and Activate Your Expression Set Version[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Simulate and Activate Your Expression Set Version

After you modify the expressions and activate it for runtime usages, run simulations with default and custom test input variables. If the expression set doesn't work as expected, edit the elements and resimulate. When you're satisfied, activate the expression set version. The expression set version is linked to a context definition. Perform the simulation by using the context mappings available in the context definition.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3=""><a title="Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management." href="https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&amp;language=en_US&amp;type=5" lwc-3eigj2skqo3="">View supported editions.</a></td></tr></tbody></table>

| User Permissions Needed |
| --- |
| [View user permissions.](https://help.salesforce.com/s/articleView?id=ind.insurance_claim_perm_set_licenses.htm&language=en_US&type=5 "Give users access to Claims Management features. Review the supported edition and permission sets for Claims Management.") |

Simulate the custom expression set that you created to test if the expression set is working as intended, and then activate the set.

1.  Open your expression set version in Expression Set Builder.
2.  Click **Simulate**.
    
    The Input Mode dropdown displays the options for providing sample simulation data to the version.
    
3.  To enter sample values for the expression set variables in the JSON Input text box, select **Advanced** Input Mode.
4.  Enter sample values for the variables in the JSON Input text box.
    
    Alternatively, download the sample JSON input file, modify the file with your input values, and paste the updated JSON inputs in the textbox.
    
5.  Simulate the expression set.
6.  For comprehensive testing of the expression set, enter different variable values, change the mapping, and resimulate.
7.  If you're happy with the simulation result, activate the expression set version.

Did this article solve your issue?

Let us know so we can improve!

YesNo