---
title: "Vlocity Object to Group Benefits Standard Object Model Mapping"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_object_to_group_benefits_standard_object_model_mapping.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Vlocity Object to Group Benefits Standard Object Model Mapping

. Vlocity Object to Group Benefits Standard Object Model Mapping[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Vlocity Object to Group Benefits Standard Object Model Mapping

Learn how fields in the Vlocity Group Benefits object model correspond to fields in the Salesforce object model. Use these field mappings when you create scripts that move Group Benefits data from one model to the other.

[](https://help.salesforce.com/s?language=en_US)

## Harmonized Objects

| 
Group Benefits Standard Object

 | 

Vlocity Object

 |
| --- | --- |
| 

GroupCensus

 | 

GroupCensus\_\_c

 |
| 

GroupCensusMember

 | 

GroupCensusMember\_\_c

 |
| 

GroupClass

 | 

GroupClass\_\_c

 |
| 

GroupClassContribution

 | 

GroupClassContribution\_\_c

 |
| 

InsuranceContract

This object is an extension of the existing Contract object, which is introduced to have insurance-specific fields.

 | 

Contract

 |
| 

ContractGroupPlan

 | 

ContractLineItem\_\_c (Plan)

 |
| 

GroupCensusMemberPlan

 | 

GroupCensusMemberPlan\_\_c

 |
| 

QuoteLineItemGroupClass

 | 

QuoteLineItemGroupClass\_\_c

 |

[](https://help.salesforce.com/s?language=en_US)

## GroupCensus Field Mapping

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Field Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

Name

 | 

Name

 | 

Name

 | 

Name

 | 

Text

 |
| 

ExternalIdentifier

 | 

External Identifier

 | 

Not Available

 | 

Not Available

 | 

Text(ExternalId)

 |
| 

SourceSystemType

 | 

Source System Type

 | 

CensusSource\_\_c

 | 

Source

 | 

Static Enum

 |
| 

Status

 | 

Status

 | 

CensusStatus\_\_c

 | 

Status

 | 

Static Enum

 |
| 

Type

 | 

Type

 | 

CensusType\_\_c

 | 

Type

 | 

Static Enum

 |
| 

MemberOptOutCount

 | 

Member Opt Out Count

 | 

CountOfDeclined\_\_c

 | 

No. Declined

 | 

Number (,)

 |
| 

MbrWithoutDependentCount

 | 

Member Without Dependent Count

 | 

CountOfEmployeeOnly\_\_c

 | 

No. Employee Only

 | 

Number (,)

 |
| 

MemberWithOneChildCount

 | 

Member With One Child Count

 | 

CountOfEmployeePlusChild\_\_c

 | 

No. Employee + Child

 | 

Number (,)

 |
| 

MbrWithMoreThan1ChldCount

 | 

Member With More Than One Child Count

 | 

CountOfEmployeePlusChildren\_\_c

 | 

No. Employee + Children

 | 

Number (,)

 |
| 

MbrWithMoreThan2ChldCount

 | 

Member With More Than Two Children Count

 | 

Not Available

 | 

Not Available

 | 

Number (,)

 |
| 

MemberWithDependentCount

 | 

Member With Dependent Count

 | 

CountOfEmployeePlusFamily\_\_c

 | 

No. Employee + Family

 | 

Number (,)

 |
| 

MemberWithSpouseCount

 | 

Member With Spouse Count

 | 

CountOfEmployeePlusSpouse\_\_c

 | 

No. Employee + Spouse

 | 

Number (,)

 |
| 

TotalMemberPlusDependent

 | 

Total Members Plus Dependents

 | 

CountOfEmployeesPlusDependents\_\_c

 | 

Total Employees + Dependents

 | 

Number (,)

 |
| 

TotalDependents

 | 

Total Dependents

 | 

NumberOfDependents\_\_c

 | 

Dependents

 | 

Number (,)

 |
| 

TotalMembers

 | 

Total Members

 | 

NumberOfMembers\_\_c

 | 

Members

 | 

Number (,)

 |
| 

FullTimeMemberCount

 | 

Full Time Member Count

 | 

CountOfFullTime\_\_c

 | 

No. Full Time

 | 

Number (,)

 |
| 

PartTimeMemberCount

 | 

Part Time Member Count

 | 

CountOfPartTime\_\_c

 | 

No. Part Time

 | 

Number (,)

 |
| 

EffectiveEndDate

 | 

Effective End Date

 | 

EffectiveEndDate\_\_c

 | 

End Date

 | 

Date

 |
| 

EffectiveStartDate

 | 

Effective Start Date

 | 

EffectiveStartDate\_\_c

 | 

Effective Date

 | 

Date

 |
| 

Account

 | 

Account

 | 

GroupId\_\_c

 | 

Group

 | 

Foreignkey Lookup ()

 |
| 

SourceSystemName

 | 

Source System Name

 | 

Not Available

 | 

Not Available

 | 

Text

 |
| 

UsageType

 | 

UsageType

 | 

Not Available

 | 

Not Available

 | 

Static Enum

 |
| 

Lead

 | 

Lead

 | 

Not Available

 | 

Not Available

 | 

Foreignkey Lookup ()

 |

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

AttributesSelectedValues\_\_c

 | 

AttributesSelectedValues

 | 

AttributesSelectedValues\_\_c

 | 

Attribute Selected Values

 | 

Text

 |
| 

SpecProduct2Id\_\_c

 | 

Product

 | 

SpecProduct2Id\_\_c

 | 

Product

 | 

Foreignkey Lookup ()

 |

[](https://help.salesforce.com/s?language=en_US)

## GroupCensusMember Field Mapping

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Field Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

Birthdate

 | 

Birthdate

 | 

Birthdate\_\_c

 | 

Birthdate

 | 

Date

 |
| 

GroupCensus

 | 

Group Census

 | 

CensusId\_\_c

 | 

Census

 | 

Parent/Child

 |
| 

Address

 | 

Address

 | 

Not Available

 | 

Not Available

 | 

Address

 |
| 

Contact

 | 

Contact

 | 

ContactId\_\_c

 | 

Contact

 | 

Foreignkey Lookup ()

 |
| 

Email

 | 

Email

 | 

Email\_\_c

 | 

Email

 | 

Email

 |
| 

FullTimeEquivalent

 | 

Full Time Equivalent

 | 

FTE\_\_c

 | 

FTE

 | 

Number (,)

 |
| 

FirstName

 | 

First Name

 | 

FirstName\_\_c

 | 

First Name

 | 

Text

 |
| 

LastName

 | 

Last Name

 | 

LastName\_\_c

 | 

Last Name

 | 

Text

 |
| 

Gender

 | 

Gender

 | 

Gender\_\_c

 | 

Gender

 | 

Dynamic Enum

 |
| 

GroupClass

 | 

Group Class

 | 

\-GroupClassId\_\_c

 | 

Group Class

 | 

Foreignkey Lookup ()

 |
| 

JoinDate

 | 

Join Date

 | 

HireDate\_\_c

 | 

Hire Date

 | 

Date

 |
| 

IsOptOutAllPlans

 | 

Is Opt-out All Plans

 | 

IsOptOut\_\_c

 | 

Opt-out

 | 

Boolean

 |
| 

IsPortalUser

 | 

Is Portal User

 | 

IsPortalUser\_\_c

 | 

Is Portal User

 | 

Boolean

 |
| 

SourceSystemIdentifier

 | 

Source System Identifier

 | 

MemberIdentifier\_\_c

 | 

Member Identifier

 | 

Text

 |
| 

MemberType

 | 

Member Type

 | 

MemberType\_\_c

 | 

Type

 | 

Dynamic Enum

 |
| 

DependentCount

 | 

Dependent Count

 | 

NumberOfDependents\_\_c

 | 

No. Dependents

 | 

Number (,)

 |
| 

AnnualEligibleSalary

 | 

Annual Eligible Salary

 | 

Not Available

 | 

Not Available

 | 

Currency

 |
| 

PrimaryMemberSource

 | 

Primary Member Source

 | 

PrimaryMemberIdentifier\_\_c

 | 

Primary Member Identifier

 | 

Text

 |
| 

PrimaryGroupCensusMember

 | 

Primary Group Census Member

 | 

RelatedCensusMemberId\_\_c

 | 

Primary Census Member

 | 

Foreignkey Lookup ()

 |
| 

OptOutPlanTypes

 | 

Opt-out Plan Types

 | 

Opt-out Types

 | 

OptOutPlanTypes

 | 

Dynamic Enum

 |
| 

Account

 | 

Account

 | 

Not Available

 | 

Not Available

 | 

Foreignkey Lookup ()

 |
| 

RelationshipToPrimaryMember

 | 

Relationship to Primary Member

 | 

Not Available

 | 

Not Available

 | 

Dynamic Enum

 |
| 

PrimaryMemberCategory

 | 

Primary Member Category

 | 

Not Available

 | 

Not Available

 | 

Dynamic Enum

 |
| 

PhoneNumber

 | 

Phone Number

 | 

Not Available

 | 

Not Available

 | 

Phone

 |
| 

SmokerStatus

 | 

Smoker Status

 | 

Not Available

 | 

Not Available

 | 

Dynamic Enum

 |
| 

Status

 | 

Status

 | 

Not Available

 | 

Not Available

 | 

Static Enum

 |
| 

MemberKey

 | 

Member Key

 | 

Not Available

 | 

Not Available

 | 

Text

 |

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

AttributesSelectedValues\_\_c

 | 

AttributesSelectedValues

 | 

AttributesSelectedValues\_\_c

 | 

Attribute Selected Values

 | 

Text

 |
| 

SpecProduct2Id\_\_c

 | 

Product

 | 

SpecProduct2Id\_\_c

 | 

Product

 | 

Foreignkey Lookup ()

 |

[](https://help.salesforce.com/s?language=en_US)

## GroupClass Field Mapping

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Field Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

Name

 | 

Name

 | 

Not Available

 | 

Not Available

 | 

Text

 |
| 

Code

 | 

Code

 | 

ClassCode\_\_c

 | 

Class Code

 | 

Text

 |
| 

Description

 | 

Description

 | 

Description\_\_c

 | 

Description

 | 

Text

 |
| 

EffectiveEndDate

 | 

Effective End Date

 | 

EffectiveEndDate\_\_c

 | 

Effective End Date

 | 

Date

 |
| 

EffectiveStartDate

 | 

Effective Start Date

 | 

EffectiveStartDate\_\_c

 | 

Effective Start Date

 | 

Date

 |
| 

Account

 | 

Account

 | 

GroupId\_\_c

 | 

Group

 | 

Parent/Child

 |
| 

ParentGroupClass

 | 

Parent Group Class

 | 

ParentGroupClassId\_\_c

 | 

Parent Group Class

 | 

Foreignkey Lookup ()

 |
| 

Category

 | 

Category

 | 

Type\_\_c

 | 

Type

 | 

Dynamic Enum

 |
| 

UsageType

 | 

UsageType

 | 

Not Available

 | 

Not Available

 | 

Static Enum

 |

[](https://help.salesforce.com/s?language=en_US)

## GroupClassContribution Field Mapping

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Field Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

Name

 | 

Name

 | 

GroupClassContributionName

 | 

Name

 | 

Text

 |
| 

Amount

 | 

Amount

 | 

ContributionAmount\_\_c

 | 

Contribution Amount

 | 

Currency

 |
| 

Percentage

 | 

Percentage

 | 

ContributionPercent\_\_c

 | 

Contribution Percent

 | 

Percent

 |
| 

Type

 | 

Type

 | 

ContributionType\_\_c

 | 

Contribution Type

 | 

Static Enum

 |
| 

EffectiveEndDate

 | 

Effective End Date

 | 

EffectiveEndDate\_\_c

 | 

Effective End Date

 | 

Date

 |
| 

EffectiveStartDate

 | 

Effective Start Date

 | 

EffectiveStartDate\_\_c

 | 

Effective Start Date

 | 

Date

 |
| 

GroupClass

 | 

GroupClass

 | 

GroupClassId\_\_c

 | 

Group Class

 | 

Parent/Child

 |
| 

MemberType

 | 

MemberType

 | 

MemberType\_\_c

 | 

Member Type

 | 

Static Enum

 |
| 

GroupBenefitProductCategory

 | 

Group Benefit Product Category

 | 

ProductCategory\_\_c

 | 

Product Category

 | 

Dynamic Enum

 |
| 

ContractGroupPlan

 | 

Contract Group Plan

 | 

Not Available

 | 

Not Available

 | 

Foreignkey Lookup ()

 |

[](https://help.salesforce.com/s?language=en_US)

## InsuranceContract Field Mapping

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Field Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

BusinessLicense

 | 

Business License

 | 

AgencyLicenseId\_\_c

 | 

Channel Partner License

 | 

Foreignkey Lookup ()

 |
| 

EnrollmentEndDate

 | 

Enrollment End Date

 | 

EnrollmentEndDate\_\_c

 | 

Enrollment End Date

 | 

Date

 |
| 

EnrollmentStartDate

 | 

Enrollment Start Date

 | 

EnrollmentStartDate\_\_c

 | 

Enrollment Start Date

 | 

Date

 |
| 

EnrollmentWaitingPeriod

 | 

Enrollment Waiting Period

 | 

EnrollmentWaitingPeriod\_\_c

 | 

Enrollment Waiting Period

 | 

Number (,)

 |
| 

Producer

 | 

Producer

 | 

ProducerId\_\_c

 | 

Producer

 | 

Foreignkey Lookup ()

 |
| 

BrokerageAgency

 | 

Brokerage Agency

 | 

AgencyBrokerageId\_\_c

 | 

Agency/Brokerage

 | 

Foreignkey Lookup ()

 |
| 

Underwriter

 | 

Underwriter

 | 

UnderwriterId\_\_c

 | 

Underwriter

 | 

Foreignkey Lookup ()

 |
| 

Enrollment Census

 | 

EnrollmentCensus

 | 

EnrollmentCensusId\_\_c

 | 

Enrollment Census

 | 

Foreignkey Lookup ()

 |
| 

Contract

 | 

Contract

 | 

Not Available

 | 

Not Available

 | 

Parent/Child

 |

[](https://help.salesforce.com/s?language=en_US)

## ContractGroupPlan Field Mapping

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Field Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

Name

 | 

Name

 | 

Name

 | 

Name

 | 

Text

 |
| 

Account

 | 

Account

 | 

AccountId\_\_c

 | 

Account

 | 

Foreignkey Lookup ()

 |
| 

Contract

 | 

Contract

 | 

ContractId\_\_c

 | 

Contract

 | 

Parent/Child

 |
| 

EligibilityCriteria

 | 

Eligibility Criteria

 | 

EligibilityCriteria\_\_c

 | 

Eligibility Criteria

 | 

Text

 |
| 

EnrollmentStartDate

 | 

Enrollment Start Date

 | 

EnrollmentStartDate\_\_c

 | 

Enrollment Start Date

 | 

Date

 |
| 

EnrollmentEndDate

 | 

Enrollment End Date

 | 

EnrollmentEndDate\_\_c

 | 

Enrollment End Date

 | 

Date

 |
| 

EnrollmentRatingType

 | 

Enrollment Rating Type

 | 

EnrollmentRatingType\_\_c

 | 

Enrollment Rating Type

 | 

Static Enum

 |
| 

EnrollmentWaitingPeriod

 | 

Enrollment Waiting Period

 | 

EnrollmentWaitingPeriod\_\_c

 | 

Enrollment Waiting Period

 | 

Number (,)

 |
| 

GroupClass

 | 

Group Class

 | 

GroupClassId\_\_c

 | 

Group Class

 | 

Foreignkey Lookup ()

 |
| 

OriginalContractPlan

 | 

Original Contract Plan

 | 

Not Available

 | 

Not Available

 | 

Foreignkey Lookup ()

 |
| 

ContractGroupParentPlan

 | 

Contract Group Parent Plan

 | 

ParentItemId\_\_c

 | 

Parent Item Id

 | 

Foreignkey Lookup ()

 |
| 

ProductNumber

 | 

Product Number

 | 

ProductNumber\_\_c

 | 

Product Number

 | 

Number (,)

 |
| 

QuoteLineItem

 | 

Quote Line Item

 | 

QuoteLineItemId\_\_c

 | 

Quote Line Item Id

 | 

Foreignkey Lookup ()

 |
| 

GroupNumber

 | 

Group Number

 | 

GroupNumber\_\_c

 | 

Group Number

 | 

Text

 |
| 

UnitPrice

 | 

Unit Price

 | 

UnitPrice\_\_c

 | 

Unit Price

 | 

Currency

 |
| 

EffectiveEndDate

 | 

Effective End Date

 | 

EffectiveEndDate\_\_c

 | 

Effective End Date

 | 

DateTime

 |
| 

EffectiveStartDate

 | 

Effective Start Date

 | 

EffectiveStartDate\_\_c

 | 

Effective Start Date

 | 

DateTime

 |
| 

Status

 | 

Status

 | 

LineStatus\_\_c

 | 

Status

 | 

Static Enum

 |
| 

PricingStructure

 | 

Pricing Structure

 | 

Not Available

 | 

Not Available

 | 

String+clob

 |
| 

UsageType

 | 

UsageType

 | 

Not Available

 | 

Not Available

 | 

Static Enum

 |

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

AttributesSelectedValues\_\_c

 | 

AttributesSelectedValues

 | 

AttributesSelectedValues\_\_c

 | 

Attribute Selected Values

 | 

Text

 |
| 

Attribute\_\_c

 | 

Attribute

 | 

Attribute\_\_c

 | 

Attribute

 | 

Text

 |
| 

AttributeData\_\_c

 | 

Attribute Data

 | 

AttributeData\_\_c

 | 

Attribute Data

 | 

Text

 |
| 

Product2Id\_c

 | 

Product

 | 

Product2Id\_c

 | 

Product

 | 

Foreignkey Lookup ()

 |
| 

ProductChildItem\_\_c

 | 

Product Child Item

 | 

ProductChildItem\_\_c

 | 

Product Child Item

 | 

Foreignkey Lookup ()

 |

[](https://help.salesforce.com/s?language=en_US)

## GroupCensusMemberPlan Field Mapping

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Field Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

Name

 | 

Name

 | 

GroupCensusMemberPlanName

 | 

Name

 | 

Text

 |
| 

ContractGroupPlan

 | 

Contract Group Plan

 | 

ContractLineId\_\_c

 | 

Plan

 | 

Foreignkey Lookup ()

 |
| 

GroupCensusMember

 | 

Group Census Member

 | 

GroupCensusMemberId\_\_c

 | 

Census Member

 | 

Foreignkey Lookup ()

 |

[](https://help.salesforce.com/s?language=en_US)

## QuoteLineItemGroupClass Field Mapping

| 
Group Benefits Standard Field Name

 | 

Group Benefits Standard Field Label

 | 

Vlocity Group Benefit Field Name

 | 

Vlocity Group Benefit Field Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

Name

 | 

Name

 | 

QuoteLineItemGroupClassName

 | 

Name

 | 

Text

 |
| 

GroupClass

 | 

Group Class

 | 

GroupClassId\_\_c

 | 

Group Class

 | 

Foreignkey Lookup ()

 |
| 

Quote

 | 

Quote

 | 

QuoteId\_\_c

 | 

Quote

 | 

Parent/Child

 |
| 

QuoteLineItem

 | 

Quote Line Item

 | 

QuoteLineItemId\_\_c

 | 

Quote Line Item

 | 

Foreignkey Lookup ()

 |

.

Did this article solve your issue?

Let us know so we can improve!

YesNo