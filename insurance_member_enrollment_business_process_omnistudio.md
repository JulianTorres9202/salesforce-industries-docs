---
title: "Member Enrollment Business Process"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_business_process_omnistudio.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Member Enrollment Business Process

Member Enrollment Business Process[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Member Enrollment Business Process

After your organization has signed a contract for insurance services, you can enroll yourself and your family in medical, dental, and vision plans of your choice. We've created a simple process to show this can be done. Read on for details of how you can quickly enroll yourself.

[](https://help.salesforce.com/s?language=en_US)

## Member Enrollment OmniScript Flow

You can find the member enrollment OmniScript in the Vlocity OmniScript Designer mode under:

-   Type - InsMember/enrollment
-   OmniScript name - Member Enrollment

The OmniScript uses Data Mappers to get account and member details. It then uses an Integration procedure to get the product information from the contract.

Next, the OmniScript displays member and dependent information for review. Additional dependents can be added at this stage.

The OmniScript uses a series of Data Mappers to extract the verified member information and then transform the data for medical, dental, and vision plans.

Next, the OmniScript gathers information about members to be included in medical plans.

Next, an Integration Procedure merges the list for selected members for medical plans. Now the MemberEnrollmentMedical1 OmniScript is called to enroll members into medical plans.

Now the OmniScript gathers information about members to be included in dental plans.

Next, an Integration Procedure merges the list for selected members for dental plans. Now the MemberEnrollmentDental1 OmniScript is called to enroll members into dental plans.

Now the OmniScript gathers information about members to be included in vision plans.

Next, an Integration Procedure merges the list for selected members for vision plans. Now the MemberEnrollmentVision1 OmniScript is called to enroll members into vision plans.

Now the MemberEnrollmentAdditional1 OmniScript is called to enroll the primary member in additional plans.

Now an Integration Procedure calls the InsEnrollmentService:enrollPlans service to enroll the user into the selected medical, dental, vision, and additional plans. Lastly, the OmniScript displays a confirmation of the selected plans and their details.

[](https://help.salesforce.com/s?language=en_US)

## What's In the Member Enrollment OmniScript?

The member enrollment OmniScript calls other OmniScripts:

-   [MemberEnrollmentMedical](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_medical_omniscript_omnistudio.htm&language=en_US&type=5 "During the enrollment process, this OmniScript Configures member enrollment for medical plans.")
    
-   [MemberEnrollmentDental](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_dental_omniscript_omnistudio.htm&language=en_US&type=5 "During the enrollment process, this OmniScript Configures member enrollment for dental plans.")
    
-   [MemberEnrollmentVision](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_vision_omniscript_omnistudio.htm&language=en_US&type=5 "During the enrollment process, this OmniScript Configures member enrollment for vision plans.")
    
-   [MemberEnrollmentAdditional](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_additional_omniscript_omnistudio.htm&language=en_US&type=5 "During the enrollment process, this OmniScript configures member enrollment for additional plans.")
    

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

FetchAccountDetails

 | 

Omnistudio Data Mapper Extract Action

 | 

Retrieves the account details and insured party specifications.

 | 

Ins\_readAccountDetails\_MemberEnrollmentOS

 |
| 

getCensusMembers

 | 

Data Mapper Extract Action

 | 

Retrieves census member information, contract ID, and producer details.

 | 

Ins\_getCensusMemberDetails

 |
| 

getProductIdForConditionalView

 | 

Integration Procedure Action

 | 

Retrieves the product ID from the contract record.

 | 

Ins\_ReadProductIdForConditionCheck\_OS

 |
| 

memberDetails

 | 

Step

 | 

Displays the member's details as noted in the company's records.

 | 

None

 |
| 

SetErrors1

 | 

Set Errors

 | 

Displays an error if the user has not agreed to terms and conditions.

 | 

None

 |
| 

createContactsForMembers

 | 

Integration Procedure Action

 | 

Creates a contact record for the member and links the contact record to the census record.

 | 

ins\_EnrollmentMemberCreateContact

 |
| 

setType

 | 

Set Values

 | 

Sets values of Medical, Dental, Vision, Term, and Additional to the insurance type.

 | 

None

 |
| 

setPrimaryMemberValuesforProducts

 | 

Set Values

 | 

Assigns the value of the primary member to the products.

 | 

None

 |
| 

medical

 | 

Step

 | 

Displays the form to select members to be enrolled for medical plans.

 | 

None

 |
| 

setCountM

 | 

Set Values

 | 

Sets the count for the medical plans depending on the user's choice.

 | 

None

 |
| 

SetMedical

 | 

Set Values

 | 

Sets cart value for the medical plan selected by the user.

 | 

None

 |
| 

dental

 | 

Step

 | 

Displays the form to select members to be enrolled for dental plans.

 | 

None

 |
| 

setCountD

 | 

Set Values

 | 

Sets the count for the dental plans depending on the user's choice.

 | 

None

 |
| 

SetMedcalDental

 | 

Set Values

 | 

Sets cart values for the medical and dental plans selected by the user.

 | 

None

 |
| 

vision

 | 

Step

 | 

Displays the form to select members to be enrolled for vision plans.

 | 

None

 |
| 

setCountV

 | 

Set Values

 | 

Sets the count for the vision plans depending on the user's choice.

 | 

None

 |
| 

setCartMedicalDentalVision

 | 

Set Values

 | 

Sets cart values for the medical, dental , and vision plans selected by the user.

 | 

None

 |
| 

term

 | 

Step

 | 

Displays the form to select term plans.

 | 

None

 |
| 

setCountT

 | 

Set Values

 | 

Sets the count for the term plans depending on the user's choice.

 | 

None

 |
| 

etCartMedicalDentalVisionTerm

 | 

Set Values

 | 

Sets cart values for the medical, dental , vision, and term plans selected by the user.

 | 

None

 |
| 

additional

 | 

Step

 | 

Displays the form to select additional plans.

 | 

None

 |
| 

setCountA

 | 

Set Values

 | 

Sets the count for the additional plans depending on the user's choice.

 | 

None

 |
| 

setCHAdditionalPlanDetails

 | 

Set Values

 | 

Sets cart value for the Critical Illness plan selected by the user.

 | 

None

 |
| 

setSIAdditionalPlanDetails

 | 

Set Values

 | 

Sets cart value for the Supplemental Health plan selected by the user.

 | 

None

 |
| 

setAdditionalPremiums

 | 

Set Values

 | 

Assigns values to additional premiums, if any.

 | 

None

 |
| 

setCartMedicalDentalVisionAdditional

 | 

Set Values

 | 

Sets cart values for the medical, dental , vision, term, and additional plans selected by the user.

 | 

None

 |
| 

ReviewDetailsCard

 | 

Step

 | 

Displays all the different plans selected by the user.

 | 

None

 |
| 

ReviewScreenSetError

 | 

Set Errors

 | 

Displays an error if the user does not accept terms and conditions.

 | 

None

 |
| 

enrollPlansForMedical

 | 

Integration Procedure Action

 | 

Uses the InsEnrollmentService service to enroll the member and any dependents in medical plans. It also generates a policy number.

 | 

EnrollPlanMedical

 |
| 

enrollPlansForDental

 | 

Integration Procedure Action

 | 

Uses the InsEnrollmentService service to enroll the member and any dependents in dental plans. It also generates a policy number.

 | 

EnrollPlanDental

 |
| 

enrollPlansForVision

 | 

Integration Procedure Action

 | 

Uses the InsEnrollmentService service to enroll the member and any dependents in vision plans. It also generates a policy number.

 | 

EnrollPlanVision

 |
| 

enrollPlansForTerm

 | 

Integration Procedure Action

 | 

Uses the InsEnrollmentService service to enroll the member and any dependents in term plans. It also generates a policy number.

 | 

InsEnrollmentTerm\_EnrollPlan

 |
| 

enrollPlansForAdditional

 | 

Integration Procedure Action

 | 

Uses the InsEnrollmentService service to enroll the member and any dependents in additional plans. It also generates a policy number.

 | 

EnrollPlanAdditional

 |
| 

ConfirmationStep

 | 

Step

 | 

Displays the enrollment statement with details of all the plans the member has enrolled in.

 | 

None

 |
| 

NavigateAction1

 | 

Navigate Action

 | 

Navigates the user back to the policyholder Home page.

 | 

None

 |

[](https://help.salesforce.com/s?language=en_US)

## What's Next

Want to see the OmniScript in action? Read [Member Enrollment Through the Policyholder Site](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_through_the_policyholder_site_omnistudio.htm&language=en_US&type=5 "If you are an employee of a group associated with a Census in an Active Contract that has the User Community Activated, you have access to a nifty policyholder digital Experience Site. You can log into the site and perform multiple tasks, including enrolling yourself into a policy of your choice.").

-   **[Member Enrollment Through the Policyholder Site](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_through_the_policyholder_site_omnistudio.htm&language=en_US&type=5)**  
    If you are an employee of a group associated with a Census in an Active Contract that has the User Community Activated, you have access to a nifty policyholder digital Experience Site. You can log into the site and perform multiple tasks, including enrolling yourself into a policy of your choice.
-   **[Member Enrollment Medical OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_medical_omniscript_omnistudio.htm&language=en_US&type=5)**  
    During the enrollment process, this OmniScript Configures member enrollment for medical plans.
-   **[Member Enrollment Dental OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_dental_omniscript_omnistudio.htm&language=en_US&type=5)**  
    During the enrollment process, this OmniScript Configures member enrollment for dental plans.
-   **[Member Enrollment Vision OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_vision_omniscript_omnistudio.htm&language=en_US&type=5)**  
    During the enrollment process, this OmniScript Configures member enrollment for vision plans.
-   **[Member Enrollment Additional OmniScript](https://help.salesforce.com/s/articleView?id=ind.insurance_member_enrollment_additional_omniscript_omnistudio.htm&language=en_US&type=5)**  
    During the enrollment process, this OmniScript configures member enrollment for additional plans.

Did this article solve your issue?

Let us know so we can improve!

YesNo