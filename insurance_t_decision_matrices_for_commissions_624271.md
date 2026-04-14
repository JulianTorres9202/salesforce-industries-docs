---
title: "Decision Matrices for Commissions"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_t_decision_matrices_for_commissions_624271.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Decision Matrices for Commissions

Decision Matrices for Commissions[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Decision Matrices for Commissions

Decision Matrices give you a way to implement complex rules in a systematic, readable way. To calculate commissions based on something more complex than a fixed percentage rate, you start by setting up Decision Matrices.

Use a flat matrix to have a single rate apply to a given premium. Use a tiered matrix to have different rates apply to each portion of the premium (like 5% for the first $1,000, 10% for the next $4,000, and so on).

Example: With this flat matrix, a $1,500 premium earns a 10% commission ($1,500 x 10% = $150). Premiums of $4,999 or more generate a 15% commission.

| 
Premium Low

 | 

Premium High

 | 

Rate

 |
| --- | --- | --- |
| 

0

 | 

999

 | 

7%

 |
| 

1,000

 | 

1,999

 | 

10%

 |
| 

2,000

 | 

4,999

 | 

12%

 |
| 

4,999

 |  | 

15%

 |

Example: With this tiered matrix, the first $999 of a $1,500 premium earns a 5% commission, and the next $501 earns 10%. That's ($999 x 5%) + ($501 x 10%), or $49.95 + $50.10 = $100.05.

| 
Producer Total Premium Low

 | 

Producer Total Premium High

 | 

Rate

 |
| --- | --- | --- |
| 

0

 | 

999

 | 

5%

 |
| 

1,000

 | 

5,999

 | 

10%

 |
| 

6,000

 | 

9,999

 | 

15%

 |
| 

10,000

 |  | 

20%

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo