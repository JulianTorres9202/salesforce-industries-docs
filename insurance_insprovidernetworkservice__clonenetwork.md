---
title: "InsProviderNetworkService:cloneNetwork"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_insprovidernetworkservice__clonenetwork.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsProviderNetworkService:cloneNetwork

InsProviderNetworkService:cloneNetwork[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsProviderNetworkService:cloneNetwork

Use this service in an OmniScript to clone a Provider Network.

This is helpful when you want to create a new Provider Network for a different region whose specifications are otherwise nearly identical to the specifications of an existing Provider Network.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsProviderNetworkService`

Method: `cloneNetwork`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

1.  The service takes the `providerNetworkId` of the Provider Network to be cloned.
    
2.  Creates a deep clone of the Provider Network, including all the network members and product relationships of the cloned network, and creates a new record ID for the clone.
    

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`providerNetworkId`

 | 

`%theIdYouAreLookingFor%`

The Id of the Provider Network the service will clone.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service doesn't take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service returns the cloned Provider Network Id in the output JSON.

```

{
	"clonedId": a5R6F000000TZGwUAO,
	“errorCode”: "INVOKE-200",
	"error": "OK"
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo