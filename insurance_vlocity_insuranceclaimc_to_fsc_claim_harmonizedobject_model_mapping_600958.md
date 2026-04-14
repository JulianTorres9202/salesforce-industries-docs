---
title: "Vlocity InsuranceClaim__c to FSC Claim Harmonized Object Model Mapping"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_insuranceclaimc_to_fsc_claim_harmonizedobject_model_mapping_600958.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Vlocity InsuranceClaim__c to FSC Claim Harmonized Object Model Mapping

Vlocity InsuranceClaim\_\_c to FSC Claim Harmonized Object Model Mapping[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Vlocity InsuranceClaim\_\_c to FSC Claim Harmonized Object Model Mapping

Learn how fields in the Vlocity managed package object model correspond to fields in the Salesforce object model. Use these field mappings when you create scripts that move claims data from one model to the other.

[](https://help.salesforce.com/s?language=en_US)

## Harmonized Objects

| 
FSC Standard Object

 | 

Vlocity CustomObject

 |
| --- | --- |
| 

Claim

 | 

InsuranceClaim\_\_c

 |
| 

ClaimParticipant

 | 

ClaimPartyRelationship\_\_c

 |
| 

ClaimItem

 | 

InsuranceClaimInvolvedInjury\_\_c and InsuranceClaimInvolvedProperty\_\_c

 |
| 

ClaimCoverage

 | 

ClaimCoverage\_\_c

 |
| 

ClaimCoveragePaymentDetail

 | 

ClaimLineItem\_\_c

 |
| 

ClaimCoveragePaymentAdjustment

 | 

ClaimLineItem\_\_c

 |
| 

ClaimPaymentSummary

 | 

ClaimPayment\_\_c

 |
| 

ClaimCoverageReserveDetail

 | 

ClaimLineItem\_\_c

 |
| 

ClaimCoverageReserveAdjustment

 | 

InsClaimReserveTransaction\_\_c

 |

[](https://help.salesforce.com/s?language=en_US)

## Claim Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

AccountID

 | 

Account

 | 

PrimaryOwnerPartyId\_\_c

 | 

Claim Owner

 | 

Lookup(Account)

 |
| 

Status

 | 

Status

 | 

ClaimStatus\_\_c

 | 

Claim Status

 | 

Picklist

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

TextArea

 |
| 

ClaimReasonType

 | 

Claim Reason Type

 | 

LossCause\_\_c

 | 

Loss Cause

 | 

Picklist

 |
| 

LossDate

 | 

Loss Date

 | 

LossDate\_\_c

 | 

Loss Date

 | 

Date

 |
| 

ClaimType

 | 

Claim Type

 | 

LossType\_\_c

 | 

Loss Type

 | 

Picklist

 |
| 

PolicyNumberId

 | 

Policy Number

 | 

PrimaryPolicyAssetId\_\_c

 | 

Primary Policy

 | 

Lookup(InsurancePolicy)

 |
| 

InitiationDate

 | 

Initiation Date

 | 

ReportedDate\_\_c

 | 

Reported Date

 | 

Date

 |

| 
FSC Field Name

 | 

FSC Label

 | 

Vlocity Field Name

 | 

Vlocity Label

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

Long Text Area(131072)

 |
| 

SpecProduct2Id\_\_c

 |  | 

SpecProduct2Id\_\_c

 | 

Product

 |  |

[](https://help.salesforce.com/s?language=en_US)

## ClaimParticipant Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

ClaimId

 | 

Claim

 | 

ClaimId\_\_c

 | 

Claim

 | 

MasterDetail

 |
| 

IsInjured

 | 

Injured

 | 

HasInjuries\_\_c

 | 

Injuries

 | 

Checkbox

 |
| 

ParticipantContactId

 | 

Participant Contact

 | 

PartyId\_\_c

 | 

Party

 | 

Lookup

 |
| 

ParticipantAccountId

 | 

Participant Account

 |  |  | 

Lookup

 |
| 

Roles

 | 

Roles

 | 

PartyRelationshipType\_\_c

 | 

Relationship Type

 | 

Multi Picklist

 |
| 

InsurancePolicyParticipantId

 | 

Insurance Policy Participant

 |  |  | 

Lookup

 |

[](https://help.salesforce.com/s?language=en_US)

## ClaimItem Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

ClaimId

 | 

Claim

 | 

ClaimId\_\_c

 | 

Claim

 | 

MasterDetail

 |
| 

ClaimParticipantId

 | 

Claim Participant

 | 

ClaimantId\_\_c

 | 

Claimant Id

 | 

Lookup

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

TextArea

 |
| 

CurrentAddress

 | 

Current Address

 | 

CurrentLocation\_\_c

 | 

Current Location

 | 

Address

 |
| 

InsurancePolicyAssetId

 | 

Insurance Policy Asset

 | 

AssetInsuredItemId\_\_c

 | 

Insured Item

 | 

Lookup

 |
| 

Category

 | 

Category

 |  |  | 

Picklist

 |

| 
FSC Field Name

 | 

FSC Label

 | 

Vlocity Field Name

 | 

Vlocity Label

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

Long Text Area(131072)

 |
| 

SpecProduct2Id\_\_c

 |  | 

SpecProduct2Id\_\_c

 | 

Product

 |  |

[](https://help.salesforce.com/s?language=en_US)

## ClaimCoverage Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

Claim

 | 

Claim

 | 

ClaimId\_\_c

 | 

Claim Id

 | 

MasterDetail (Claim)

 |
| 

ClaimParticipant

 | 

Claim Participant

 | 

ClaimantId\_\_c

 | 

Claimant Id

 | 

Lookup (ClaimParticipant)

 |
| 

InsurancePolicyAsset

 | 

Insurance Policy Asset

 | 

AssetInsuredItemId\_\_c

 | 

Insured Item

 | 

Lookup (InsurancePolicyAsset)

 |
| 

ClaimItem

 | 

Claim Item

 | 

InvolvedItemId\_\_c, InvolvedInjuryId\_\_c

 | 

Involved Property Id

 | 

Lookup (ClaimItem)

 |
| 

InsurancePolicyCoverage

 | 

Insurance Policy Coverage

 | 

AssetCoverageId\_\_c

 | 

Policy Coverage Id

 | 

Lookup (InsurancePolicyCoverage)

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

TextArea

 |
| 

Name

 | 

Name

 | 

ClaimantName\_\_c

 | 

Claimant Name

 | 

Name (Text)

 |
| 

Status

 | 

Status

 | 

CoverageStatus\_\_c

 | 

Coverage Status

 | 

Picklist

 |
| 

InternalReserveMode

 | 

Reserve Mode

 | 

ReserveProcessingMode\_\_c

 | 

Reserve Processing Mode

 | 

Picklist (static)

 |
| 

LossReserveAmount

 | 

Loss Reserve

 | 

ReserveAmount\_\_c

 | 

Reserve Amount

 | 

Currency

 |
| 

ExpenseReserveAmount

 | 

Expense Reserve

 | 

ExpenseReserveAmount\_\_c

 | 

Expense Reserve Amount

 | 

Currency

 |

[](https://help.salesforce.com/s?language=en_US)

## ClaimCoveragePaymentDetail Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

ClaimCoverageId

 | 

Claim Coverage

 | 

ClaimCoverageId\_\_c

 | 

Claim Coverage Id

 | 

Master/Detail (Claim Coverage)

 |
| 

CoverageReserveDetailId

 | 

Claim Coverage Reserve Detail

 |  |  | 

Lookup (ClaimCoverageReserveDetail)

 |
| 

ClaimParticipantRecipient

 | 

Claim Participant Recipient

 | 

vlocity\_ins\_\_PayeeAccountId\_\_c, vlocity\_ins\_\_PayeeContactId\_\_c

 | 

Payee

 | 

Lookup (Claim Participant)

 |
| 

ClaimPayment

 | 

Claim Payment

 |  |  | 

Lookup (Claim Payment)

 |
| 

ClaimedAmount

 | 

Claimed Amount

 | 

ClaimAmount\_\_c

 | 

Claim Amount

 | 

Currency

 |
| 

AdjustedAmount

 | 

Adjusted Amount

 | 

AdjustedAmount\_\_c

 | 

Adjusted Amount

 | 

Picklist

 |
| 

BenefitName

 | 

Benefit Name

 | 

BenefitType\_\_c

 | 

Benefit Type

 | 

Text

 |
| 

UnitOfMeasurement

 | 

UnitOfMeasurement

 | 

 | 

 | 

Dynamic Picklist

 |
| 

UnitCount

 | 

Unit Count

 | 

Quantity\_\_c

 | 

Quantity

 | 

Number

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

Status

 | 

Status

 | 

Status\_\_c

 | 

Status

 | 

Dynamic Picklist

 |
| 

Type

 | 

Type

 | 

Type\_\_c

 | 

Type

 | 

Static Picklist

 |
| 

Name

 | 

Name

 |  |  | 

Name (Text)

 |

[](https://help.salesforce.com/s?language=en_US)

## ClaimPaymentDetailAdjustment Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

ClaimCoveragePayment

 | 

Claim Coverage Payment Detail Id

 | 

ParentItemId\_\_c

 | 

Claim Line ItemID

 | 

Master/Detail (ClaimCoveragePaymentDetail)

 |
| 

AdjustmentAmount

 | 

Adjustment Amount

 | 

AdjustedAmount\_\_c

 | 

Adjustment Amount

 | 

Currency

 |
| 

AdjustmentReason

 | 

Adjustment Reason

 | 

AdjustedReason\_\_c

 | 

Adjustment Reason

 | 

Text

 |
| 

Name

 | 

Name

 | 

 | 

 | 

Name (Text)

 |

[](https://help.salesforce.com/s?language=en_US)

## ClaimPaymentSummary Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

PaymentAmount

 | 

Payment Amount

 | 

Amount\_\_c

 | 

Amount

 | 

Currency

 |
| 

Claim

 | 

Claim

 | 

InsuranceClaimId\_\_c

 | 

Claim

 | 

Master/Detail (Claim)

 |
| 

PaymentStatus

 | 

Payment Status

 | 

Status\_\_c

 | 

Status

 | 

Dynamic Picklist

 |
| 

PaymentIdentifier

 | 

Payment Identifier

 | 

 | 

 | 

Text

 |
| 

PaymentDate

 | 

Payment Date

 | 

PaymentDate\_\_c

 | 

Payment Date

 | 

Date

 |
| 

Name

 | 

Name

 | 

 | 

 | 

Name (Text)

 |

[](https://help.salesforce.com/s?language=en_US)

## ClaimCoverageReserveDetail Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

ClaimCoverageId

 | 

Claim Coverage

 | 

ClaimCoverageId\_\_c

 | 

Claim Coverage Id

 | 

MasterDetail

 |
| 

BenefitName

 | 

Benefit Name

 | 

BenefitType

 | 

Benefit Type

 | 

Text

 |
| 

Name

 | 

Name

 | 

Name

 | 

Name

 | 

Name

 |
| 

ReserveAmount

 | 

Amount

 | 

ReserveAmount\_\_c

 | 

Reserve Amount

 | 

Currency

 |
| 

Status

 | 

Status

 | 

Status\_\_c

 | 

Status

 | 

Picklist

 |
| 

Type

 | 

Type

 | 

Type\_\_c

 |   | 

Picklist

 |

[](https://help.salesforce.com/s?language=en_US)

## ClaimCoverageReserveAdjustment Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

ClaimCoverageId

 | 

Claim Coverage

 | 

ClaimCoverageId\_\_c

 | 

Claim Coverage Id

 | 

MasterDetail

 |
| 

ClaimCoverageReserveDetail

 | 

Claim Coverage Reserve Detail

 |  |  | 

Lookup (ClaimCoverageReserveDetail)

 |
| 

AdjustmentAmount

 | 

Adjustment Amount

 | 

Amount\_\_c

 | 

Adjusted Amount

 | 

Currency

 |
| 

AdjustmentReason

 | 

Adjustment Reason

 | 

Name/Type\_\_c

 | 

Adjustment Reason

 | 

Text

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo