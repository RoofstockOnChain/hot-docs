---
description: How to add Metadata to your HOT compliant ERC-721
---

# HOT Metadata Standard

Asset metadata on the HOT Property allows the Roofstock onChain marketplace to pull in and display asset data. As single-family residential properties have a variety of attributes that need to be displayed, the metadata provides a mechanism to display rich content pertaining to a HOT Property.

The tokenURI method in the ERC-721 contract should return an HPPT or IPFS URL that when queried will need to return a JSOB blob with the metadata for the Home Ownership Token.

| Name          | Required | Description                                                                                             |
| ------------- | -------- | ------------------------------------------------------------------------------------------------------- |
| name          | True     | Name of the HOT (name of the collection and token id - e.g., Roofstock Genesis HOT #01)                 |
| description   | True     | Human readable description of the HOT. Markdown is supported.                                           |
| image         | True     | URL to the main image of the HOT (suggest png or jpeg). We recommend 350 x 350. URL can be HTTP or IPFS |
| address       | True     | Property Address (see details below)                                                                    |
| year\_built   | True     | Year the property was constructed                                                                       |
| beds          | True     | Number of Bedrooms (e.g., 4)                                                                            |
| baths         | True     | Number of Bathrooms (e.g., 2.5)                                                                         |
| sqft          | True     | Square Footage of the Property (e.g., 3,080)                                                            |
| lot\_size     | True     | Lot size of the Property in square feet (e.g., 12,000)                                                  |
| images        | True     | Property images                                                                                         |
| attributes    | True     | Attributes for the HOT that will show up with the listing (see details below)                           |
| external\_url | False    | Allows users to see more detailed data about the HOT including documents in the data room               |

### Address

| Name    | Required | Description                               |
| ------- | -------- | ----------------------------------------- |
| line1   | True     | Property Address1 (e.g., 123 Main Street) |
| line2   | False    | (Optional) 2nd Line of Property Address   |
| city    | True     | Property City                             |
| state   | True     | Property State                            |
| zip     | True     | Property Zipcode (5 or 9 digit)           |
| country | True     | Property Country                          |

### Attributes

Attributes are used to add additional details to the HOT property. They have a traditional key-value structure.

| Name        | Required | Description                                            |
| ----------- | -------- | ------------------------------------------------------ |
| trait\_type | True     | Used as a label to describe the value of the attribute |
| value       | True     | The value of the attribute                             |

### Roofstock onChain HOT metadata

The following is an example of a Roofstock onChain property's metadata. It includes some suggested attributes:

```
{
    "name": "Roofstock HOT #2",
    "description": "Roofstock Home Ownership Token #2 - 123 East Main St, SomeCity, IN 12121",
    "image": "https://image1.com",
    "address": {
        "line1": "123 East Main St",
        "line2": "",
        "city": "SomeCity",
        "state": "IN",
        "zip": "12121"
    },
    "year_built": "1900",
    "beds": "4",
    "baths": "2",
    "sqft": "1454",
    "lot_size": "6,844",
    "images" : [
        "https://image1.com",
        "https://image2.com",
        "https://image3.com"
    ]
    "attributes": [
        {
            "trait_type": "Market",
            "value": "Dallas, TX"
        },
        {
            "trait_type": "Property Type",
            "value": "Single Family Residential"
        },
        {
            "trait_type": "Property Style",
            "value": "contemporary"
        },
        {
            "trait_type": "Longitude",
            "value": "-25.31312"
        },
        {
            "trait_type": "Latitude",
            "value": "108.83731"
        },
        {
            "trait_type": "Video Walkthrough",
            "value": "https://video1.com"
        },
        {
            "trait_type": "Realtor Url",
            "value": "https://arealtor.com"
        },
        {
            "trait_type": "Redfin Url",
            "value": "https://redfin.com/123EastMainSt"
        },
        {
            "trait_type": "Zillow Url",
            "value": "https://zillow.com/123EastMainSt"
        },
        {
            "trait_type": "Entity Name",
            "value": "ThePropertyLLC"
        },
        {
            "trait_type": "Entity Type",
            "value": "LLC"
        },
        {
            "trait_type": "Entity Tax Id",
            "value": "00-0000000"
        },
        {
            "trait_type": "Entity State Jurisdiction",
            "value": "Wyoming"
        },
        {
            "trait_type": "Entity Country Jurisdiction",
            "value": "USA"
        },
    ],
}
```
