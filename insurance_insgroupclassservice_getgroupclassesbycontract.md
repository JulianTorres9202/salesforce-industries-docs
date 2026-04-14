---
title: "InsGroupClassService:getGroupClassesByContract"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insgroupclassservice_getgroupclassesbycontract.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsGroupClassService:getGroupClassesByContract

InsGroupClassService:getGroupClassesByContract[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsGroupClassService:getGroupClassesByContract

​Use this service to get a list of eligible plans with the `contractId` that’s provided as input, and a list of eligible plans for the GroupclassId that’s provided as input.​

Class: `InsGroupClassService`

Method: `getGroupClassesByAccount`

## How It Works

1.  The service takes `contractId` and `groupClassId` as input.
    
    Note It is mandatory to provide `contractId`, but `groupClassId` is optional.
    
2.  It then validates the input data to verify that the provided `contractId` and `groupClassId` are valid.
    
3.  If only `contractId` is provided, the service retrieves all eligible plans with coverages and all valid group classes along with eligible plans for each valid group class.
    
4.  If `groupClassId` is also provided along with `contractId`, the service retrieves all the eligible plans for the provided `groupClassId`.
    

## Input Options

| Input | Description |
| --- | --- |
| contractId | Id of the contract group plan |
| groupClassId | Id of the group class |

## Input JSON

Here's the sample input JSON when only `contractId` is provided as input:

```json
{    

      "contractId":"001B000001UGEaRIAX"

}
```

## Output JSON

Here's the sample output JSON when only `contractId` is provided as input:

```json
{

"accountId": "800RN000000jc0JYAQ",
"eligiblePlans":

[
                             {
                                 "Id":"0rgRN000000030fYTT",
                                 "Name":"Vision Standard",
                                 "Type":"Vision",
                                 "childPlans":[
                                                            {
                                                                "value": "0rgDC000000000RYAQ",
                                                                "IsOptional": false,
                                                                "name": "MandatoryCoverage"
                                                            }
                                                      ]
                           },
                           {
                              "Id":"0rgRN000000030fYTS",
                              "Name":"Medical Standard",
                              "Type":"Medical",
                              "childPlans":[
                                                        {
                                                             "value": "0rgDC000000000RYAR",
                                                             "IsOptional": false,
                                                             "name": "MandatoryCoverage"
                                                        },
                                                        {
                                                             "value": "0rgDC000000000RYAT",
                                                             "IsOptional": true,
                                                             "name": "OptionalCoverage"
                                                        }
                                                  ]
                         }
 ],
"groupClasses":

[         

        {

                    "Id":"0rERN000000004Y2PN",
                    "Name":"Employees",
                     "Code":"Employees"

        },

         {


"Id":"0rERN000000004Y2AQ",
"Name":"Executives",
"Code":"Executives",
"eligiblePlans":

 [

{
      "Id":"0rgRN000000030fYAA",
      "Name":"Dental Premium",
      "Type":"Dental",
      "childPlans":

       [

{
     "value": "0rgDC000000000RYAR",
     "IsOptional": false,
     "name": "MandatoryCoverage"
},
{
     "value": "0rgDC000000000RYAT",
     "IsOptional": true,
     "name": "OptionalCoverage"
}

     ]
}

 ] //eligible plans node

  }

] // groupclasses node

}
```

## Input JSON

Here's the sample input JSON when both `contractId` and `groupClassId` are provided as input:

```json
{
    "contractId":"001B000001UGEaRIAX",
    "groupClassId":"0rERN000000004Y2AQ"
}
```

## Output JSON

Here's the sample output JSON when both `contractId` and `groupClassId`are provided as input:

```json
{
          "accountId": "800RN000000jc0JYAQ",
          "eligiblePlans":[
                                           {

"Id":"0rgRN000000030fYTT",
"Name":"Vision Standard",
"Type":"Vision",
"childPlans":

   [

{
"value": "0rgDC000000000RYAQ",
"IsOptional": false,
"name": "MandatoryCoverage"
}

   ]

 },
{


"Id":"0rgRN000000030fYTS",
"Name":"Medical Standard",
"Type":"Medical",
"childPlans":[


{
"value": "0rgDC000000000RYAR",
"IsOptional": false,
"name": "MandatoryCoverage"
},
{
"value": "0rgDC000000000RYAT",
"IsOptional": true,
"name": "OptionalCoverage"
}

 ]

 }

], // eligible plans node

       "groupClasses":[

{

"Id":"0rERN000000004Y2AQ",
"Name":"Executives",
"Code":"Executives",
"eligiblePlans":[


{
"Id":"0rgRN000000030fYAA",
"Name":"Dental Premium",
"Type":"Dental",
"childPlans":[
{
"value": "0rgDC000000000RYAR",
"IsOptional": false,
"name": "MandatoryCoverage"
},
{
"value": "0rgDC000000000RYAT",
"IsOptional": true,
"name": "OptionalCoverage"
}

                         ]

}

]

}
```

## Output JSON

Here's the sample output JSON with errors:

```json
{
   "errors" : [
                        {
                              "error":"Specify a valid ContractID",
                             "contractId":"001B000001UGEaRIAX"
                        }
   ]
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo