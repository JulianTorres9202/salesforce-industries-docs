---
title: "View the Rules Log"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_view_the_rules_log_608231.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# View the Rules Log

View the Rules Log[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# View the Rules Log

The Rules Log shows a history of product underwriting (workflow) and state transition rule runs. For underwriting (workflow) rules, the log shows the history of rules run on a quote, policy, or claim. For state transition rules, the log shows the history of rules run on any object.

To view the Rules Log on the quote, asset (policy), insurance policy, or claim record page, click Rules Log or whatever name was defined for the Rules Log on the record page.

Important Product underwriting rules get triggered by service calls and by clicking state transitions in the UI. Editing the Status field manually in the UI doesn’t trigger underwriting rules, so the Rules Log doesn’t show the history of state transitions made this way.

![Rules Log entries with numbered sections and names](https://sf-zdocs-cdn-prod.zoominsoftware.com/tdta-insurance-260-0-0-production-enus/e4c2671d-0822-4c56-95dd-073f2b1f9ddc/insurance/images/r/ruleslog_uwrules.png)

[](https://help.salesforce.com/s?language=en_US)The Rules Log groups details by state transition (1). A count of rule runs appears next to transition names.

[](https://help.salesforce.com/s?language=en_US)Expand a product name (2) to review:

-   The name of each rule run.
    
-   Whether each rule passed or failed. Rules that evaluate to true have a green checkmark (3) next to them. Rules that evaluate to false have a circle-backslash symbol (4) next to them.
    
-   The name of the instance for which the rule was run, for example, a quote line item.
    

[](https://help.salesforce.com/s?language=en_US)Expand State Rules to review:

-   The name of each state rule run.
    
-   Whether each rule passed or failed.
    
-   The success or failure message for each rule (5).
    

Did this article solve your issue?

Let us know so we can improve!

YesNo