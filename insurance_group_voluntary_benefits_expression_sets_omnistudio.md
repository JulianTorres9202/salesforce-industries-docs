---
title: "Group Voluntary Benefits Expression Sets"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_group_voluntary_benefits_expression_sets_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Group Voluntary Benefits Expression Sets

Group Voluntary Benefits Expression Sets[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Group Voluntary Benefits Expression Sets

The expression sets for the product categories Vision, Dental, Medical, Critical Illness, and Dental Summary include variables, constants, decision matrices, and calculation steps.

To learn more about creating and editing expression sets, see [Expression Sets](https://help.salesforce.com/s/articleView?id=ind.expression_sets.htm&language=en_US&type=5).

## Expression Sets

Here are the expression sets we use for the Group Voluntary Benefits product categories:

| Product Category Name | Expression Set Name |
| --- | --- |
| Vision | VisionExpressionSet |
| Dental | DentalPremiumExpressionSet |
| Medical | MedicalExpressionSet |
| Critical Illness | CriticalIllnessExpressionSet |
| Dental Summary | DentalSummaryRating |

Here's what each step of these expression sets do:

1.  Checks the rating type, whether the calculation is for enrollment or quoting process.
2.  Uses the decision matrix to fetch the base premium based on the age and product code.
3.  Increases the premium by a corresponding factor multiplied to the base premium for each optional coverage selected.
4.  Calculates the member premium from the final premium that’s received in the previous two steps.
5.  Aggregates the member premium for a family or a census to calculate the corresponding premium for the product.

## Decision Matrices

All these expression sets call specific decision matrices that evaluates input parameters to provide base premium as the output.

| Expression Set Name | Decision Matrix Name (Lookup Table) | Input Field (Data Type) | Output Field (Data Type) |
| --- | --- | --- | --- |
| VisionExpressionSet | VisionRatingMatrixRRF | Age (Number Range) and Product Code (Text) | Base Premium (Currency) |
| DentalPremiumExpressionSet | DentalRatingMatrix | Age (Number Range) and Product Code (Text) | Base Premium (Currency) |
| MedicalExpressionSet | MedicalRatingMatrixRRF | Age (Number Range) and Product Code (Text) | Base Premium (Currency) |
| CriticalIllnessExpressionSet | CriticalillnessRatingMatrixRRF | Age (Number Range) and Product Code (Text) | Base Premium (Currency) |
| DentalSummaryRating | DentalSummaryRatingMatrix | Age (Number Range) and Product Code (Text) | Base Premium (Currency) |

Did this article solve your issue?

Let us know so we can improve!

YesNo