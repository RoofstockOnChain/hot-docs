# The HOT Standard: Modified ERC-721

The blockchain architecture for Home Ownership Tokens is a modified ERC-721 (Ethereum Request for Comments 721) smart contract, which is a non-fungible token standard.  &#x20;

From erc721.org: “ERC-721 is a free, open standard that describes how to build non-fungible or unique tokens on the Ethereum blockchain. While most tokens are fungible (every token is the same as every other token), ERC-721 tokens are all unique. ERC-721 defines a minimum interface a smart contract must implement to allow unique tokens to be managed, owned, and traded. It does not mandate a standard for token metadata or restrict adding supplemental functions.”&#x20;

The modified ERC-721 standard used by Roofstock is based on the OpenZeppelin implementation. The HOT ERC-721 has several important features that protect and improve the security of the tokens, the HOT owners and the overall ecosystem. Among other things, Home Ownership Tokens include a feature that prevents them from being transferred to parties that are not on Roofstock’s Identity Registry. It is not currently anticipated that HOTs will be transferrable outside of Roofstock’s ecosystem, considering the corporate and regulatory requirements to know the identity of the ultimate beneficial owner.&#x20;

Additionally, Home Ownership Tokens will be able to be involuntarily transferred away from the HOT owner if an owner is subsequently discovered to be a prohibited owner (e.g., if the person appears on a sanctions list), if a transfer is required because of death or incapacity of the HOT owner, or if other unanticipated legal situations arise, such as tax liens, bankruptcies, etc. The restrictions on Transfer also protect a HOT owner from losing their HOT as a result of phishing or other malicious attacks.&#x20;

The `transferFrom` function from OpenZepplin's [standard ERC-721 contract](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/57725120581e27ec469e1c7e497a4008aafff818/contracts/token/ERC721/ERC721.sol#L150) is:

{% embed url="https://gist.github.com/zmckinnon/f1c23cb4980642f2daf06097ada601f5" %}
OpenZeppelin's standard ERC721 transferFrom function
{% endembed %}

The HOT permissioned architecture modifies the `transferFrom` function in ERC-721 to restrict all transfers to the ROOFSTOCK\_TRANSFERER role:

{% embed url="https://gist.github.com/zmckinnon/b450dde6fe6d9105f659d456ff1d956a" %}
Roofstock Home Ownership Token's Modified ERC-721 transferFrom function
{% endembed %}

The result of this is that the ROOFSTOCK\_TRANSFERER role will be the only role that can transfer a token from one account to another.

![Roofstock's Permissioned ERC-721 Transfer Architecture ](<.gitbook/assets/Screen Shot 2022-05-13 at 3.49.25 PM.png>)
