---
title: "Member Enrollment Medical OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_medical_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Member Enrollment Medical OmniScript

Member Enrollment Medical OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Member Enrollment Medical OmniScript

During the enrollment process, this OmniScript Configures member enrollment for medical plans.

This OmniScript isn't meant to be used alone. It's called by the [Member Enrollment OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_business_process_omnistudio.htm&language=en_US&type=5 "After your organization has signed a contract for insurance services, you can enroll yourself and your family in medical, dental, and vision plans of your choice. We've created a simple process to show this can be done. Read on for details of how you can quickly enroll yourself.") in the Group Voluntary Benefits with OmniStudio Application.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The Member Enrollment Medical OmniScript takes the user data (from the previous steps in the flow that uses this OmniScript) and displays the available medical plans from the contract and lets you select your plan.

The OmniScript then uses this data to set values for the selected products and members to be enrolled.

[](https://help.salesforce.com/s?language=en_US)

## What's In It

You can find the Member Enrollment Medical OmniScript in the Vlocity OmniScript Designer as:

-   Type/SubType - ins/EnrolmentMedical
-   OmniScript Name - MemberEnrollmentMedical

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

userInputsMedical

 | 

Omnistudio Data Mapper Transform Action

 | 

Transforms user input data into attribute data.

 | 

Ins\_TransUserInputs\_MemberEnrollmentOSMedical

 |
| 

medicalProduct

 | 

Step

 | 

Lets the user select a medical plan and the members to be enrolled in it.

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

Ins\_GetQuoteLineItemsMedical

 |
| 

SetValuesMedicalPlan

 | 

Set Values

 | 

Assigns an Id to the selected medical plan.

 | 

None

 |
| 

MedicalSelectedProducts

 | 

Set Values

 | 

Assigns the relevant Ids to the selected plan and members enrolled in the plan.

 | 

None

 |
| 

transformForEnrollmentMedical

 | 

Data Mapper Transform Action

 | 

Transforms the medical plan enrollment data into attribute data.

 | 

Ins\_TransForEnrolment\_MemberEnrollmentMedical

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo