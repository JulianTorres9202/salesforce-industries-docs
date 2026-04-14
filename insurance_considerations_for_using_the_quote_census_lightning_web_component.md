---
title: "Considerations for Using the Quote Census Lightning Web Component"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_for_using_the_quote_census_lightning_web_component.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Considerations for Using the Quote Census Lightning Web Component

Considerations for Using the Quote Census Lightning Web Component[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Considerations for Using the Quote Census Lightning Web Component

The Quote Census Lightning web component provides insurance carrier administrators and brokers a straightforward workflow for managing census data in small and medium group quotes.

| 
Quote Census Lightning Web Component

 | 

Description

 |
| --- | --- |
| 

insGroupCensus

 | 

Use this component in record pages such as the Quote record page. It works with Group Census Member records in the Salesforce data model, and on Customer Community portals such as a broker portal

 |
| 

insOsGroupCensus

 | 

Use this component for census uploads in an OmniScript quote workflow. It works with Group Census Member records in the Salesforce data model.

 |

## CSV Record Requirements

If you use CSV files as source files for group census data, prepare the data to ensure a smooth upload.

-   CSV files can't have an extra empty line at the end of the file.
    
-   Remove any trailing spaces before the comma in all column headers to improve upload performance.
    
-   Define `Relationship to Primary Member` as Self, Spouse, or Child.
    

Did this article solve your issue?

Let us know so we can improve!

YesNo