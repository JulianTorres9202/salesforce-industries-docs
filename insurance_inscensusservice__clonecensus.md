---
title: "InsCensusService:cloneCensus"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_inscensusservice__clonecensus.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# InsCensusService:cloneCensus

InsCensusService:cloneCensus[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# InsCensusService:cloneCensus

Use this service to clone a census and all the census members.

[](https://help.salesforce.com/s?language=en_US)

Class: `InsCensusService`

Method: `cloneCensus`

[](https://help.salesforce.com/s?language=en_US)

## How It Works

The service clones a given census, to one of four possible types, and returns a `clonedObjectId` for the clone.

[](https://help.salesforce.com/s?language=en_US)

## Remote Options

| 
Option

 | 

Description

 |
| --- | --- |
| 

`censusId`

 | 

Required.

Id of the census to deep clone.

 |
| 

`type`

 | 

Required.

New census type for the cloned census:

System, Quote, Enrollment, or Group.

 |

[](https://help.salesforce.com/s?language=en_US)

## Input JSON

This service does not take an input JSON.

[](https://help.salesforce.com/s?language=en_US)

## Output JSON

The service does not return an output JSON.

Did this article solve your issue?

Let us know so we can improve!

YesNo