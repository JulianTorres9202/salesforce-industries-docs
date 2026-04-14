---
title: "Components to Activate"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_components_to_activate.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Components to Activate

Components to Activate[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Components to Activate

Activate the required OmniScripts, FlexCards, flows, and batch jobs for enrollment, termination, and quoting processes.

Here's a list of components you must activate:

| Feature | Component Type | Name | API Name |
| --- | --- | --- | --- |
| Large Group Enrollment | Flow | LG Enrollment Flow | LG\_Enrollment\_Flow |
| Batch Job | Insurance Enrollment | Insurance\_Enrollment |
| OmniScript | LGE/enrollmentProcess | NA |
| Large Group Quoting | Flow | Large Group Quoting Census Rating | Large\_Group\_Quoting\_Census\_Rating |
| Flow | Finish Processing Large Group Quote Census Rating | Finish\_Processing\_Large\_Group\_ Quote\_Census\_Rating |
| Batch Job | Census Rating | CensusRating |
| Contract Creation | OmniScript | InsGVB/CreateContract | NA |
| New Hire Enrollment | Flow | LG Enrollment Flow | LG\_Enrollment\_Flow |
| Batch Job | Insurance Enrollment | Insurance\_Enrollment |
| OmniScript | LGE/newHireEnrollmentProcess | NA |

Tip Even after activating these components, if one of the processes does not run as expected, try deactivating the existing component and activate it again.

Did this article solve your issue?

Let us know so we can improve!

YesNo