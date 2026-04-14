---
title: "Fix Common Issues Found in Rules Debug Mode"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_fixcommon_issues_found_in_rules_debug_mode_611350.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Fix Common Issues Found in Rules Debug Mode

Fix Common Issues Found in Rules Debug Mode[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Fix Common Issues Found in Rules Debug Mode

There are a few issues that often come up when you're running rules debug mode. Check for the usual suspects at the root of the problem and take steps to fix things.

-   Does the Attribute Value = Token Value?
    
    If it doesn't, try the following:
    
    -   Refresh your browser.
        
    -   Reprice the quote by clicking **Rate Now**.
        
    -   If the mismatch of these values persists after you've done steps 1 and 2, contact Vlocity Support for assistance.
        
-   Is your expression formed correctly?
    
    -   Check the product code to make sure it points to an existing product.
        
    -   Check for typos.
        
-   Have you refreshed your browser lately?
    
    If not:
    
    -   Clear your cache.
        
    -   Refresh your browser.
        

If you find an issue with a rule, access the related attribute from a Product page to fix it.

1.  Open the Products page in a new browser tab.
2.  Navigate to the Product this attribute is attached to.
    
    This may be a root product spec, an insured item spec, a coverage spec, or an insured party spec.
    
3.  Find the attribute and click the rules icon (the little blue scales) for the attribute, or the attribute value for an attribute value rule.
4.  Make changes to the rule.
5.  Click **Update** to save the rule to the attribute.
6.  Back on the Quote UI, refresh your browser.
7.  Verify that the rule's expression is now correct on the quote.

Did this article solve your issue?

Let us know so we can improve!

YesNo