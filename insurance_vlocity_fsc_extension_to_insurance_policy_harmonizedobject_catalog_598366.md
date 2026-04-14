---
title: "Insurance Industries Extension to Insurance Policy Object Model Mapping"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_vlocity_fsc_extension_to_insurance_policy_harmonizedobject_catalog_598366.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Insurance Industries Extension to Insurance Policy Object Model Mapping

Insurance Industries Extension to Insurance Policy Object Model Mapping[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Insurance Industries Extension to Insurance Policy Object Model Mapping

Learn how fields in the Insurance Industries Extension object model correspond to fields in the Insurance Policy object model. Use these field mappings when you create scripts that move insurance policy data from one model to the other.

Get a head start on data migration using template scripts based on these mappings. Add custom fields to these scripts if necessary.

-   [](https://help.salesforce.com/s?language=en_US)[FSC Extension to FSC Core Insurance Policy Mapping Scripts](https://volt.my.salesforce.com/sfc/p/o0000000ikm8/a/3m000000nwxt/tq9k2miunezctdgj3hsekrwywxxpmil_gn69lbkucsg)
    
-   [FSC Extension to FSC Core Insurance Policy Mappings in CSV Format](https://volt.my.salesforce.com/sfc/p/o0000000ikm8/a/3m000000nwyg/k78hixc5zsbm0owfw1zipu5dkcbwpgpqfkmm3chyl.g)
    

[](https://help.salesforce.com/s?language=en_US)

## Harmonized Objects

| 
FSC Object

 | 

Vlocity FSC Extension Object

 |
| --- | --- |
| 

InsurancePolicy

 | 

InsurancePolicy

 |
| 

InsurancePolicyCoverage

 | 

InsurancePolicyCoverage

 |
| 

InsurancePolicyAsset

 | 

InsurancePolicyAsset

 |
| 

InsurancePolicyParticipant

 | 

InsurancePolicyParticipant

 |
| 

InsurancePolicyMemberAsset

 | 

InsurancePolicyMemberAsset

 |
| 

InsurancePolicyTransaction

 | 

InsurancePolicyTransaction\_c

 |
| 

InsurancePolicySurcharge

 | 

InsurancePolicyPricingAdjustment\_\_c

 |
| 

ProducerCommissions

 | 

none

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicy Field Mapping

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

GrossWrittenPremium

 | 

Gross Written Premium

 | 

TotalAmountForTerm\_\_c

 | 

Total Amount for Term

 | 

Currency(16, 2)

 |
| 

OriginalEffectiveDate

 | 

Original Effective Date

 | 

OriginalEffectiveDate\_\_c

 | 

Original Effective Date

 | 

Date/Time

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

OriginalPolicyId\_\_c

 | 

Original Policy

 | 

Lookup(Insurance Policy)

 |
| 

PaidToDate

 | 

Paid To Date

 | 

PaidToDate\_\_c

 | 

Policy Paid To Date

 | 

Date

 |
| 

PolicyTerm

 | 

Policy Term

 | 

PolicyTerm\_\_c

 | 

Policy Term

 | 

Picklist

 |
| 

PremiumCalculationMethod

 | 

Premium Calculation Method

 | 

PremiumCalculationMethod\_\_c

 | 

Premium Calculation Method

 | 

Picklist

 |
| 

PremiumPaymentType

 | 

Premium Payment Type

 | 

PremiumPaymentType\_\_c

 | 

Premium Payment Type

 | 

Picklist

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

StandardPremiumAmount

 | 

Premium Amount

 | 

PremiumAmount

 | 

Standard Premium

 | 

Currency(16, 2)

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

TermFeeAmount

 | 

Total Fee For Term

 | 

TotalFeeForTerm\_\_c

 | 

Total Fee for Term

 | 

Currency(16, 2)

 |
| 

TermPremiumAmount

 | 

Total Premium For Term

 | 

TotalPremiumForTerm\_c

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

Total Tax for Term

 | 

Currency(16, 2)

 |
| 

TotalSumInsured

 | 

Total Sum Insured

 | 

TotalSumInsured\_\_c

 |   | 

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

Currency(16, 2)

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

PremiumAmount

 | 

Premium Amount

 | 

Currency(16, 2)

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

ProratedPremiumAmount\_\_c

 | 

Prorated Premium Amount

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
| 

ProductCode\_\_c

 | 

ProductCode

 |   | 

Product Code

 | 

Formula (Text)

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicyAsset Field Mapping

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

AssetName

 | 

AssetName

 | 

AssetName\_\_c

 | 

Asset Name

 | 

Text(255)

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

PrimaryPolicyParticipantId

 | 

Primary Policy ParticipantId

 | 

PrimaryPolicyParticipantId\_\_c

 | 

Primary Policy ParticipantId

 | 

Lookup(Insurance Policy Participant)

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

Premium Amount

 | 

Currency(16, 2)

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

ProratedPremiumAmount\_\_c

 | 

Prorated Premium Amount

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
FSC Field Name

 | 

FSC Field Label

 | 

Asset Field Name

 | 

Asset Label

 | 

Data Type

 |
| --- | --- | --- | --- | --- |
| 

isPolicyholder

 | 

IsPolicyholder

 | 

IsPolicyholder\_\_c

 | 

Is Policyholder

 | 

Formula (Checkbox)

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

Premium Amount

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

Tax Amoun

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

ProratedPremiumAmount\_\_c

 | 

Prorated Premium Amount

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
| 

ProductCode\_\_c

 | 

ProductCode

 |   | 

Product Code

 | 

Formula (Text)

 |
| 

RecordTypeName\_\_c

 | 

RecordTypeName

 |   | 

Record Type Name

 | 

Formula (Text)

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicyMemberAsset Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

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

InsurancePolicyId

 | 

InsurancePolicyId\_\_c

 | 

Insurance Policy Id

 | 

Formula (Text)

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

AttributesSelectedValues

 | 

Long Text Area(131072)

 |

[](https://help.salesforce.com/s?language=en_US)

## InsurancePolicyTransaction Field Mapping

| 
FSC Field Name

 | 

FSC Field Label

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

InsurancePolicyId\_\_c

 | 

Insurance Policy Id

 | 

Master-Detail(Insurance Policy)

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

Text(255)

 |
| 

Total Transaction Amount

 | 

TotalTransactionAmount

 | 

TotalAmount\_\_c

 | 

Total Amount

 | 

Formula (Currency)

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
FSC Field Name

 | 

FSC Field Label

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

InsurancePolicyId\_\_c

 | 

Insurance Policy

 | 

MasterDetail

 |
| 

InsurancePolicyCoverageId

 | 

Insurance Policy Coverage

 | 

InsurancePolicyCoverageId\_\_c

 | 

Insurance Policy Coverage

 | 

Lookup

 |
| 

InsurancePolicyParticipantId

 | 

Insurance Policy Participant

 | 

InsurancePolicyParticipantId\_\_c

 | 

Insurance Policy Participant

 | 

Lookup

 |
| 

InsurancePolicyTransactionId

 | 

Insurance Policy Transaction

 | 

InsurancePolicyTransactionId\_\_c

 | 

Insurance Policy Transaction

 | 

Lookup

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