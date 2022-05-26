---
description: How to add Metadata to your HOT compliant ERC-721
---

# Metadata Standard

Asset metadata on the HOT Property allows the Roofstock onChain marketplace to pull in and display asset data. As single-family residential properties have a variety of attributes that need to be displayed, the metadata provides a mechanism to display rich content pertaining to a HOT Property.

The tokenURI method in the ERC-721 contract should return an HPPT or IPFS URL that when queried will need to return a JSOB blob with the metadata for the Home Ownership Token.

