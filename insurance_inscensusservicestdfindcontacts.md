---
title: "InsCensusServiceStd:findContacts"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservicestdfindcontacts.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusServiceStd:findContacts

InsCensusServiceStd:findContacts[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusServiceStd:findContacts

Search for existing contacts by first name, last name, and email, or by a search key and group account.

Class: `InsCensusServiceStd`

Method: `findContacts`

## How It Works

1.  If a service request payload contains an array of members with first name, last name, email address, and a group account:
    
    1.  The service queries the Contact entity and retrieves all contacts with matching first name and/or last name and/or email address and account.
        
    2.  All matched contacts Id, first name, last name and email are added to the 'contacts' node list in the response.
        
2.  If a service request payload contains a searchKey and a group account:
    
    1.  If the given search key contains one word, the service queries the Contact entity and retrieve all contacts with partial/exact matching names and account. Partial match is supported for names starting with the given search word.
        
    2.  If the given searchkey contains more than one word:
        
        1.  The service considers only the first two words (separated by a space) for the Contacts search and ignores the rest of the words in the search key.
            
        2.  The service queries the Contact entity and retrieves all contacts with either (first name starts with first word and last name starts with second word of the search key) or (first name starts with second word and last name starts with first word of the search key) and account.
            
    3.  All matched contacts Id, first name, last name and email are added to the 'contacts' node list in the response.
        

## Inputs

| Input | Description |
| --- | --- |
| `accountId` | 
Required

GroupAccountId of contacts.

 |
| `searchKey` | 

Required if not using members.

One or more words used to search contacts with contact name containing search key words.

 |
| `members` | 

Required if not using searchKey.

List of members to search for in contacts.

 |
| **member node** |
| `FirstName` | first name |
| `LastName` | last name |
| `Email` | email |

## Remote Options

| Option | Description |
| --- | --- |
| `accountId` | 
Required.

GroupAccountId of contacts.

 |
| `searchKey` | 

Required if not using members.

One or more words used to search contacts with contact name containing search key words.

 |
| `members` | 

Required if not using searchKey.

List of members to search for in contacts.

 |
| **member node** |
| `FirstName` | first name |
| `LastName` | last name |
| `Email` | email |

## Input JSON

Here's the sample input JSON:

```json
{  
    "contacts":[
                    {
                        "Id":"003B000000LEreFIAT",
                        "FirstName":"Christine",
                        "LastName":"Boon",
                        "Email":"cBoon@test.com"
                    },
                    {
                        "Id":"003B000000M07HDIAZ",
                        "FirstName":"David",
                        "LastName":"Boon",
                        "Email":"cBoon@test.com"
                    }            
               ] }
```

## Output JSON

Here's the sample output JSON:

```json
{  
 
   "contacts":[
                    {
                        "FirstName":"Christine",
                        "LastName":"Boon",
                        "Email":"cBoon@test.com",
                        "Id":"003B000000LEreFIAT"
                    },
                    {
                        "FirstName":"Christine",
                        "LastName":"Boon",
                        "Email":"cBoon@test.com",
                        "Id":"003B000000M07HDIAZ"
                    },
                    ...
    ] }
```

Did this article solve your issue?

Let us know so we can improve!

YesNo