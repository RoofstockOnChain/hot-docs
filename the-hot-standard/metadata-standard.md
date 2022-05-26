---
description: How to add Metadata to your HOT compliant ERC-721
---

# Metadata Standard

Asset metadata on the HOT Property allows the Roofstock onChain marketplace to pull in and display asset data. As single-family residential properties have a variety of attributes that need to be displayed, the metadata provides a mechanism to display rich content pertaining to a HOT Property.

The tokenURI method in the ERC-721 contract should return an HPPT or IPFS URL that when queried will need to return a JSOB blob with the metadata for the Home Ownership Token.

|                        | Required |                                                                                                         |
| ---------------------- | -------- | ------------------------------------------------------------------------------------------------------- |
| image                  | True     | URL to the main image of the HOT (suggest png or jpeg). We recommend 350 x 350. URL can be HTTP or IPFS |
| external\_url          | True     | Allows users to see more detailed data about the HOT including documents in the data room               |
| description            | True     | Human readable description of the HOT. Markdown is supported.                                           |
| name                   | True     | Name of the HOT (name of the collection and token id - e.g., Roofstock Genesis HOT #01)                 |
| attributes             | True     | Attributes for the HOT that will show up with the listing (array of trait\_type, value)                 |
| address1               | True     | Property Address1 (e.g., 123 Main Street)                                                               |
| address2               | False    | (Optional) 2nd Line of Property Address                                                                 |
| city                   | True     | Property City                                                                                           |
| state                  | True     | Property State                                                                                          |
| zip                    | True     | Property Zip                                                                                            |
| market                 | True     | Core Based Statistical Area (CBSA) of the Property                                                      |
| images                 | True     | Property images                                                                                         |
| 3d\_walkthrough        | False    | 3D Walkthrough of the Property                                                                          |
| video\_walkthrough     | False    | Video walkthrough of the Property                                                                       |
| floor\_plan            | False    | Floor plan for the Property                                                                             |
| lat\_long              | False    | Latitude and Longitude for the Property                                                                 |
| property\_type         | True     | Property Type (e.g., single family residential, town home, condo)                                       |
| year\_built            | True     | Year Property was built (e.g., 1999)                                                                    |
| beds                   | True     | Number of Bedrooms (e.g., 4)                                                                            |
| baths                  | True     | Number of Bathrooms (e.g., 2.5)                                                                         |
| sqft                   | True     | Square Footage of the Property (e.g., 3,080)                                                            |
| lot\_size              | True     | Lot size of the Property in square feet (e.g., 12,000)                                                  |
| property\_style        | False    | Style of the Property (e.g., Contemporary)                                                              |
| community              | False    | Community where Property is located (e.g., Education Hill)                                              |
| realtor\_url           | False    | Realtor.com URL for Property                                                                            |
| redfin\_url            | False    | Redfin URL for Property                                                                                 |
| zillow\_url            | False    | Zillow URL for Property                                                                                 |
| entity\_name           | True     | Name of Entity where Property is Titled (e.g., name of the LLC)                                         |
| entity\_type           | True     | Type of Entity (e.g., LLC)                                                                              |
| tax\_id                | False    | EIN or Tax ID of the Entity                                                                             |
| state\_jurisdiction    | True     | State or Province where entity is registered                                                            |
| national\_jurisdiction | True     | Country where entity is registered                                                                      |
