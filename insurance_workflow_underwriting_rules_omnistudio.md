---
title: "Workflow (Underwriting) Rules for the Multi Auto Product Model"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_workflow_underwriting_rules_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Workflow (Underwriting) Rules for the Multi Auto Product Model

Workflow (Underwriting) Rules for the Multi Auto Product Model[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Workflow (Underwriting) Rules for the Multi Auto Product Model

Multi Auto includes several workflow (underwriting) rules. These get run towards the end of the quoting process by the InsQuoteService:invokeProductRules service. This service is called by an integration procedure in the Auto quote OmniScript and by the Lightning Web Component in the Quote UI.

Workflow (underwriting) rules are created on the insurance root product spec, on the Rules tab.

[](https://help.salesforce.com/s?language=en_US)Here are the workflow rules we created on Multi Auto:

[](https://help.salesforce.com/s?language=en_US)You can modify these, delete those you don't want to use, and/or add your own.

Did this article solve your issue?

Let us know so we can improve!

YesNo