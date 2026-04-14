---
title: "Member Enrollment Vision OmniScript"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_vision_omniscript_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Member Enrollment Vision OmniScript

Member Enrollment Vision OmniScript[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Member Enrollment Vision OmniScript

During the enrollment process, this OmniScript Configures member enrollment for vision plans.

This OmniScript isn't meant to be used alone. It's called by the [Member Enrollment OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_business_process_omnistudio.htm&language=en_US&type=5 "After your organization has signed a contract for insurance services, you can enroll yourself and your family in medical, dental, and vision plans of your choice. We've created a simple process to show this can be done. Read on for details of how you can quickly enroll yourself.") in the Group Voluntary Benefits with OmniStudio Application.

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The Member Enrollment Vision OmniScript takes the user data (from the previous steps in the flow that uses this OmniScript) and displays the available vision plans from the contract and lets you select your plan and the members you want to add to it.

The OmniScript then uses this data to set values for the selected products and members to be enrolled and creates a policy.

[](https://help.salesforce.com/s?language=en_US)

## What's In It

You can find the Member Enrollment Vision OmniScript in the Vlocity OmniScript Designer as:

-   Type/SubType - ins/EnrolmentVision
    
-   OmniScript Name - MemberEnrollmentVision
    

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

userInputs

 | 

Omnistudio Data Mapper Transform Action

 | 

Transforms user input data into attribute data.

 | 

Ins\_TransUserInputs\_MemberEnrollmentOSVision

 |
| 

visionProduct

 | 

Step

 | 

Lets the user select a vision plan and the members to be enrolled in it.

 | 

None

 |
| 

getQuoteLineItemsVision

 | 

Data Mapper Extract Action

 | 

Retrieves the quote line items.

 | 

Ins\_GetQuoteLineItemsVision

 |
| 

SetValuesVisionPlan

 | 

Set Values

 | 

Assigns an Id to the selected vision plan.

 | 

None

 |
| 

VisionSelectedProducts

 | 

Set Values

 | 

Assigns the relevant Ids to the selected plan and members enrolled in the plan.

 | 

None

 |
| 

transformForEnrollmentVision

 | 

Data Mapper Transform Action

 | 

Transforms the vision plan enrollment data into attribute data.

 | 

Ins\_TransForEnrolment\_MemberEnrollmentVision

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo