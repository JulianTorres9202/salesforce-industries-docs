---
title: "Customize the Expense Item Form to Enhance Usability"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_customize_the_expense_line_item_form_to_enhance_usability.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Customize the Expense Item Form to Enhance Usability

Customize the Expense Item Form to Enhance Usability[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Customize the Expense Item Form to Enhance Usability

Claims adjusters can process expenses more efficiently by using forms that show only the attributes specific to coverage in the expense line item form.

The **New Expense Item** form sends users through a logical flow of information, showing:

-   **Coverage**, **Description**, and **Payee** first along with **Benefit Type**, if it’s part of the coverage spec.
    
-   Custom fields
    
-   **Expense Amount**
    

Here's an example of payment details for Auto Car coverage. The Auto Car collision coverage spec is associated with a custom field set that has an **Expense Category** field.

**Where:** This change applies to Lightning Experience in Professional, Enterprise, and Unlimited editions with the Insurance Industries managed package.

**Why:** Each line of business can involve different processes and data entry requirements. Account for these differences by configuring expense payment processes at the coverage spec level. Then corresponding expense item forms can guide claims adjusters through expected interactions logically and consistently.

**How:** Configure a custom field set on the Claim Coverage Payment Detail object. To associate the custom field set with a Coverage Spec, use the **Insurance Configuration Setup** custom setting. After you complete the configuration tasks, the payment detail form shows the custom fields that are associated with the selected coverage.

Did this article solve your issue?

Let us know so we can improve!

YesNo