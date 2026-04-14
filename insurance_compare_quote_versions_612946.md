---
title: "Compare Quote Versions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_compare_quote_versions_612946.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Compare Quote Versions

Compare Quote Versions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Compare Quote Versions

You can compare versions of a quote on a Quote record.

1.  Click the **Version History** tab.
2.  Select at least two versions that you want to compare. You can compare up to three versions at a time. You can also compare versions of the quote to the existing policy by selecting **Compare to Policy**.
    
    Note
    
    A star next to the quote name indicates the most recent version.
    
3.  Click the **Compare Versions** button.
4.  Review the side-by-side view of the selected versions. Expandable accordion elements contain the details of the quote and each insured item.
    
    To resolve errors about missing fields when comparing versions of a quote to an existing policy, edit the field sets used by Version History:
    
    -   For the Quote object, the `QuoteCompareDetails` field set.
        
    -   For the Insurance Policy object, the `Ins_ComparePolicyHeader` field set.
        
    
    From Object Manager, find and select the appropriate object. Go to **Field Sets**, and then click the field set. Drag the missing fields from the object palette and drop them into the **In the Field Set** container.
    
5.  Click the details or an insured item to show a breakdown of the differences between quote versions.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    An orange asterisk after the label indicates line items that are different between versions.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo