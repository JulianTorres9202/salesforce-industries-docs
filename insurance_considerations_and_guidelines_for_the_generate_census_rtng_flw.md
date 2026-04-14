---
title: "Considerations and Guidelines for the Generate Census Rating Flow"
source: "https://help.salesforce.com/s/articleView?id=ind.insurance_considerations_and_guidelines_for_the_generate_census_rtng_flw.htm&language=en_US&type=5"
scraped: "2026-04-14"
filter: "ind.insurance_"
---# Considerations and Guidelines for the Generate Census Rating Flow

Considerations and Guidelines for the Generate Census Rating Flow[](https://help.salesforce.com/s?language=en_US)

You are here:

1.  [Salesforce Help](/s/?language=en_US)
2.  [Docs](/s/products?language=en_US)
3.  [Digital Insurance](https://help.salesforce.com/s/articleView?id=ind.insurance_admin_standard.htm&language=en_US&type=5)

# Considerations and Guidelines for the Generate Census Rating Flow

After you configure and customize the Generate Census Rating flow, keep this information in mind when using the flow in your org.

Always specify a Transform Omnistudio Data Mapper name in the **Data Mapper Bundle Name** field of each Rating Fact that's associated with your product. All fields selected in the **Get Group Census Member Family**, **Get Account**, and **Get Group Census** actions are collected in JSON and the JSON is passed as input to the Data Mapper that you specified in the rating fact product. Your Transform Data Mapper also produces a JSON file. If you want to use any attributes of the rating fact for rating, make sure the output JSON has keys that match the **Attribute Code** of that attribute.

For example, if your rating fact has an attribute for age with the Attribute Code `RF_Age`:

1.  Fetch the **Birthdate** field in the **Get Group Census Member Family** action.
2.  Add a formula to convert the **Birthdate** to **Age** in the Data Mapper. The Birthdate is input from the key `groupCensusMember:Birthdate`.
3.  Include the age computed from the formula with the key `RF_Age` in the Data Mapper’s output.

Here’s an example of the format of the JSON available for input to the Transform Data Mapper:

```html
{
"groupCensus": {
"Id": "0rfXXXXXXXXXXXX",
"Name": "Sample Group Census",
... (Any other fields of Group Census entity selected in Get Group Census action)
},
"groupCensusMember": {
"Id": "0r6XXXXXXXXXXXX",
"GroupClassId": "0rEXXXXXXXXXXXX",
"RelationshipToPrimaryMember": "Child",
"PrimaryGroupCensusMemberId": "0r6XXXXXXXXXXXX",
... (Any other fields of Group Census Member entity selected in Get Group Census Member Family action)
},
"account": {
"Id": "001XXXXXXXXXXXX",
"Name": "Sample Account",
... (Any other fields of Account entity selected in Get Account action)
}
```

Did this article solve your issue?

Let us know so we can improve!

YesNo