---
title: "Required Omniscript Components"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_required_omniscript_components.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Required Omniscript Components

Required Omniscript Components[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Required Omniscript Components

Verify that the required components are in place in Salesforce to support the Request Insurance Proof service process. The Address Update Omniscript calls these Integration Procedures, Omnistudio Data Mappers, FlexCards, and Apex classes.

Integration Procedure Actions:

[](https://help.salesforce.com/s?language=en_US)

-   FSCInsRqstInsPrf\_FetchAssetsorParticipants
-   FSCInsRqstInsPrf\_FetchPolicies
-   FSCInsRqstInsPrf\_GetSelectedPolicyDetails
-   FSCInsSelfService\_SetServiceProcessAccountContext\_Procedure
-   FSCInsServiceProcess\_GetAccountDetails\_Procedure

FlexCards:

[](https://help.salesforce.com/s?language=en_US)

-   FSCInsRqstInsPrfAssetsSummary
-   FSCInsRqstInsPrfCallScript
-   FSCInsRqstInsPrfDisplayAssetsHeader
-   FSCInsRqstInsPrfDisplayAssetsInfo
-   FSCInsRqstInsPrfDisplayParticipantsHeader
-   FSCInsRqstInsPrfDisplayParticipantsInfo
-   FSCInsRqstInsPrfDisplayPolicyDetails
-   FSCInsRqstInsPrfParticipantsSummary
-   FSCInsServiceProcessDisplayNewCaseConfirmationIcon
-   FSCInsServiceProcessDisplayNewCaseConfirmationIcon
-   FSCInsServiceProcessShowAccountDetails

Data Transforms:

[](https://help.salesforce.com/s?language=en_US)

-   FSCInsGetAccountId
-   FSCInsRqstInsPrfGetAllPolicies
-   FSCInsRqstInsPrfGetPolicies
-   FSCInsRqstInsPrfGetPolicyAssets
-   FSCInsRqstInsPrfGetPolicyCoverages
-   FSCInsRqstInsPrfGetPolicyParticipants
-   FSCInsRqstInsPrfPdfMapper
-   FSCInsRqstInsPrfTransformPolicies
-   FSCInsRqstInsPrfTransformPolicyAssets
-   FSCInsRqstInsPrfTransformPolicyDates
-   FSCInsRqstInsPrfTransformPolicyDetails
-   FSCInsRqstInsPrfTransformPolicyParticipants
-   FSCInsServiceProcessExtractAccountDetails

Apex Classes:

[](https://help.salesforce.com/s?language=en_US)

-   FSCInsRqstinsPrfHelperFunction: Creates Case and Service Request by using Salesforce ConnectApi
-   FSCInsUtilityClass: Utility class used in apex class

Did this article solve your issue?

Let us know so we can improve!

YesNo