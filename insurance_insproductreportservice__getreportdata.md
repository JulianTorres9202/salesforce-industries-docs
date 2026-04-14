---
title: "InsProductReportService:getReportData"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insproductreportservice__getreportdata.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProductReportService:getReportData

InsProductReportService:getReportData[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProductReportService:getReportData

Use this service to retrieve all product fields and attributes for a given set of IDs and field sets, including all child products and their attributes.

Class: `InsProductReportService`

Method: `getReportData`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

This service takes a product Id and converts it to its report data equivalent.

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Options

 | 

Description

 |
| --- | --- |
| 

`fieldsetName`

 | 

Required.

The field set name, including prefix, to include all the fields in the report data.

Leaving this blank will limit the product fields to Product Code, Name, and Description.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns an output JSON which contains the necessary details, and corresponding column header information, for the report.

```
{
   "rows":[
      {
         "values":{
            "ATTRIBUTE-15446":"Private Limit 5k/day",
            "ATTRIBUTE-15447":10,
            "ATTRIBUTE-15448":true,
            "ATTRIBUTE-15444":200000,
            "ATTRIBUTE-15445":5,
            "ins_tj_dev__TotalInsuredFormula__c":null,
            "ins_tj_dev__Term__c":null,
            "ins_tj_dev__PricingFormula__c":null,
            "ins_tj_dev__IsConfigurable__c":false,
            "ins_tj_dev__RecordTypeName__c":"Product",
            "ins_tj_dev__PricingSource__c":null,
            "ins_tj_dev__ImageId__c":null,
            "ins_tj_dev__Tier__c":null,
            "ins_tj_dev__IsRecommended__c":false,
            "ins_tj_dev__RateBandId__c":null,
            "ins_tj_dev__SubType__c":null,
            "ins_tj_dev__Type__c":null,
            "ins_tj_dev__MarketSegment__c":null,
            "ins_tj_dev__LineOfBusiness__c":null,
            "ProductCode":"HP107",
            "Family":null,
            "Description":null,
            "Name":"Health Plan v107",
            "Id":"01t4P000009ANHBQA4"
         },
         "headers":{
            "ATTRIBUTE-15448":"DC Dental C",
            "ATTRIBUTE-15447":"DC Dental B",
            "ATTRIBUTE-15446":"DC Dental A",
            "ATTRIBUTE-15445":"M200K Medical B",
            "ATTRIBUTE-15444":"M200K Medical A",
            "ins_tj_dev__TotalInsuredFormula__c":"Total Insured Formula",
            "ins_tj_dev__Term__c":"Term",
            "ins_tj_dev__PricingFormula__c":"Pricing Formula",
            "ins_tj_dev__IsConfigurable__c":"Configurable",
            "ins_tj_dev__RecordTypeName__c":"Record Type Name",
            "ins_tj_dev__PricingSource__c":"Pricing Source Mapping",
            "ins_tj_dev__ImageId__c":"Image",
            "ins_tj_dev__Tier__c":"Tier",
            "ins_tj_dev__IsRecommended__c":"Recommended",
            "ins_tj_dev__RateBandId__c":"Rate Band",
            "ins_tj_dev__SubType__c":"Sub Type",
            "ins_tj_dev__Type__c":"Type",
            "ins_tj_dev__MarketSegment__c":"Market Segment",
            "ins_tj_dev__LineOfBusiness__c":"Line of Business",
            "ProductCode":"Product Code",
            "Family":"Product Family",
            "Description":"Product Description",
            "Name":"Product Name",
            "Id":"Product ID"
         }
      },
      {
         "values":{
            "ATTRIBUTE-15442":"new Value",
            "ATTRIBUTE-15443":"Default Product Name",
            "ins_tj_dev__TotalInsuredFormula__c":null,
            "ins_tj_dev__Term__c":null,
            "ins_tj_dev__PricingFormula__c":null,
            "ins_tj_dev__IsConfigurable__c":false,
            "ins_tj_dev__RecordTypeName__c":"Product",
            "ins_tj_dev__PricingSource__c":null,
            "ins_tj_dev__ImageId__c":null,
            "ins_tj_dev__Tier__c":null,
            "ins_tj_dev__IsRecommended__c":false,
            "ins_tj_dev__RateBandId__c":null,
            "ins_tj_dev__SubType__c":null,
            "ins_tj_dev__Type__c":null,
            "ins_tj_dev__MarketSegment__c":null,
            "ins_tj_dev__LineOfBusiness__c":null,
            "ProductCode":"v107AA",
            "Family":null,
            "Description":null,
            "Name":"v107 All Attributes",
            "Id":"01t4P000009AMnuQAG"
         },
         "headers":{
            "ATTRIBUTE-15443":"COL_COVERAGE Product Name",
            "ATTRIBUTE-15442":"COL_COVERAGE Product Code",
            "ins_tj_dev__TotalInsuredFormula__c":"Total Insured Formula",
            "ins_tj_dev__Term__c":"Term",
            "ins_tj_dev__PricingFormula__c":"Pricing Formula",
            "ins_tj_dev__IsConfigurable__c":"Configurable",
            "ins_tj_dev__RecordTypeName__c":"Record Type Name",
            "ins_tj_dev__PricingSource__c":"Pricing Source Mapping",
            "ins_tj_dev__ImageId__c":"Image",
            "ins_tj_dev__Tier__c":"Tier",
            "ins_tj_dev__IsRecommended__c":"Recommended",
            "ins_tj_dev__RateBandId__c":"Rate Band",
            "ins_tj_dev__SubType__c":"Sub Type",
            "ins_tj_dev__Type__c":"Type",
            "ins_tj_dev__MarketSegment__c":"Market Segment",
            "ins_tj_dev__LineOfBusiness__c":"Line of Business",
            "ProductCode":"Product Code",
            "Family":"Product Family",
            "Description":"Product Description",
            "Name":"Product Name",
            "Id":"Product ID"
         }
      },
      {
         "values":{
            "SG_empOnlyCount":"",
            "SG_empSpouseCount":"",
            "SG_empChildCount":"",
            "SG_empFamilyCount":"",
            "SG_CM_MemberClass":null,
            "SG_CM_Age":"",
            "SG_CM_State":null,
            "SG_CM_Gender":null,
            "SG_CM_Smoker":false,
            "SG_CM_IsPrimary":true,
            "SG_CM_IsSpouse":false,
            "SG_mailOrderDrugsT1_INN":"$37.50 Copay",
            "SG_mailOrderDrugsT1_OON":"Not Covered",
            "SG_mailOrderDrugsT2_INN":"$87.50 Copay",
            "SG_mailOrderDrugsT2_OON":"Not Covered",
            "SG_mailOrderDrugsT3_INN":"$125 Copay",
            "SG_mailOrderDrugsT3_OON":"Not Covered",
            "SG_mailOrderDrugsT4_INN":"$187.50 Copay",
            "SG_mailOrderDrugsT4_OON":"Not Covered",
            "SG_mailOrderDrugsT5_INN":"$1,250 Copay",
            "SG_mailOrderDrugsT5_OON":"Not Covered",
            "SG_RetailDrugsT1_INN":"$15 Copay",
            "SG_RetailDrugsT1_OON":"Not Covered",
            "SG_RetailDrugsT2_INN":"$35 Copay",
            "SG_RetailDrugsT2_OON":"Not Covered",
            "SG_RetailDrugsT3_INN":"$50 Copay",
            "SG_RetailDrugsT3_OON":"Not Covered",
            "SG_RetailDrugsT4_INN":"$75 Copay After Ded",
            "SG_RetailDrugsT4_OON":"Not Covered",
            "SG_RetailDrugsT5_INN":"Not Covered",
            "SG_RetailDrugsT5_OON":"Not Covered",
            "SG_imaging_INN":"$125 Copay",
            "SG_imaging_OON":"Not Covered",
            "SG_specialist_INN":"$50 Copay",
            "SG_specialist_OON":"Not Covered",
            "SG_primaryCare_INN":"$25 Copay",
            "SG_primaryCare_OON":"Not Covered",
            "SG_annualDed_INN":"$500 Indiv | $1,000 Fam",
            "SG_annualDed_OON":"Not Covered",
            "SG_annualOOP_INN":"$1,500 Indiv | $3,000 Fam",
            "SG_annualOOP_OON":"Not Covered",
            "SG_coinsurance_INN":"20% After Ded",
            "SG_coinsurance_OON":"Not Covered",
            "SG_lifetimeMax_INN":"Unlimited",
            "SG_lifetimeMax_OON":"Unlimited",
            "SG_preventative_INN":"$0 Copay",
            "SG_preventative_OON":"$0 Copay",
            "SG_outpatientXray_INN":"$50 Copay",
            "SG_outpatientMental_INN":"20% Coins After Ded",
            "SG_outpatientRehab_INN":"20% Coins After Ded",
            "SG_outpatientSurg_INN":"$75 Copay",
            "SG_skilledNursing_INN":"20% Coins After Ded",
            "SG_outpatientXray_OON":"Not Covered",
            "SG_outpatientMental_OON":"30% Coins After Ded",
            "SG_outpatientRehab_OON":"Not Covered",
            "SG_outpatientSurg_OON":"Not Covered",
            "SG_skilledNursing_OON":"Not Covered",
            "SG_inPatientHosp_INN":"20% Coins After Ded",
            "SG_inPatientHosp_OON":"Not Covered",
            "SG_inpatientMental_INN":"20% Coins After Ded",
            "SG_inpatientMental_OON":"Not Covered",
            "SG_HSA _INN":"Yes",
            "SG_HSA _OON":"Yes",
            "SG_ambula_INN":"$175 Copay",
            "SG_ambula_OON":"$175 Copay",
            "SG_emergRoom_INN":"$250 Copay",
            "SG_emergRoom_OON":"$500 Copay",
            "SG_urgentCareFacility_INN":"$100 Copay",
            "SG_urgentCareFacility_OON":"Not Covered",
            "ins_tj_dev__TotalInsuredFormula__c":null,
            "ins_tj_dev__Term__c":null,
            "ins_tj_dev__PricingFormula__c":"GroupPremium",
            "ins_tj_dev__IsConfigurable__c":false,
            "ins_tj_dev__RecordTypeName__c":"Product",
            "ins_tj_dev__PricingSource__c":null,
            "ins_tj_dev__ImageId__c":null,
            "ins_tj_dev__Tier__c":null,
            "ins_tj_dev__IsRecommended__c":false,
            "ins_tj_dev__RateBandId__c":null,
            "ins_tj_dev__SubType__c":"PPO",
            "ins_tj_dev__Type__c":"Medical",
            "ins_tj_dev__MarketSegment__c":"Small Group",
            "ins_tj_dev__LineOfBusiness__c":"Group Health",
            "ProductCode":"SG-PPO-35",
            "Family":"Other",
            "Description":null,
            "Name":"PPO 35",
            "Id":"01t4P000009AtC8QAK"
         },
         "headers":{
            "SG_CM_IsSpouse":"SG-Census-RF IsSpouse",
            "SG_CM_IsPrimary":"SG-Census-RF IsPrimary",
            "SG_CM_Smoker":"SG-Census-RF Smoker",
            "SG_CM_Gender":"SG-Census-RF Gender",
            "SG_CM_State":"SG-Census-RF State",
            "SG_CM_Age":"SG-Census-RF Age",
            "SG_CM_MemberClass":"SG-Census-RF MemberClass",
            "SG_empFamilyCount":"SG-Census-RF Employee + Family Count",
            "SG_empChildCount":"SG-Census-RF Employee + Child Count",
            "SG_empSpouseCount":"SG-Census-RF Employee + Spouse Count",
            "SG_empOnlyCount":"SG-Census-RF Employee Only Count",
            "SG_RetailDrugsT5_OON":"SG_Prescript_drugs Retail Drugs–Tier 5",
            "SG_RetailDrugsT5_INN":"SG_Prescript_drugs Retail Drugs–Tier 5",
            "SG_RetailDrugsT4_OON":"SG_Prescript_drugs Retail Drugs–Tier 4",
            "SG_RetailDrugsT4_INN":"SG_Prescript_drugs Retail Drugs–Tier 4",
            "SG_RetailDrugsT3_OON":"SG_Prescript_drugs Retail Drugs–Tier 3",
            "SG_RetailDrugsT3_INN":"SG_Prescript_drugs Retail Drugs–Tier 3",
            "SG_RetailDrugsT2_OON":"SG_Prescript_drugs Retail Drugs–Tier 2",
            "SG_RetailDrugsT2_INN":"SG_Prescript_drugs Retail Drugs–Tier 2",
            "SG_RetailDrugsT1_OON":"SG_Prescript_drugs Retail Drugs–Tier 1",
            "SG_RetailDrugsT1_INN":"SG_Prescript_drugs Retail Drugs–Tier 1",
            "SG_mailOrderDrugsT5_OON":"SG_Prescript_drugs Mail Order Drugs–Tier 5 (90-Day Supply)",
            "SG_mailOrderDrugsT5_INN":"SG_Prescript_drugs Mail Order Drugs–Tier 5 (90-Day Supply)",
            "SG_mailOrderDrugsT4_OON":"SG_Prescript_drugs Mail Order Drugs–Tier 4 (90-Day Supply)",
            "SG_mailOrderDrugsT4_INN":"SG_Prescript_drugs Mail Order Drugs–Tier 4 (90-Day Supply)",
            "SG_mailOrderDrugsT3_OON":"SG_Prescript_drugs Mail Order Drugs–Tier 3 (90-Day Supply)",
            "SG_mailOrderDrugsT3_INN":"SG_Prescript_drugs Mail Order Drugs–Tier 3 (90-Day Supply)",
            "SG_mailOrderDrugsT2_OON":"SG_Prescript_drugs Mail Order Drugs–Tier 2 (90-Day Supply)",
            "SG_mailOrderDrugsT2_INN":"SG_Prescript_drugs Mail Order Drugs–Tier 2 (90-Day Supply)",
            "SG_mailOrderDrugsT1_OON":"SG_Prescript_drugs Mail Order Drugs–Tier 1 (90-Day Supply)",
            "SG_mailOrderDrugsT1_INN":"SG_Prescript_drugs Mail Order Drugs–Tier 1 (90-Day Supply)",
            "SG_imaging_OON":"SG_Xray_Diagnostic Imaging",
            "SG_imaging_INN":"SG_Xray_Diagnostic Imaging",
            "SG_specialist_OON":"SG_Specialist Specialist",
            "SG_specialist_INN":"SG_Specialist Specialist",
            "SG_primaryCare_OON":"SG_Pri_Care_Visit Primary Care Visit",
            "SG_primaryCare_INN":"SG_Pri_Care_Visit Primary Care Visit",
            "SG_preventative_OON":"SG_Med_Base Preventive Services",
            "SG_preventative_INN":"SG_Med_Base Preventive Services",
            "SG_lifetimeMax_OON":"SG_Med_Base Lifetime Maximum",
            "SG_lifetimeMax_INN":"SG_Med_Base Lifetime Maximum",
            "SG_coinsurance_OON":"SG_Med_Base Coinsurance",
            "SG_coinsurance_INN":"SG_Med_Base Coinsurance",
            "SG_annualOOP_OON":"SG_Med_Base Annual OOP Limit",
            "SG_annualOOP_INN":"SG_Med_Base Annual OOP Limit",
            "SG_annualDed_OON":"SG_Med_Base Annual Deductible",
            "SG_annualDed_INN":"SG_Med_Base Annual Deductible",
            "SG_skilledNursing_OON":"SG_Lab_Outpat_Prof Skilled Nursing Facility Care",
            "SG_skilledNursing_INN":"SG_Lab_Outpat_Prof Skilled Nursing Facility Care",
            "SG_outpatientSurg_OON":"SG_Lab_Outpat_Prof Outpatient Surgery",
            "SG_outpatientSurg_INN":"SG_Lab_Outpat_Prof Outpatient Surgery",
            "SG_outpatientRehab_OON":"SG_Lab_Outpat_Prof Outpatient Rehab Services",
            "SG_outpatientRehab_INN":"SG_Lab_Outpat_Prof Outpatient Rehab Services",
            "SG_outpatientMental_OON":"SG_Lab_Outpat_Prof Outpatient Mental Health",
            "SG_outpatientMental_INN":"SG_Lab_Outpat_Prof Outpatient Mental Health",
            "SG_outpatientXray_OON":"SG_Lab_Outpat_Prof Outpatient Lab/X-Ray",
            "SG_outpatientXray_INN":"SG_Lab_Outpat_Prof Outpatient Lab/X-Ray",
            "SG_inpatientMental_OON":"SG_Hosp_based_Serv In-Patient Mental Health",
            "SG_inpatientMental_INN":"SG_Hosp_based_Serv In-Patient Mental Health",
            "SG_inPatientHosp_OON":"SG_Hosp_based_Serv In-Patient Hospital Care",
            "SG_inPatientHosp_INN":"SG_Hosp_based_Serv In-Patient Hospital Care",
            "SG_HSA _OON":"SG_HSA Health Savings Account Eligible",
            "SG_HSA _INN":"SG_HSA Health Savings Account Eligible",
            "SG_urgentCareFacility_INN":"SG_Emerg_Serv Urgent Care Facility",
            "SG_emergRoom_OON":"SG_Emerg_Serv Emergency Room",
            "SG_urgentCareFacility_OON":"SG_Emerg_Serv Urgent Care Facility",
            "SG_emergRoom_INN":"SG_Emerg_Serv Emergency Room",
            "SG_ambula_OON":"SG_Emerg_Serv Ambulance",
            "SG_ambula_INN":"SG_Emerg_Serv Ambulance",
            "ins_tj_dev__TotalInsuredFormula__c":"Total Insured Formula",
            "ins_tj_dev__Term__c":"Term",
            "ins_tj_dev__PricingFormula__c":"Pricing Formula",
            "ins_tj_dev__IsConfigurable__c":"Configurable",
            "ins_tj_dev__RecordTypeName__c":"Record Type Name",
            "ins_tj_dev__PricingSource__c":"Pricing Source Mapping",
            "ins_tj_dev__ImageId__c":"Image",
            "ins_tj_dev__Tier__c":"Tier",
            "ins_tj_dev__IsRecommended__c":"Recommended",
            "ins_tj_dev__RateBandId__c":"Rate Band",
            "ins_tj_dev__SubType__c":"Sub Type",
            "ins_tj_dev__Type__c":"Type",
            "ins_tj_dev__MarketSegment__c":"Market Segment",
            "ins_tj_dev__LineOfBusiness__c":"Line of Business",
            "ProductCode":"Product Code",
            "Family":"Product Family",
            "Description":"Product Description",
            "Name":"Product Name",
            "Id":"Product ID"
         }
      }
   ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo