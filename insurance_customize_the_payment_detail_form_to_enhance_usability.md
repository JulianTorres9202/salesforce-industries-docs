---
title: "Customize the Payment Detail Form to Enhance Usability"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_customize_the_payment_detail_form_to_enhance_usability.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize the Payment Detail Form to Enhance Usability

Customize the Payment Detail Form to Enhance Usability[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize the Payment Detail Form to Enhance Usability

Claims adjusters can process losses more efficiently by using forms that show only the elements that they need in an intuitive layout.

The **New Item Loss** form walks users through a logical flow of information, showing:

-   **Description** and **Payee** first along with **Benefit Type**, if it’s part of the coverage spec
    
-   Custom fields
    
-   **Claim Amount** or a **Calculate** button, as appropriate, and **Adjusted Amount**
    

[](https://help.salesforce.com/s?language=en_US)For example, a rental car coverage uses a custom field set with **Limit Unit Count** (a number) and **Limit Unit of Measure** (days), but not **Claim Amount**. On the corresponding payment detail form, the user enters 4 Days of car rental. To calculate the default benefit amount for the **Adjusted Amount** field, they click **Calculate**.

[](https://help.salesforce.com/s?language=en_US)**Where:** Available in Spring '22 and later releases.

**Why:** Each line of business can involve different processes and data entry requirements. Account for these differences by configuring payment detail processes at the coverage spec level. Corresponding payment detail forms can then guide claims adjusters through expected interactions logically and consistently.

**How:** Configure a custom field set on the Claim Coverage Payment Detail object. To associate the custom field set with a Coverage Spec, use the **Insurance Configuration Setup** custom setting. After you complete the configuration tasks, the payment detail form shows the custom fields that are associated with the selected coverage. If needed, the form also shows a **Calculate** button.

## See Also

[Customize the Claim Loss Payment Detail Form](https://help.salesforce.com/s/articleView?id=ind.insurance_customize_the_payment_detail_form_618950.htm&language=en_US&type=5 "Each line of business can involve different processes and data entry requirements. Account for these differences by configuring payment detail processes at the coverage spec level. Corresponding payment detail forms can then guide claims adjusters through expected interactions logically and consistently.")

Did this article solve your issue?

Let us know so we can improve!

YesNo