---
title: "Asset to Insurance Policy Object Model Mapping"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_asset_to_insurance_policy_object_model_mapping_599506.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Asset to Insurance Policy Object Model Mapping

Asset to Insurance Policy Object Model Mapping[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Asset to Insurance Policy Object Model Mapping

Learn how fields in the Asset object model correspond to fields in the Insurance Policy object model. Use these field mappings when you create scripts that move insurance policy data from one model to the other.

A CSV file containing all the mappings is available to download:

[FSC to Vlocity Asset Model Mappings](https://volt.my.salesforce.com/sfc/p/o0000000ikm8/a/3m000000nwyb/gad.0e2opqzdfoi4q8y.gqckw1gruwxjemif54uskzu)

[](https://help.salesforce.com/s?language=en_US)

## Harmonized Objects

| 
Insurance Policy Model Object

 | 

Asset Model Object

 |
| --- | --- |
| 

InsurancePolicy

 | 

Asset

 |
| 

InsurancePolicyCoverage

 | 

AssetCoverage\_\_c

 |
| 

InsurancePolicyAsset

 | 

AssetInsuredItem\_\_c

 |
| 

InsurancePolicyParticipant

 | 

AssetPartyRelationship\_\_c

 |
| 

InsurancePolicyMemberAsset

 | 

InsuredItemPartyRelationship\_\_c

 |
| 

InsurancePolicyTransaction

 | 

AssetTransaction\_\_c

 |
| 

InsurancePolicySurcharge

 | 

PolicyPricingAdjustment\_\_c

 |
| 

ProducerCommissions

 | 

none

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicy Field Mapping

| 
Insurance Policy Field Name

 | 

Insurance Policy Field Label

 | 

Asset Field Name

 | 

Asset Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

EffectiveDate

 | 

Effective Date

 | 

EffectiveDate\_\_c

 | 

Effective Date

 | 

Date/Time

 |
| 

ExpirationDate

 | 

Expiration Date

 | 

ExpirationDate\_\_c

 | 

Expiration Date

 | 

Date/Time

 |
| 

GrossWrittenPremium

 | 

Gross Written Premium

 | 

TotalPremiumForTerm\_\_c

 | 

Total Premium for Term

 | 

Currency(16, 2)

 |
| 

NameInsuredId

 | 

Name Insured

 | 

AccountId

 | 

Account

 | 

Master-Detail(Account)

 |
| 

OriginalExpirationDate

 | 

Original Expiration Date

 | 

OriginalExpirationDate\_\_c

 | 

Original Expiration Date

 | 

Date/Time

 |
| 

OriginalPolicyId

 | 

Original Policy Id

 | 

ExpiredPolicyAssetId\_\_c

 | 

ExpiredPolicyAssetId

 | 

Lookup(Insurance Policy)

 |
| 

ParentPolicyId

 | 

Parent Policy

 | 

ParentId

 | 

Parent Asset

 | 

Lookup(Insurance Policy)

 |
| 

PaymentDueDate

 | 

Payment Due Date

 | 

NextPaymentAmountDueDate\_\_c

 | 

Next Payment Amount Due Date

 | 

Date/Time

 |
| 

PolicyTerm

 | 

Policy Term

 | 

Term\_\_c

 | 

Term

 | 

Picklist

 |
| 

PolicyType

 | 

Policy Type

 | 

Type\_\_c

 | 

Type

 | 

Picklist

 |
| 

PremiumAmount

 | 

Premium Amount

 | 

StandardPremium\_\_c

 | 

Standard Premium

 | 

Currency(16, 2)

 |
| 

PremiumFrequency

 | 

Premium Frequency

 | 

BillingFrequency\_\_c

 | 

Billing Frequency

 | 

Picklist

 |
| 

PreviousPremium

 | 

Previous Premium

 | 

PreviousVersionId\_\_c.TotalAmount\_\_c

 |   | 

Currency(16, 2)

 |
| 

PreviousRenewalDate

 | 

Previous Renewal Date

 | 

PreviousVersionId\_\_c.EffectiveDate\_\_c

 |   | 

Date/Time

 |
| 

PriorPolicyId

 | 

Prior Policy

 | 

PreviousVersionId\_\_c

 | 

Previous Version Id

 | 

Lookup(Insurance Policy)

 |
| 

ProducerId

 | 

Producer

 | 

PrimaryProducerId\_\_c

 | 

Primary Producer

 | 

Lookup(Producer)

 |
| 

ProductId

 | 

Product

 | 

Product2Id

 | 

Product

 | 

Lookup(Product)

 |
| 

RenewalDate

 | 

Renewal Date

 | 

OriginalExpirationDate\_\_c

 | 

Original Expiration Date

 | 

Date/Time

 |
| 

ServicingOffice

 | 

Servicing Office

 | 

PrimaryProducerId\_\_c.Address

 |   | 

Address

 |
| 

SourceQuoteId

 | 

Source Quote

 | 

SourceQuoteId\_\_c

 | 

Source Quote

 | 

Lookup(Quote)

 |
| 

SourceSystemIdentifier

 | 

Source System Identifier

 | 

AssetReferenceId

 |   | 

Text(255) (Unique Case Insensitive)

 |
| 

StandardFeeAmount

 | 

Total Fee Amount

 | 

TotalFeeAmount\_\_c

 | 

Total Fee Amount

 | 

Roll-Up Summary (SUM Insurance Policy Pricing Adjustment)

 |
| 

StandardTaxAmount

 | 

Total Tax Amount

 | 

TotalTaxAmount\_\_c

 | 

Total Tax Amount

 | 

Roll-Up Summary (SUM Insurance Policy Pricing Adjustment)

 |
| 

Status

 | 

Status

 | 

Status

 | 

Status

 | 

Picklist

 |
| 

TermFeeAmount

 | 

Total Fee For Term

 | 

TotalFeeForTerm\_\_c

 | 

Total Fee For Term

 | 

Currency(16, 2)

 |
| 

TermPremium

 | 

Total Premium For Term

 | 

TotalPremiumForTerm\_\_c

 | 

Total Premium For Term

 | 

Currency(16, 2)

 |
| 

TermTaxAmount

 | 

Total Tax For Term

 | 

TotalTaxForTerm\_\_c

 | 

Total Tax For Term

 | 

Currency(16, 2)

 |
| 

TotalSumInsured

 | 

Total Sum Insured

 | 

TotalSumInsured\_\_c

 | 

Total Sum Insured

 | 

Currency(16, 2)

 |
| 

TotalStandardAmount

 | 

Total Standard Amount

 | 

TotalAmount\_\_c

 | 

Total Amount

 |   |

| 
Insurance Policy Field Name

 | 

Insurance Policy Field Label

 | 

Asset Field Name

 | 

Asset Label

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

ContractLineItemId\_\_c

 | 

ContractLineItemId

 | 

BenefitPlanId\_\_c

 | 

Plan

 | 

Lookup(Plan)

 |
| 

ProductCode\_\_c

 | 

ProductCode

 | 

ProductCode\_\_c

 | 

ProductCode

 | 

Formula (Text)

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicyCoverage Field Mapping

| 
Insurance Policy Field Name

 | 

Insurance Policy Field Label

 | 

Asset Field Name

 | 

Asset Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

CoverageName

 | 

Coverage Name

 | 

Name

 | 

Name

 | 

Text(255)

 |
| 

EffectiveDate

 | 

Effective Date

 | 

StartDate\_\_c

 | 

Start Date

 | 

Date/Time

 |
| 

ExpirationDate

 | 

Expiration Date

 | 

EndDate\_\_c

 | 

End Date

 | 

Date/Time

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

Lookup(Insurance Policy Asset)

 |
| 

InsurancePolicyId

 | 

Insurance Policy

 | 

PolicyAssetId\_\_c

 | 

Policy

 | 

Master-Detail(Insurance Policy)

 |
| 

InsurancePolicyParticipantId

 | 

Insurance Policy ParticipantId

 | 

InsuredPartyRelationshipId\_\_c

 | 

Insured Party

 | 

Lookup(Insurance Policy Participant)

 |
| 

PremiumAmount

 | 

Premium Amount

 | 

TotalProratedAmount\_\_c

 | 

Total Prorated Amount

 | 

Formula (Currency)

 |
| 

StandardFeeAmount

 | 

FeeAmount

 | 

FeeAmount\_\_c

 | 

Fee Amount

 | 

Currency(16, 2)

 |
| 

StandardPremiumAmount

 | 

Standard Premium Amount

 | 

PremiumAmount\_\_c

 | 

Premium

 |   |
| 

StandardTaxAmount

 | 

TaxAmount

 | 

TaxAmount\_\_c

 | 

Tax Amount

 | 

Currency(16, 2)

 |
| 

TermFeeAmount

 | 

Term Fee Amount

 | 

ProratedFeeAmount\_\_c

 | 

Prorated Fee Amount

 | 

Currency(16, 2)

 |
| 

TermPremiumAmount

 | 

Term Premium Amount

 | 

ProRatedPremiumAmount\_\_c

 | 

Prorated Premium

 | 

Currency(16, 2)

 |
| 

TermTaxAmount

 | 

Term Tax Amount

 | 

ProratedTaxAmount\_\_c

 | 

Prorated Tax Amount

 | 

Currency(16, 2)

 |
| 

TotalStandardAmount

 | 

Total Standard Amount

 | 

TotalAmount\_\_c

 | 

Total Amount

 | 

Formula (Currency)

 |

| 
Insurance Policy Field Name

 | 

Insurance Policy Label

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

AttributeSelectedValues\_\_c

 | 

AttributeSelectedValues

 | 

Long Text Area(131072)

 |
| 

Product2Id\_\_c

 | 

Product2Id

 | 

Product2Id\_\_c

 | 

Coverage Spec

 | 

Lookup(Product)

 |
| 

ProductChildItemId\_\_c

 | 

ProductChildItemId

 | 

ProductChildItemId\_\_c

 | 

Policy Coverage Spec

 | 

Lookup(Product Child Item)

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicyAsset Field Mapping

| 
Insurance Policy Field Name

 | 

Insurance Policy Field Label

 | 

Asset Field Name

 | 

Asset Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

AssetName

 | 

AssetName

 | 

Name

 | 

Name

 | 

Text(255)

 |
| 

InsurancePolicyId

 | 

InsurancePolicy

 | 

PolicyAssetId\_\_c

 | 

Name

 | 

Master-Detail(Insurance Policy)

 |
| 

PremiumAmount

 | 

Premium Amount

 | 

TotalProratedAmount\_\_c

 | 

Policy

 | 

Formula(Currency)

 |
| 

PrimaryPolicyParticipantId

 | 

Primary Policy ParticipantId

 | 

PrimaryInsuredPartyRelationshipId\_\_c

 | 

Held Product Relationship

 | 

Lookup(Insurance Policy Participant)

 |
| 

StandardFeeAmount

 | 

Fee Amount

 | 

FeeAmount\_\_c

 | 

Fee Amount

 | 

Currency(16,2)

 |
| 

StandardPremiumAmount

 | 

PremiumAmount

 | 

PremiumAmount\_\_c

 | 

Premium

 | 

Currency(16,2)

 |
| 

StandardTaxAmount

 | 

TaxAmount

 | 

TaxAmount\_\_c

 | 

Tax Amount

 | 

Currency(16,2)

 |
| 

TermFeeAmount

 | 

Term Fee Amount

 | 

ProratedFeeAmount\_\_c

 | 

Prorated Fee Amount

 | 

Currency(16,2)

 |
| 

TermPremiumAmount

 | 

Term Premium Amount

 | 

ProRatedPremiumAmount\_\_c

 | 

Prorated Premium

 | 

Currency(16,2)

 |
| 

TermTaxAmount

 | 

Term Tax Amount

 | 

ProratedTaxAmount\_\_c

 | 

Prorated Tax Amount

 | 

Currency(16,2)

 |
| 

TotalStandardAmount

 | 

Total Standard Amount

 | 

TotalAmount\_\_c

 | 

Total Amount

 | 

Lookup(User Record Access)

 |

| 
Insurance Policy Field Name

 | 

Insurance Policy Label

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

AttributeSelectedValues\_\_c

 | 

AttributeSelectedValues

 | 

Long Text Area(131072)

 |
| 

Product2Id\_\_c

 | 

Product2Id

 | 

Product2Id\_\_c

 | 

Insured Item Spec

 | 

Lookup(Product)

 |
| 

ProductChildItemId\_\_c

 | 

ProductChildItemId

 | 

ProductChildItemId\_\_c

 | 

Policy Insured Item Spec

 | 

Lookup(Product Child Item)

 |
| 

RecordTypeName\_\_c

 | 

RecordTypeName

 | 

RecordTypeName\_\_c

 | 

Product Record Type Name

 | 

Formula (Text)

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicyParticipant Field Mapping

| 
Insurance Policy Field Name

 | 

Insurance Policy Field Label

 | 

Asset Field Name

 | 

Asset Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

InsurancePolicyId

 | 

InsurancePolicy

 | 

AssetId\_\_c

 | 

Held Product

 | 

Master-Detail(Insurance Policy)

 |
| 

PrimaryParticipantAccountId

 | 

PrimaryParticipantAccount

 | 

PartyAccountId\_\_c

 | 

Account Id

 | 

Lookup(Account)

 |
| 

PrimaryParticipantContactId

 | 

PrimaryParticipantContact

 | 

PartyContactId\_\_c

 | 

Contact Id

 | 

Lookup(Contact)

 |
| 

RelationshipToInsured

 | 

RelationshipToInsured

 | 

RelationshipToInsured\_\_c

 | 

Relationship to Insured

 | 

Picklist

 |
| 

Role

 | 

Role

 | 

PartyRelationshipTypeId\_\_c

 | 

Relationship Type

 | 

Picklist (Multi-Select)

 |
| 

StandardFeeAmount

 | 

FeeAmount

 | 

FeeAmount\_\_c

 | 

Fee Amount

 | 

Currency(16, 2)

 |
| 

StandardPremiumAmount

 | 

PremiumAmount

 | 

PremiumAmount\_\_c

 | 

Premium

 | 

Currency(16, 2)

 |
| 

StandardTaxAmount.

 | 

TaxAmount

 | 

TaxAmount\_\_c

 | 

Tax Amount

 | 

Currency(16, 2)

 |
| 

TermFeeAmount

 | 

Term Fee Amount

 | 

ProratedFeeAmount\_\_c

 | 

Prorated Fee Amount

 | 

Currency(16, 2)

 |
| 

TermPremiumAmount.

 | 

Term Premium Amount

 | 

ProRatedPremiumAmount\_\_c

 | 

Prorated Premium

 | 

Currency(16, 2)

 |
| 

TermTaxAmount

 | 

Term Tax Amount

 | 

ProratedTaxAmount\_\_c

 | 

Prorated Tax Amount

 | 

Currency(16, 2)

 |
| 

TotalStandardAmount

 | 

Total Standard Amount

 | 

TotalAmount\_\_c

 | 

Total Amount

 | 

Formula (Currency)

 |
| 

TotalTermAmount

 | 

Total Term Amount

 | 

TotalProratedAmount\_\_c

 | 

Total Prorated Amount

 | 

Formula (Currency)

 |

| 
Insurance Policy Field Name

 | 

Insurance Policy Label

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

AttributesSelectedValues

 | 

Long Text Area(131072)

 |
| 

InsuredPartySpecId\_\_c

 | 

InsuredPartySpecId

 | 

InsuredPartySpecId\_\_c

 | 

Insured Party Spec Id

 | 

Lookup(Product)

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicyMemberAsset Field Mapping

| 
Insurance Policy Field Name

 | 

Insurance Policy Field Label

 | 

Asset Field Name

 | 

Asset Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

InsurancePolicyAssetId

 | 

InsurancePolicyAsset

 | 

InsuredItemId\_\_c

 | 

Insured Item

 | 

Master-Detail(Insurance Policy Asset)

 |
| 

InsurancePolicyId

 | 

InsurancePolicyId

 | 

AssetId

 | 

Asset Id

 | 

Formula (Text)

 |
| 

InsurancePolicyParticipantId

 | 

InsurancePolicyParticipant

 | 

InsuredPartyId\_\_c

 | 

Held Product Relationship

 | 

Lookup(Insurance Policy Participant)

 |
| 

Name

 | 

Name

 | 

Name

 | 

Insured Item Party Name

 | 

Auto Number

 |

| 
Insurance Policy Field Name

 | 

Insurance Policy Label

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

AttributesSelectedValues

 | 

Long Text Area(131072)

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicyTransaction Field Mapping

| 
Insurance Policy Field Name

 | 

Insurance Policy Field Label

 | 

Asset Field Name

 | 

Asset Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

Insurance Policy

 | 

InsurancePolicyId

 | 

AssetId\_\_c

 | 

Held Product

 | 

Master-Detail(Insurance Policy)

 |
| 

Parent Transaction

 | 

ParentTransactionId

 | 

TransactionId\_\_c

 | 

Transaction Id

 | 

Lookup(Insurance Policy Transaction)

 |
| 

Transaction Amount

 | 

TransactionAmount

 | 

Amount\_\_c

 | 

Amount

 | 

Currency(16, 2)

 |
| 

Transaction Effective Date

 | 

TransactionEffectiveDate

 | 

TransactionDate\_\_c

 | 

Transaction Date

 | 

Date/Time

 |
| 

Transaction Fee

 | 

TransactionFeeAmount

 | 

FeeAmount\_\_c

 | 

Fee Amount

 | 

Currency(16, 2)

 |
| 

Transaction Number

 | 

TransactionNumber

 | 

TransactionNumber\_\_c

 | 

Transaction Number

 | 

Text(255)

 |
| 

Transaction Posted Date

 | 

TransactionPostedDate

 | 

PostDate\_\_c

 | 

Post Date

 | 

Date/Time

 |
| 

Transaction Tax

 | 

TransactionTaxAmount

 | 

TaxAmount\_\_c

 | 

Tax Amount

 | 

Currency(16, 2)

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

Picklist

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicySurcharge Field Mapping

| 
Insurance Policy Field Name

 | 

Insurance Policy Field Label

 | 

Asset Field Name

 | 

Asset Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

SurchargeAmount

 | 

Surcharge Amount

 | 

Amount\_\_c

 | 

Amount

 | 

Currency

 |
| 

ApplicableObjectType

 | 

Applicable Object Type

 | 

ApplicableItemType\_\_c

 | 

Applicable Item Type

 | 

Picklist(static)

 |
| 

InsurancePolicyId

 | 

Insurance Policy

 | 

AssetId\_\_c

 | 

Asset

 | 

MasterDetail

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

InsurancePolicyCoverageId

 | 

Insurance Policy Coverage

 | 

AssetCoverageId\_\_c

 | 

Coverage

 | 

Lookup

 |
| 

InsurancePolicyParticipantId

 | 

Insurance Policy Participant

 | 

AssetPartyRelationshipId\_\_c

 | 

Party Relationship

 | 

Lookup

 |
| 

InsurancePolicyTransactionId

 | 

Insurance Policy Transaction

 | 

AssetTransactionId\_\_c

 | 

Transaction

 | 

Lookup

 |
| 

Name

 | 

Name

 | 

Name

 | 

Tax/Fee Name

 | 

Name (Text)

 |

| 
Insurance Policy Field Name

 | 

Insurance Policy Label

 | 

Vlocity Field Name

 | 

Vlocity Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

AdjustmentType\_\_c

 |   | 

AdjustmentType\_\_c

 | 

Adjustment Type

 | 

Text(255)

 |
| 

PriceListEntryId\_\_c

 |   | 

PriceListEntryId\_\_c

 | 

Tax/Fee Id

 | 

Lookup(Product Tax and Fee)

 |
| 

PriceListEntryName\_\_c

 |   | 

PriceListEntryName\_\_c

 | 

Tax/Fee Name

 | 

Formula (Text)

 |
| 

IsRefundable\_c

 |   | 

IsTaxAndFeeRefundable\_\_c

 | 

Refundable

 | 

Checkbox

 |

Did this article solve your issue?

Let us know so we can improve!

YesNo