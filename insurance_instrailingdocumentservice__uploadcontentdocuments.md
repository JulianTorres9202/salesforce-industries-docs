---
title: "InsTrailingDocumentService:uploadContentDocuments"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_instrailingdocumentservice__uploadcontentdocuments.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsTrailingDocumentService:uploadContentDocuments

InsTrailingDocumentService:uploadContentDocuments[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsTrailingDocumentService:uploadContentDocuments

Add this service as remote properties within File and Image inputs to upload documents that satisfy requirements set up as placeholders for specific objects.

Class: `InsTrailingDocumentService`

Method: `uploadContentDocuments`

This service is supported on the following objects:

-   Quote
    
-   Policy (asset)
    
-   Claim
    
-   Contract
    
-   Case
    

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  Takes the document(s) uploaded by the user.
    
2.  Reads the list of content Ids uploaded in the OmniScript. The OmniScript creates an input JSON that includes the filename and size of the uploaded document(s).
    
3.  Finds the placeholder record with the same `categoryName` the user entered in the OmniScript. If the service doesn't find a placeholder record, it creates one with that `categoryName` and creates a content document link with that placeholder record.
    
4.  Return the trailing document placeholder Ids and a list of content document link Ids created under the placeholder.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`objectId`

 | 

The Id of the object that the trailing documents will attach to.

 |
| 

`categoryName`

 | 

The name of the folder in the file hierarchy where this trailing file will be stored.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service gets an input JSON created by the OmniScript.

In this example, the input JSON includes the filename and file size. The name of the record array is the `vlcFileKey`, which pulls the name of the input object. The `vlcFileKey` \= `damageImages`, which is the name of the Input component in a sample OmniScript.

```
{
	"damageImages": [{
		"filename": "accidentphoto1.jpg",
		"size": 77337,
		"data": "753039b5-d626-4413-8ad3-b0a7b06855b0"
	}]
}
```

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns Ids content document links and the trailing document placeholder (requirements for the documents). You can use these Ids to locate these documents in Vlocity.

```

{
	"result": {
		"contentDocLinkIds": [
			"06Af4000004SBL1EAO"
		],
		"trailingDocPlaceholderId": "a51f4000000XocEAAS"
	},
	"error": "OK"
}      
```

[](https://help.salesforce.com/s?language=en_US)

## Examples

The service is typically used for policies, claims, and other flows when a user is likely to need to upload supporting documents to a trailing document placeholder Id. To see a working example of this service, download this item into your org:

-   [Property Claim - First Notice of Loss (FNOL)](https://c.na78.visual.force.com/apex/processlibraryscreen3?library=abqo0000000pasqgaw&processid=abs1n000000gpdhwa0&cardid=abpo00000008ozfga2&menuid=abto0000000gmawgas)
    

Did this article solve your issue?

Let us know so we can improve!

YesNo