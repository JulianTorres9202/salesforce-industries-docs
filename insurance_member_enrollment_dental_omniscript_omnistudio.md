---
title: "Member Enrollment Dental OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_dental_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Member Enrollment Dental OmniScript

Member Enrollment Dental OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Member Enrollment Dental OmniScript

During the enrollment process, this OmniScript Configures member enrollment for dental plans.

This OmniScript isn't meant to be used alone. It's called by the [Member Enrollment OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_business_process_omnistudio.htm&language=en_US&type=5 "After your organization has signed a contract for insurance services, you can enroll yourself and your family in medical, dental, and vision plans of your choice. We've created a simple process to show this can be done. Read on for details of how you can quickly enroll yourself.") in the Group Voluntary Benefits with OmniStudio Application.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The Member Enrollment Dental OmniScript takes the user data (from the previous steps in the flow that uses this OmniScript) and displays the available dental plans from the contract and lets you select your plan.

The OmniScript then uses this data to set values for the selected products and members to be enrolled.

[](https://help.salesforce.com/s?language=en_US)

## What's In It

You can find the Member Enrollment Dental OmniScript in the Vlocity OmniScript Designer as:

-   Type/SubType - ins/EnrolmentDental
-   OmniScript Name - MemberEnrollmentDental

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

userInputsDental

 | 

Omnistudio Data Mapper Transform Action

 | 

Transforms user input data into attribute data.

 | 

Ins\_TransUserInputs\_MemberEnrollmentDental

 |
| 

dentalProduct

 | 

Step

 | 

Lets the user select a dental plan and the members to be enrolled in it.

 | 

None

 |
| 

DataMapperExtractAction1

 | 

Data Mapper Extract Action

 | 

Retrieves the quote line items.

 | 

InsGetQuoteLineItemsDental

 |
| 

SetValuesDentalPlan

 | 

Set Values

 | 

Assigns an Id to the selected dental plan.

 | 

None

 |
| 

DentalSelectedProducts

 | 

Set Values

 | 

Assigns the relevant Ids to the selected plan and members enrolled in the plan.

 | 

None

 |
| 

transformForEnrollmentDental

 | 

Data Mapper Transform Action

 | 

Transforms the dental plan enrollment data into attribute data.

 | 

Ins\_TransForEnrolment\_MemberEnrollmentDental

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo