---
title: "InsCensusServiceStd:findAccounts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestdfindaccounts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:findAccounts

InsCensusServiceStd:findAccounts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:findAccounts

Search for existing person accounts by first name, last name, and email, or by a search key and group account.

Class: `InsCensusServiceStd`

Method: `findAccounts`

## How It Works

1.  If a service request payload contains an array of members with first name, last name, email address and a group account:
    
    1.  The service queries the Account entity and retrieves all person accounts with matching first name and/or last name and/or email address and account.
        
    2.  All matched person account Id, first name, last name and email are added to the 'accounts' node list in the response.
        
2.  If a service request payload contains a searchKey and a group account:
    
    1.  If the given search key contains one word, the service queries the Account entity and retrieves all person accounts with partial/exact matching names and account. Partial match is supported for names starting with the given search word.
        
    2.  If the given search key contains more than one word:
        
        1.  The service considers only the first two words (separated by a space) for Account search and ignores the rest of the words in the search key.
            
        2.  The service queries the Account entity and retrieves all person accounts with either (first name starts with first word and last name starts with second word of the search key) or (first name starts with second word and last name starts with first word of the search key) and account.
            
    3.  All matched person accounts Id, first name, last name and email are added to the 'accounts' node list in the response.
        

## Inputs

| Input | Description |
| --- | --- |
| `accountId` | 
Required.

GroupAccountId of person accounts.

 |
| `searchKey` | 

Required if not using members.

One or more words used to search person account with account name containing search key words.

 |
| `members` | 

Required if not using searchKey.

List of members to search accounts.

 |
| **member node** |   |
| `members.FirstName` | first name |
| `members.LastName` | last name |
| `members.PersonEmail` | email |

## Remote Options

| Option | Description |
| --- | --- |
| `accountId` | 
Required.

GroupAccountId of contacts

 |
| `searchKey` | 

Required if not using members.

One or more words used to search person accounts with contact name containing search key words.

 |
| `members` | 

Required if not using searchKey.

List of members to search person accounts.

 |
| **member node** |   |
| `FirstName` | first name |
| `LastName` | last name |
| `PersonEmail` | email |

## Input JSON

Here's the sample input JSON:

```json
{  
    "accounts":[
                    {
                        "Id":"001B000001QZObgIAH",
                        "FirstName":"Christine",
                        "LastName":"Boon",
                        "PersonEmail":"cBoon@test.com"
                    },
                    {
                        "Id":"001B000001QZObgIAJ",
                        "FirstName":"David",
                        "LastName":"Boon",
                        "PersonEmail":"cBoon@test.com"
                    }            
               ] }
```

## Output JSON

Here's the sample output JSON:

```json

{  
 
   "accounts":[
                    {
                        "FirstName":"Christine",
                        "LastName":"Boon",
                        "PersonEmail":"cBoon@test.com",
                        "Id":"001B000001QZObgIAJ"
                    },
                    {
                        "FirstName":"Christine",
                        "LastName":"Boon",
                        "Email":"cBoon@test.com",
                        "PersonEmail":"001B000001QZObgIAR"
                    },
                    ...
    ] }
```

Did this article solve your issue?

Let us know so we can improve!

YesNo