---
title: "InsEnrollmentService: enrollMembers Coverage Check"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insenrollmentserviceenrollmembers_coverage_check_4584.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsEnrollmentService: enrollMembers Coverage Check

InsEnrollmentService: enrollMembers Coverage Check[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsEnrollmentService: enrollMembers Coverage Check

The InsEnrollmentService: enrollMembers service checks whether plans selected by census members have coverages.

**Why:** This prevents null pointer exception errors from occurring when the service creates dependent relationships (AssetPartyRelationship\_\_c objects) for plans without coverages.

Did this article solve your issue?

Let us know so we can improve!

YesNo