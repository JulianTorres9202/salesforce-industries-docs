---
title: "Property & Casualty Application Naming and Numbering Conventions Reference"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_p_and_c_app_naming_and_numbering_conventionsreference_509172.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Property & Casualty Application Naming and Numbering Conventions Reference

Property & Casualty Application Naming and Numbering Conventions Reference[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Property & Casualty Application Naming and Numbering Conventions Reference

We've created product models, rating procedures, and business processes for you in this Application.

Once you've got your own spin, you're free to extend what we've created, and create your own components and processes.

To make your extensions and additions work best with this Application, follow the naming and numbering conventions described below.

[](https://help.salesforce.com/s?language=en_US)

## Abbreviations

These abbreviations are used in some naming conventions to group items within a product line. Note that the Type field will be used on the product object for product lines.

Note

We use the **Type** field on the Product object for product lines.

| 
Product Line

 | 

Abbreviation

 |
| --- | --- |
| 

All product lines

 | 

`ins`

 |
| 

Auto

 | 

`auto`

 |
| 

Business Owners Policy

 | 

`bop`

 |
| 

Life and Annuities

 | 

`life`

 |
| 

Property

 | 

`prop`

 |
| 

Watercraft

 | 

`wi`

 |

| 
Application Area

 | 

Abbreviation

 |
| --- | --- |
| 

Console

 | 

`cnsl`

 |
| 

Portal

 | 

`port`

 |

[](https://help.salesforce.com/s?language=en_US)

## Attribute Categories

Attribute categories are grouped in sequence spaces to prevent clashing. If you create your own, you'll be more successful if you follow the patterns we've established.

Note

Many Insurance UIs display attribute categories and use the sequencing for UI ordering.

| 
Sequence Space

 | 

Product Line

 | 

Attribute Category

 | 

Sequence Number

 | 

Attribute Abbreviation

 | 

Comments

 |
| --- | --- | --- | --- | --- | --- |
| 

0-99

 |  |  |  |  | 

Reserved for your use

 |
| 

100-199

 | 

Watercraft

 |  |  |  |  |
|  |  | 

Marine vessel

 | 

110

 | 

mv

 |  |
|  |  | 

Marine operator

 | 

120

 | 

mop

 |  |
|  |  | 

Marine terms

 | 

130

 | 

mt

 |  |
| 

200-299

 | 

Auto

 |  |  |  |  |
| 

300-399

 | 

Property

 |  |  |  |  |
|  |  | 

Property location

 | 

310

 | 

pl

 |  |
|  |  | 

Property terms

 | 

320

 | 

pt

 |  |
|  |  | 

Property item

 | 

330

 | 

pi

 |  |
| 

400-499

 | 

Business Owners Policy

 |  |  |  |  |
| 

500-599

 | 

Life

 |  |  |  |  |
| 

600-699

 |  |  |  |  | 

Reserved for future product lines

 |
| 

700-799

 |  |  |  |  | 

Reserved for future product lines

 |
| 

1000-1100

 | 

Claims

 |  |  |  |  |

[](https://help.salesforce.com/s?language=en_US)

## Products

We've created product codes using camel case, no spaces, prefaced by the product line abbreviation listed earlier on this page.

If you create other products, set the following information for each product:

-   Line of Business = Property & Casualty (all products in this org)
    
-   Product Family
    
-   Type
    
-   Sub Type
    

| 
Line of Business

 | 

Product Family

 | 

Type

 | 

Sub Type

 |
| --- | --- | --- | --- |
| 

Property & Casualty

 | 

Personal Lines

 | 

Auto

 | 

Auto

 |
| 

Property & Casualty

 | 

Personal Lines

 | 

Auto

 | 

Multi Auto

 |
| 

Property & Casualty

 | 

Personal Lines

 | 

Property

 | 

Homeowners

 |
| 

Property & Casualty

 | 

Personal Lines

 | 

Property

 | 

Renters

 |
| 

Property & Casualty

 | 

Personal Lines

 | 

Watercraft

 | 

Watercraft

 |
| 

Property & Casualty

 | 

Personal Lines

 | 

Watercraft

 | 

Multi Watercraft

 |
| 

Property & Casualty

 | 

Commercial Lines

 | 

Small Business

 | 

Business Owners

 |
| 

Life, Annuities, & Disability

 | 

Individual

 | 

Life

 | 

Whole

 |
| 

Life, Annuities, & Disability

 | 

Individual

 | 

Life

 | 

Term

 |
| 

Life, Annuities, & Disability

 | 

Individual

 | 

Annuity

 | 

Fixed

 |
| 

Life, Annuities, & Disability

 | 

Individual

 | 

Annuity

 | 

Variable

 |
| 

Life, Annuities, & Disability

 | 

Individual

 | 

Annuity

 | 

Immediate

 |
| 

Life, Annuities, & Disability

 | 

Individual

 | 

Annuity

 | 

Deferred

 |
| 

Life, Annuities, & Disability

 | 

Individual

 | 

Disability

 | 

Long Term

 |
| 

Life, Annuities, & Disability

 | 

Individual

 | 

Disability

 | 

Short Term

 |
| 

Life, Annuities, & Disability

 | 

Group

 | 

Disability

 | 

Long Term

 |

[](https://help.salesforce.com/s?language=en_US)

## OmniScripts and Integration Procedures

Form all OmniScript and Integration Procedure names in camel case (camelCase).

Follow these guidelines when you set up OmniScripts and Integration Procedures:

-   **Type** field
    
    -   Set this field to the product line of this OmniScript or Integration Procedure
        
    -   Prefix the value of this field with `ins` for OmniScripts and Integration Procedures common to all product lines
        
    -   Create common groupings for OmniScripts and Integration Procedures used in similar areas
        
-   **Sub Type** field
    
    A short and descriptive word or phrase, which will be used as part of the naming convention for Omnistudio Data Mappers
    

| 
Product line

 | 

Type

 |
| --- | --- |
| 

Auto

 | 

Auto

 |
| 

Homeowners

 | 

Homeowners

 |
| 

Renters

 | 

Renters

 |
| 

Watercraft

 | 

Watercraft

 |
| 

All lines

 | 

ins<Type>

 |

[](https://help.salesforce.com/s?language=en_US)

## Data Mappers

Consistent naming conventions help you determine what product line a Data Mapper is used for and where it is used.

For Data Mappers used in OmniScripts and Integration Procedures, use the following conventions, without spaces:

<Product Line Abbreviation><Read/Trans/Post><Descriptor><OS/IP Subtype><OS/IP>

For example: wi\_ReadProducer\_QuoteOS

Where:

-   Product Line Abbreviation
    
    -   Use the product line abbreviation from the top of this page.
        
    -   For Data Mappers used across product lines, prefix the name with the full Type of the OmniScript or Integration Procedure.
        
-   Read/Trans/Post
    
    -   Read: Use for Data Mappers of type Extract
        
    -   Trans: Use for Data Mappers of type Transform
        
    -   Post: Use for Data Mappers of type Load
        
-   Descriptor
    
    A word or short phrase that gives a user a high-level understanding of how this Data Mapper is used.
    
-   OS/IP Subtype
    
    The Sub Type field of the OmniScript or Integration Procedure that uses this Data Mapper. In combination with the Product Line Abbreviation, this lets the user find where this Data Mapper is used.
    
-   OS/IP
    
    Either OS or IP, to tell the user whether this Data Mapper is used in an OmniScript or an Integration Procedure.
    

For Data Mappers used in Cards, use the following naming convention:

<Product Line Abbreviation><Read/Trans/Post><Descriptor>\_Card

Add the Card name in the Description field for the Data Mapper.

Where:

[](https://help.salesforce.com/s?language=en_US)

-   Product Line Abbreviation
    
    -   Use the product line abbreviation from the top of this page.
        
    -   For Data Mappers used across product lines, prefix the name with the full Type of the OmniScript or Integration Procedure.
        
-   Read/Trans/Post
    
    -   Read: Use for Data Mappers of type Extract
        
    -   Trans: Use for Data Mappers of type Transform
        
    -   Post: Use for Data Mappers of type Load
        
-   Descriptor
    
    A word or short phrase that gives a user a high-level understanding of how this Data Mapper is used.
    

[](https://help.salesforce.com/s?language=en_US)

## Calculation Procedures and Calculation Matrices

Create names of Calculation Procedure and Calculation Matrices in camel case. Begin each name with the Product Line Abbreviation from the list at the beginning of this page.

Did this article solve your issue?

Let us know so we can improve!

YesNo