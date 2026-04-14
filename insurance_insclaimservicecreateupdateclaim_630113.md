---
title: "InsClaimService:createUpdateClaim"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insclaimservicecreateupdateclaim_630113.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsClaimService:createUpdateClaim

InsClaimService:createUpdateClaim[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsClaimService:createUpdateClaim

Use this service to create or update a claim.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsClaimService`

[](https://help.salesforce.com/s?language=en_US)

Method: `createUpdateClaim`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The Salesforce Claims product supports both the existing Vlocity object model (custom objects in managed package) and the new Salesforce object model (standard Salesforce objects). The Vlocity model supports the Asset → InsuranceClaim relationship between policies and claims. The Salesforce model supports the InsurancePolicy → Claim relationship between policies and claims.

1.  Gets a pre-transformed JSON called by the `inputKey`. Then the service checks the `policyId` element in the input JSON to determine if the service creates a Vlocity or a Salesforce FSC claim:
    
    [](https://help.salesforce.com/s?language=en_US)
    -   If `policyId` belongs to an Asset record, the service creates Vlocity claim objects - `InsuranceClaim__c`, `InsuranceClaimInvolvedInjury__c`, `InsuranceClaimInvolvedProperty__c` and `InsuranceClaimPartyRelationship__c`.
        
    -   If `policyId` belongs to an `InsurancePolicy` record, the service creates these Salesforce FSC claim objects: `Claim`, `ClaimItem`, and `ClaimParticipant`.
        
    -   If `policyId` element isn’t available in the input JSON or its value is blank, the remote option `isAssetInsuranceClaim` is checked. If its value is `true`, the service creates Vlocity claim objects, else it creates FSC claim objects. In case `policyId` has no value and `isAssetInsuranceClaim` isn’t set, the default value of `isAssetInsuranceClaim` is `false`.
        
2.  If no `claimId` is passed in, the service creates a claim object.
    
    If a `claimId` is passed in, the service updates the claim object.
    
3.  If the `generateClaimNumber` or `uniqueIdGeneratorObjectSetting` or both options are set, the service uses them to create a `claimNumber` (**Name** field).
    
    As a best practice, assign a unique claim number to every claim. Use remote options to meet this recommendation, and make sure any custom workflows generate unique claimNumber values. If a unique value isn't configured, the system sets claim numbers for all claims to the same value.
    
4.  Returns `claimId`, `policyHolderClaimantId` (or `policyholderClaimParticipantId` if it's an FSC claim), and the `involvedItems` node in the output JSON.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`inputKey`

 | 

Required.

Gets a list of pre-transformed JSON structures that contain information the service needs. Depending on the `policyId`, the `claimJson` uses either of the following claim object models:

-   Salesforce FSC Claim Object Model
    
-   Vlocity Claim Object Model
    

 |
| 

`claimId`

 | 

Optional.

If the `claimId` is passed in, the service updates the claim.

If the `claimId` isn’t passed in, the service creates a claim.

 |
| 

`generateClaimNumber`

 | 

Optional.

If `true`, the service uses the `UniqueIdGeneratorService` to generate a unique key and to set the `Name` field to that unique key.

 |
| 

`uniqueIdGeneratorObjectSetting`

 | 

Optional.

If `generateClaimNumber` is `true` and this parameter =`null`, the service finds the Vlocity UniqueId Generator setting with `Object Type` = `Claim`.

If the service finds multiple settings, the service returns an error.

If the service finds one setting, the service uses that setting.

If `generateClaimNumber` is `true` and this parameter doesn’t = `null`, the service finds Vlocity UniqueId Generator Setting with `Name` = < this parameter value > and `Object Type` = `Claim`. It then uses that setting to generate the unique key.

 |
| 

`isAssetInsuranceClaim`

 | 

Optional.

Determines if the service creates a Vlocity claim or a Salesforce FSC claim.

-   If the value is `true`, the service creates Vlocity claim.
    
-   If the value is `false`, the service creates a Salesforce FSC claim.
    

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON (Salesforce FSC Claim Object Model)

This model is applicable in either of the following two cases:

-   The `policyID` in claimJson belongs to an InsuranceClaim object.
    
-   The value of the `isAssetInsuranceClaim` remote option is `false`.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    The `isAssetInsuranceClaim` remote option is applied only when `policyId` isn't present in the input JSON, or when it has a blank value. Also, when `policyId` has no value and `isAssetInsuranceClaim` isn’t set, the default value of `isAssetInsuranceClaim` is `false`.
    

The service uses the `inputKey` to get a pre-transformed JSON to use as input. This service can also take the insured item spec from the product directly and create an insured party or property.

In this example, `inputKey` = `claimJson`.

| 
Input

 | 

Description

 |
| --- | --- |
| 

`inputKey` = `claimJson`

 |
| 

`claimJSON`

 | 

The input elements within the JSON structure:

-   `policyholderInsurancePolicyParticipantId`: The ID of the policyholder's insurance participant.
    
-   `policyholderClaimParticipantRole`: A list of the roles of the policyholder's claim participant. Insert a semicolon delimiter between each value.
    
    [](https://help.salesforce.com/s?language=en_US)Example: `"Insured;Claimant"`
    
-   lossDate: Required when claim is configured with time sensitive attribute class such as Rolling and Calendar Year. If no date provided, then Policy Terms with duration type Rolling and Calendar Year aren't created.
    

 |
| 

`claimPropertyItems` or `claimPartyItems`

 | 

The list of property and injury inputs. This input parameter is a part of `claimJSON`.

-   `insurancePolicyParticipantId`: The ID of the policy participant who's either injured or has suffered a property loss. If you provide this ID, the service uses the appropriate `ContactId` and `AccountId` from the `InsurancePolicyParticipant` record. You can leave out `contactId` and `accountId` if you provide `insurancePolicyParticipantId`.
    
-   `contactId`: The ID of the contact who's either injured or has suffered a property loss. Provide `contactId` if the claimant doesn't have a policy participant ID. If you provide this ID, the service uses the appropriate `AccountId` from the Contact record. You can leave out `accountId` if you provide `contactId`.
    
-   `accountId`: The ID of the Account. Provide `accountId` if the claimant doesn't have a Policy Participant ID and you don't provide `contactId`.
    
-   `claimParticipantRoles`: A list of the roles of the policyholder's claim participant. Insert a semicolon delimiter between each value.
    
    [](https://help.salesforce.com/s?language=en_US)Example: `"Insured;Claimant"`
    
-   `insuredItemId`: This input accepts the ID of an InsurancePolicyAsset record.
    

 |
| 

`additionalClaimParticipants`

 | 

[](https://help.salesforce.com/s?language=en_US)The list of additional claim participants. This input parameter is a part of `claimJSON`.

Specify at least one of the ID fields: `insurancePolicyParticipantId`, `contactId,` or `accountId`.

-   `insurancePolicyParticipantId`: The ID of an additional participant on this claim. If you provide this ID, the service uses the appropriate `ContactId` and `AccountId` from the `InsurancePolicyParticipant` record. You can leave out `contactId` and `accountId` if you provide `insurancePolicyParticipantId`.
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    `contactId`: The ID of the Contact who's an additional participant on this claim. If you provide this ID but not `insurancePolicyParticipantId`, the service uses the appropriate `AccountId` from the Contact record. You can leave out `accountId` if you provide `contactId`.
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    `accountId`: The ID of the Account.
    
-   [](https://help.salesforce.com/s?language=en_US)
    
    `claimParticipantRoles`: A list of the claim participant's roles. Insert a semicolon delimiter between each value.
    
    Example: `"Claimant;Payee;Witness"`
    

 |

Here's an example of the input JSON for a Salesforce FSC claim:

```
{ 
 "claimJson": {
  "claimAttributes": {
     "amountDeductible": "500.00"
  },
  "claimPropertyItems": { 
   "autoClaimInvolvedVehicle": [ 
     {
      "claimParticipantRoles": "First Party Claimant; Insured",          
      "insurancePolicyParticipantId": "0ao5w0000000Cl7AAE",          
      "contactId": null,          
      "accountId": null,
      "insuredItemId": "0YW5w0000000HLKGA2",          
      "additionalFields": {},          
      "productCode": "autoClaimInvolvedVehicle",           
      "avMake": "Jeep",           
      "avModel": "Wrangler",          
      "avLicNum": "49J9384",           
      "avLicState": "CA",          
      "avYear": "2019",           
      "avColor": "Red",          
      "claimInsuredProp": true,          
      "claimEstimate": null,          
      "claimPropertyLoc": null,          
      "claimSeverity": null,          
      "claimDamage": "Front End Damage",          
      "claimDamageLoc": null,          
      "claimDrivable": false
     },        
      {          
       "claimParticipantRoles": "Third Party Claimant",          
       "insurancePolicyParticipantId": null,          
       "contactId": "0ao5w0000000J47AX5",          
       "accountId": null,          
       "insuredItemId": null,          
       "additionalFields": {},          
       "productCode": "autoClaimInvolvedVehicle",
       "avMake": "Audi",          
       "avModel": "A5",          
       "avLicNum": "48H03949",          
       "avLicState": "WA",          
       "avYear": "2015",          
       "avColor": "Blue",          
       "claimInsuredProp": false,          
       "claimEstimate": null,          
       "claimPropertyLoc": null,           
       "claimSeverity": null,          
       "claimDamage": "Rear End Damage",          
       "claimDamageLoc": null,          
       "claimDrivable": false
      }      
     ]    
    },    
    "claimPartyItems": {      
    "claimInjuredPerson": [        
    {          
     "claimParticipantRoles": "Third Party Claimant",          
     "contactId": "0ao5w0000000J47AX5",          
     "accountId": null,          
     "insurancePolicyParticipantId": null,          
     "additionalFields": {},          
     "productCode": "claimParticipantPerson",          
     "injDescription": "Whiplash"        
    }      
   ],    
    "additionalClaimParticipants": [
     {
      "Id": null,
      "insurancePolicyParticipantId":  null,
      "contactId": null,
      "accountId": "0015g00000H480EAAR",
      "claimParticipantRoles": "Witness", 
      "additionalFields": {}
     }
    ]
   },
  "additionalFields": {},    
  "policyholderClaimParticipantRole": "Insured",    
  "policyholderInsurancePolicyParticipantId": "0ao5w0000000Cl7AAE",    
  "policyId": "0YT5w0000000ieyGAA",    
  "lossDate": "2021-03-29T16:00:00.000Z",    
  "productCode": "autoClaimProduct"  
 } 
} 
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's an example of an output JSON for a Salesforce FSC claim:

```
{  
 "CreateUpdateClaimRemoteAction": {    
  "involvedItems": [      
    {       
     "insuredItemId": "0YW5w0000000HLKGA2",     
     "claimItemId": "0dq5w0000008PrNAAU",    
     "accountId": "0035w000034fL4YAK",    
     "contactId": "0035w000039cfL2AAI",   
     "insurancePolicyParticipantId": "0ao5w0000000Cl7AAE",      
     "claimParticipantRoles": "First Party Claimant; Insured",   
     "claimParticipantId": "0aS5w00000007r3EAA"    
    },      
    {
     "insuredItemId": null,    
     "claimItemId": "0dq5w0000008PrNAAU",    
     "accountId": null,   
     "contactId": "0035w000039cfL2AAI",   
     "insurancePolicyParticipantId": "0ao5w0000000Cl7AAE",  
     "claimParticipantRoles": "Third Party Claimant", 
     "claimParticipantId": "0aS5w00000004K59dD"      
    }    
   ],
   "policyholderClaimParticipantId": "0ao5w0000000Cl7AAE",    
   "claimId": "0Zk5w0000000IOVCA2"  
  },
  "policyTermIds": [     
   "a6Q5w0000002x6oEAA", 
   "a6Q5w0000002x6pEAA", 
   "a6Q5w0000002x6qEAA", 
   "a6Q5w0000002x6rEAA", 
   "a6Q5w0000002x6sEAA", 
   "a6Q5w0000002x6tEAA"  
  ]
 }
```

[](https://help.salesforce.com/s?language=en_US)

## Input JSON (Vlocity Claim Object Model)

This model is applicable in either of the following two cases:

-   The `policyID` in claimJson belongs to an Asset object.
    
-   The value of the `isAssetInsuranceClaim` remote option is `true`.
    
    [](https://help.salesforce.com/s?language=en_US)Note
    
    The `isAssetInsuranceClaim` remote option is applied only when `policyId` isn't present in the input JSON or when it has a blank value. Also, when `policyId` has no value and `isAssetInsuranceClaim` isn't set, the default value of `isAssetInsuranceClaim` is `false`.
    

The service uses the `inputKey` to get a pre-transformed JSON to use as input. This service can also take the insured item spec from the product directly and create an insured party or property.

In this example, `inputKey` = `claimJson`.

| 
Input

 | 

Description

 |
| --- | --- |
| 

`inputKey` = `claimJson`.

 |
| 

`claimJSON`

 | 

The input elements within the JSON structure:

-   `policyHolderPartyId`: Party ID based on the ID of Party object (`Party__c`).
    
-   `policyHolderPartyName`: Party name based on the name of Party object (`Party__c`). It must be the name of an existing `Party__c` record.
    
-   `policyHolderPartyRelationshipTypeId`: Relationship type ID based on the ID of Vlocity Party Relationship Type object (`PartyRelationshipType__c`).
    
-   `policyHolderPartyRelationshipType`: Relationship type name based on the name of Vlocity Party Relationship Type object (`PartyRelationshipType__c)`. It must be the name of existing `PartyRelationshipType__c` record.
    

 |
| 

`claimPropertyItems` or `claimPartyItems`

 | 

The list of property and injury inputs. This input parameter is a part of claimJSON.

Property

-   `claimantPartyId`
    
-   `claimantPartyName`
    
-   `claimantPartyRelationshipTypeId`
    
-   `claimantPartyRelationshipTypeName`
    
-   `insuredItemId`
    

Injury

-   `partyId`
    
-   `partyName`
    
-   `claimPartyRelationshipTypeId`
    
-   `claimPartyRelationshipTypeName`
    

 |

For `claimantPartyRelationshipTypeID` and `claimantPartyRelationshipTypeName` you need only one of these two elements.

For `claimantPartyName` and `claimantPartyID` you need only one of these two elements.

You must have a package of one of each of these inputs that match.

If it's a new combination, it inserts a record. If it's not a new combo, it uses the existing record for the combo.

The output is a `claimantId` (not a `partyId`).

Here's the format of the input JSON for a Vlocity claim:

```
{
  "input": {
    "claimJson": {
      "claimAttributes": {
        "amountDeductible": <Decimal>
      },
      "claimPropertyItems": {
        "homeUnit": [
          {
            "Id": <Id>,
            "claimantPartyRelationshipTypeName": <String>,
            "claimantPartyRelationshipTypeId": <Id>,
            "claimantPartyName": <String>,
            "claimantPartyId": <Id>,
            "insuredItemId": <Id>,
            "additionalFields": {},
            "productCode": <String>,
            "productName": <String>,
            "productId": <Id>
          }
        ],
  		"claimClaimantPerson": [
    		"additionalFields": {
      		"Name": <String>
    		},
    		"productCode": <String>,
    		"persPhone": <String>,
    		"persLastName": <String>,
    		"persName": <String>,
    		"persFirstName": <String>,
    		"persEmail": <String>,
    		"claimInjury": <String>,
    		"claimPartyRelationshipTypeName": <String>,
			"claimPartyRelationshipTypeId": <Id>,
			"partyName": <String>
    		"partyId": <Id>
  		]
      },
      "additionalFields": {},
      "policyHolderPartyRelationshipType": <String>,
      "policyHolderPartyRelationshipTypeId": <Id>,
      "policyHolderPartyName": <String>,
      "policyHolderPartyId": <Id>,
      "policyId": <Id>,
      "policyNumber": <String>,
      "lossDate": <Date>,
      "productCode": "deluxeHomeowners",
      "productName": "Deluxe Homeowners",
      "productId": <Id>
    	}
	}
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

Here's the format of the output JSON for a Vlocity claim:

```
{  
   "output": {
    "claimId": <String>,
    "policyHolderClaimantId": <Id>,
    "involvedItems": [
      {
        "insuredItemId": <Id>,
        "claimantPartyAccountName": <String>,
        "claimantPartyContactName": <String>,
        "claimantPartyId": <Id>,
        "claimantId": <Id>,
        "involvedItemId": <Id>
      },
      {
        "heldProductRelationshipId": <Id>,
        "claimantPartyAccountName": <String>,
        "claimantPartyContactName": <String>,
        "claimantPartyId": <Id>,
        "claimantId": <Id>,
        "involvedInjuryId": <Id>
      }
    ]
  }
}
```

[](https://help.salesforce.com/s?language=en_US)

## Sample Interface (Vlocity Claim Object Model)

```
{
  "input": {
    "claimJson": {
      "claimPropertyItems": {
        "claimVehicle": [
          {
            "insuredItemId": null,
            "claimantPartyId":null,
            "claimantPartyName":null,
            "claimantPartyRelationshipTypeId":null,
            "claimantPartyRelationshipTypeName":null,
            "additionalFields": {},
            "productCode": "claimVehicle",
            "productName": "Damaged Vehicle",
            "productId": "01t3i0000001cWAAAY",
            "autoBodyType": null,
            "autoColor": null,
            "autoLicNum": null,
            "autoLicState": null,
            "autoMake": null,
            "autoModel": null,
            "autoVIN": null,
            "autoYear": null,
            "claimDamage": null,
            "claimDamageLoc": null,
            "claimDrivable": false,
            "claimImage": null,
            "claimInsuredProp": false,
            "claimEstimate": null,
            "claimPropertyLoc": null,
            "claimSeverity": null
          }
        ]
      },
      "claimPartyItems": {
        "claimWitness": [
          {
            "heldProductRelationshipId": null,
            "partyId": null,
            "partyName": null,
            "claimPartyRelationshipTypeId":null,
            "claimPartyRelationshipTypeName":null,
            "additionalFields": {},
            "productCode": "claimWitness",
            "productName": "Witness",
            "productId": "01t3i0000001cWCAAY",
            "claimRel": null,
            "claimStatement": null,
            "claimTestify": false,
            "persPhone": null,
            "persSalutation": null,
            "persAddress": null,
            "persBirthdate": null,
            "persEmail": null,
            "persFirstName": null,
            "persLastName": null,
            "persMiddleName": null,
            "persName": null
          }
        ],
        "claimInjuredPerson": [
          {
            "heldProductRelationshipId": null,
            "partyId": null,
            "partyName": null,
            "claimPartyRelationshipTypeId":null,
            "claimPartyRelationshipTypeName":null,
            "additionalFields": {},
            "productCode": "claimInjuredPerson",
            "productName": "Injured Person",
            "productId": "01t3i0000001cWEAAY",
            "claimCarrier": null,
            "claimInjury": null,
            "claimPhysician": null,
            "claimPolicyNumber": null,
            "claimRel": null,
            "claimStatement": null,
            "claimTreatLoc": null,
            "claimInsuredProp": false,
            "claimEstimate": null,
            "claimSeverity": null,
            "persAddress": null,
            "persBirthdate": null,
            "persEmail": null,
            "persFirstName": null,
            "persLastName": null,
            "persMiddleName": null,
            "persName": null,
            "persPhone": null,
            "persSalutation": null,
            "claimantPartyRelationshipTypeId":null
          }
        ],
        "claimDriver": [
          {
            "heldProductRelationshipId": null,
            "partyId": null,
            "partyName": null,
            "claimPartyRelationshipTypeId":null,
            "claimPartyRelationshipTypeName":null,
            "additionalFields": {},
            "productCode": "claimDriver",
            "productName": "Driver",
            "productId": "01t3i0000001cWBAAY",
            "persAddress": null,
            "Birthdate": null,
            "persEmail": null,
            "First Name": null,
            "persIDJuris": null,
            "perIDNumber": null,
            "persIDType": null,
            "LastName": null,
            "MiddleName": null,
            "NAME": null,
            "persPhone": null,
            "persSalutation": null,
            "claimCarrier": null,
            "claimInjury": null,
            "claimInsured": false,
            "claimPhysician": null,
            "claimPolicyNumber": null,
            "claimRel": null,
            "claimStatement": null,
            "claimTestify": false,
            "claimTreatLoc": null
          }
        ]
      },
      "additionalFields": {},
      "policyHolderPartyId": null,
      "policyHolderPartyName": null,
      "policyHolderPartyRelationshipTypeId": null,
      "policyHolderPartyRelationshipType": null,
      "policyId": null,
      "policyNumber": null,
      "lossDate": null,
      "productCode": "claimPerilAutoCollision",
      "productName": "Auto Collision",
      "productId": null
    }
  }
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo