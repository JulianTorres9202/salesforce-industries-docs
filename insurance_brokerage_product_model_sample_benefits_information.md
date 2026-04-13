---
title: "Plan Benefits Sample Information"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_brokerage_product_model_sample_benefits_information.htm&language=en_US&type=5"
scraped: "2026-04-13"
filter: "ind.insurance_"
---# Plan Benefits Sample Information

Plan Benefits Sample Information[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Plan Benefits Sample Information

Use the plan benefits information to model the medical, dental, and vision coverage products under the Employee Benefits root product.

### Required Editions

<table class="slds-table slds-table_bordered slds-m-bottom_small edition" lwc-3eigj2skqo3=""><colgroup lwc-3eigj2skqo3=""><col style="width:100%" lwc-3eigj2skqo3=""></colgroup><tbody lwc-3eigj2skqo3=""><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: Lightning Expereince</td></tr><tr class="" lwc-3eigj2skqo3=""><td style="vertical-align:top;" class="slds-cell-wrap" lwc-3eigj2skqo3="">Available in: <strong class="uicontrol" lwc-3eigj2skqo3="">Professional</strong>, <strong class="uicontrol" lwc-3eigj2skqo3="">Enterprise</strong>, and<strong class="uicontrol" lwc-3eigj2skqo3=""> Unlimited</strong> Editions where Financial Service Cloud and Insurance Brokerage are enabled</td></tr></tbody></table>

## Medical Coverage Product

| Product Component group (sequence) | product classification | product classification Attributes | benefit product (sequence) | attribute definitions (datatype) (sequence) |
| --- | --- | --- | --- | --- |
| General Plan Information (1) | Annual Deductable | Deductible | Annual Deductible/Individual (1) | Deductible ($) (1) |
| Annual Deductible/Family (2) | Deductible ($) (1) |
| Annual Plan Max | Annual Maximum | Annual Plan Maximum (3) |   |
|   | Annual Maximum ($) (1) |
| Reasonable Customary Percentile | Percentile | Reasonable & Customary Percentile (4) |   |
|   | Percentile (Picklist) |
| Waiting Period | Penalty | Waiting Period (5) |   |
|   | Penalty (Picklist) (1) |
| Diagnostic and Preventitive Services (2) | Preventitive Services | Benefit Maximum | Preventitive Services (1) |   |
|   | Benefit Maximum (%) (1) |
| Basic Major Services | Benefit Maximum, Coinsurance | Basic Services (2) |   |
|   | Benefit Maximum (%) (1) |
|   | Coinsurance (%) (2) |
| Major Services (3) |   |
|   | Benefit Maximum (%) (1) |
|   | Coinsurance (%) (2) |
| Endodontic | Benefit Maximum | Endodontic Treatment (4) |   |
|   | Benefit Maximum (%) (1) |
| Periodontic | Benefit Maximum | Periodontic Treatment (5) |   |
|   | Benefit Maximum (%) (1) |
| Orthodontia Services (3) | Orthodontia | Benefit Maximum, Covered Members | Orthodontia Services (1) |   |
|   | Benefit Maximum (%) (1) |
|   | Covered Members (Picklist) (2) |
| Lifetime Plan Max | Annual Maximum | Lifetime Plan Maximum (2) |   |
|   | Annual Maximum ($) (1) |

## Dental Coverage Product

| Product Component group (Sequence) | product classification | product classification attributes | benefit product (sequence) | Attribute definitions (data type) (sequence) |
| --- | --- | --- | --- | --- |
| General Plan Information (1) | Exam and Materials | Copay, Benefit Frequency | Exam |   |
|   | Copay ($) (1) |
|   | Benefit Frequency (Picklist) (2) |
| Materials |   |
|   | Copay ($) (1) |
|   | Benefit Frequency (Picklist) (2) |
| Lenses Frames and Contacts | Benefit Frequency | Lenses |   |
|   | Benefit Frequency (Picklist) (1) |
| Frames |   |
|   | Benefit Frequency (Picklist) (1) |
| Contacts |   |
|   | Benefit Frequency (Picklist) (1) |
| Covered Services - Lenses (2) | Single Bi Tri Focal Lenses | Benefit Maximum, Reimbursed Upto | Single Vision Lens |   |
|   | Benefit Maximum (%) (1) |
|   | Reimbursed Upto ($) (2) |
| Bifocal |   |
|   | Benefit Maximum (%) (1) |
|   | Reimbursed Upto ($) (2) |
| Trifocal |   |
|   | Benefit Maximum (%) (1) |
|   | Reimbursed Upto ($) (2) |
| Covered Services - Contacts (3) | Effective | Reimbursed Upto, Copay Waiver, In-network limitations | Effective |   |
|   | Reimbursed Upto ($) (1) |
|   | Copay Waiver (Picklist) 2 |
|   | In-network Limitations (Picklist) (2) |
| Covered Services - Frames (4) | Frames | Reimbursed Upto, Copay Waiver, In-network limitations | Frames |   |
|   | Reimbursed Upto ($) (1) |
|   | Copay Waiver (2) |
|   | In-network limitations (Picklist) (2) |

## Vision Coverage Product

| Product Component group (Sequence) | product classification | product classification Attributes | benefit product (sequence) | Attribute definitions (Datatype) (Sequence) |
| --- | --- | --- | --- | --- |
| General Plan Information (1) | Annual Deductible | Deductible | Annual Deductible/ Individual (1) |   |
|   | Deductible ($) (1) |
| Annual Deductible/ Family (2) |   |
|   | Deductible ($) (1) |
| OOP Limit | OOP Max | Annual Out-of-Pocket Limit/Individual (3) |   |
|   | OOP Max ($) (1) |
| Annual Out-of-Pocket Limit/Family (4) |   |
|   | OOP Max ($) (1) |
| Office Visit PCP | Copay,Coinsurance,Deductible Waiver | Office Visit | PCP (5) |   |
|   | Copay ($) (1) |
|   | Coninsurance (%) (1) |
|   | Deductible Waiver (Picklist) 2 |
| Office Visit Spec Virt | Copay,Coinsurance,Deductible Waiver,Notes | Office Visit | Specialist (6) |   |
|   | Copay ($) (1) |
|   | Coninsurance (%) (1) |
|   | Deductible Waiver (Picklist) (2) |
|   | Notes (Text) (3) |
| Office Visit | Virtual (7) |   |
|   | Copay ($) (1) |
|   | Coninsurance (%) (1) |
|   | Deductible Waiver (Picklist) (2) |
|   | Notes (Text) (3) |
| Outpatient Services (2) | Preventive Care | Copay,Coinsurance,Deductible Waiver | Preventive Care (1) |   |
|   | Copay ($) (1) |
|   | Coninsurance (%) (1) |
|   | Deductible Waiver (Picklist) (2) |
| Inpatient Outpatient | Copay,Coinsurance | Inpatient Hospital (2) |   |
|   | Copay ($) (1) |
|   | Coninsurance (%) (1) |
| Outpatient Surgery (3) |   |
|   | Copay ($) (1) |
|   | Coninsurance (%) (1) |
| Emergency Room | Copay,Coinsurance,Emergency Room Copay Waived | Emergency Room (4) |   |
|   | Copay ($) (1) |
|   | Coninsurance (%) (1) |
|   | Emergency Room Copay Waived (Picklist) (2) |
| Urgent Care\_Imaging | Copay (with subsequent Coinsurance),Coinsurance | Urgent Care (5) |   |
|   | Copay (with subsequent Coinsurance) ($) (1) |
|   | Coinsurance (%) (2) |
| Lab + Imaging (6) |   |
|   | Copay (with subsequent Coinsurance) ($) (1) |
|   | Coinsurance (%) (2) |
| Complex Imaging (7) |   |
|   | Copay (with subsequent Coinsurance) ($) (1) |
|   | Coinsurance (%) (2) |
| Chiropractic Services (3) | Chiropractic Care | Copay,Coinsurance,Visit Limit,Currency Limit | Chiropractic Care (1) |   |
|   | Copay ($) (1) |
|   | Coinsurance (%) (2) |
|   | Visit Limit (Number) (3) |
|   | Currency Limit ($) (3) |
| Acupuncture | Visit Limit,Currency Limit | Acupuncture (2) |   |
|   | Visit Limit (Number) (1) |
|   | Currency Limit ($) (1) |
| Prescription Drugs (4) |   |   |   |   |
| Rx Deductible Individual | Not Applicable,Deductible | Rx Deductible | Individual (1) |   |
|   | Deductible ($) (1) |
|   | Not Applicable (Picklist) (1) |
| Rx Retail Generic | Copay,Copay Min,Copay Max,Coinsurance,Deductible Waiver,Notes | Rx Retail | Generic (2) |   |
|   | Copay ($) (1) |
|   | Copay Min ($) (1) |
|   | Copay Max ($) (2) |
|   | Coinsurance (%) (2) |
|   | Deductible Waiver (Picklist) (3) |
|   | Notes (Text) (3) |
| Rx Retail Preferred Generic | CopayCopay MaxCopay MinCoinsuranceDeductible WaiverNotes | Rx Retail | Preferred Generic (3) |   |
|   | Copay ($) (1) |
|   | Coinsurance (%) (1) |
|   | Deductible Waiver (Picklist) (2) |
|   | Notes (Text) (2) |
| Rx High Cost Gen Preferred | Copay,Copay Min,Copay Max,Coinsurance | Rx Retail | High-cost Generic (4) |   |
|   | Copay ($) (1) |
|   | Coinsurance ($) (1) |
|   | Copay Min ($) (2) |
|   | Copay Max (%) (3) |
| Rx Retail | Preferred Brand (5) |   |
|   | Copay ($) (1) |
|   | Copay Min ($) (1) |
|   | Copay Max ($) (2) |
|   | Coinsurance (%) (3) |
| Rx Retail Non-preferred Brand | Copay,Copay Min,Copay Max,Coinsurance,Deductible Waiver,Notes | Rx Retail | Non-preferred Brand (6) |   |
|   | Copay ($) (1) |
|   | Copay Min ($) (1) |
|   | Copay Max ($) (1) |
|   | Coinsurance (%) (1) |
|   | Deductible Waiver (Picklist) (2) |
|   | Notes (Text) (2) |
| Rx Mail-order | Retail Copay Multiplier,Retail Copay Multiplier with Coinsurance,Coinsurance,Notes | Rx Mail-order (7) |   |
|   | Retail Copay Multiplier (Picklist) (1) |
|   | Retail Copay Multiplier with Coinsurance (Picklist) (1) |
|   | Coinsurance (%) (2) |
|   | Notes (Text) (2) |

Did this article solve your issue?

Let us know so we can improve!

YesNo