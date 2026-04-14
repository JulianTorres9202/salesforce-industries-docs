---
title: "Member Enrollment Additional OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_additional_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Member Enrollment Additional OmniScript

Member Enrollment Additional OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Member Enrollment Additional OmniScript

During the enrollment process, this OmniScript configures member enrollment for additional plans.

This OmniScript isn't meant to be used alone. It's called by the [Member Enrollment OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_business_process_omnistudio.htm&language=en_US&type=5 "After your organization has signed a contract for insurance services, you can enroll yourself and your family in medical, dental, and vision plans of your choice. We've created a simple process to show this can be done. Read on for details of how you can quickly enroll yourself.") in the Group Voluntary Benefits with OmniStudio Application.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The Member Enrollment Additional OmniScript takes the user data (from the previous steps in the flow that uses this OmniScript) and displays the available additional plans from the contract and lets you select your plan.

The OmniScript then uses this data to set values for the selected products and members to be enrolled.

[](https://help.salesforce.com/s?language=en_US)

## What's In It

You can find the Member Enrollment Additional OmniScript in the Vlocity OmniScript Designer as:

-   Type/SubType - ins/EnrolmentAdditional
    
-   OmniScript Name - MemberEnrollmentAdditional
    

| 
Component Name

 | 

Component Type

 | 

What It Does

 | 

What It Calls

 |
| --- | --- | --- | --- |
| 

getAdditionalPlansQlClId

 | 

Omnistudio Data Mapper Extract Action

 | 

Retrieves the plan ID, product name, and quote line item ID for the additional product.

 | 

ins\_readAdditionaPlanQlIdClId\_OS

 |
| 

userInputsAdditional

 | 

Data Mapper Transform Action

 | 

Transforms the user information to attribute values for the additional product.

 | 

Ins\_TransUserInputs\_MemberEnrollmentAdditional\_OS

 |
| 

AdditionalProducts

 | 

Step

 | 

Displays the additional products to the user.

 | 

None

 |
| 

AdditionalSelectedProducts

 | 

Set Values

 | 

Assigns the selected product IDs to the AdditionalPlanEnrollment element.

 | 

None

 |
| 

transformForEnrollmentAdditional

 | 

Data Mapper Transform Action

 | 

Transforms the additional plan enrollment data into attribute data.

 | 

Ins\_TransForEnrolment\_MemberEnrollmentAdditional

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo