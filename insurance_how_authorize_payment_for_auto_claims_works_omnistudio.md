---
title: "How Authorize Payment for Auto Claims Works"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_how_authorize_payment_for_auto_claims_works_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# How Authorize Payment for Auto Claims Works

How Authorize Payment for Auto Claims Works[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# How Authorize Payment for Auto Claims Works

Understand the workflow for payment authorization, and the levels of claim users and their authorities.

To learn about payment authorization, see [Create a Payment Authorization Workflow](https://help.salesforce.com/s/articleView?id=ind.insurance_finauth_create_workflow.htm&language=en_US&type=5 "Configure the building blocks of your business process for financial transaction payment authorization.").

## Claim Users and Authorities

Take a look at the roles and users for each level. The financial authorities and corresponding users, along with the required configurations are already configured in the Property and Casualty Express Org for payment authorization workflow to function.

| Level | Role | User Name |
| --- | --- | --- |
| Level 1 | Claims Team Handler | Vidya Kumar |
| Level 2 | Claims Team Member | Kim Park |
| Level 3 | Claims Team Leader | Aaron Matthews |

Limit how much users at each financial authority level can pay or approve at different levels for each type of financial activity by using User Financial Authority records.

| Claim Financial Authority Level | Coverage Spec | Loss Authority ($) | Expense Authority ($) |
| --- | --- | --- | --- |
| Level 1 | autoCollision | 2000 | 500 |
| Level 1 | autoBI | 2000 | 0 |
| Level 1 | autoPD | 0 | 500 |
| Level 2 | autoCollision | 4000 | 500 |
| Level 2 | autoBI | 10000 | 1000 |
| Level 2 | autoPD | 2000 | 500 |
| Level 3 | autoCollision | 10000 | 1000 |
| Level 3 | autoBI | 20000 | 1500 |
| Level 3 | autoPD | 5000 | 100 |

Did this article solve your issue?

Let us know so we can improve!

YesNo