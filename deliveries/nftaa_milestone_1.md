# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** [nftaa.md](https://github.com/w3f/Grants-Program/blob/master/applications/nftaa.md)
* **Milestone Number:** 1

**Context** (optional)

In this milestone, we are delivering the foundational component of the NFT as an Account (NFTAA) project — a custom Substrate pallet enabling NFTs to function as proxy tradable accounts.

**Deliverables**

Repository overview - Here are the three repositories related to our project:

1. NFTAA W3F Proposal Documents
   Repository containing all materials related to the W3F proposal for NFTAA.  
   [GitHub Link: polkadot-nftaa-proposal](https://github.com/decenzio/polkadot-nftaa-proposal)

2. Pallet Source Code  
   The core implementation of the NFTAA pallet.  
   [GitHub Link: nftaa](https://github.com/decenzio/nftaa)

3. Custom Polkadot-SDK Fork  
   A customized fork of the Polkadot SDK. Development is happening in the `dev` branch.  
   [GitHub Link: polkadot-sdk](https://github.com/decenzio/polkadot-sdk)


| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 0a. | License |[MIT NFTAA general repo](https://github.com/decenzio/polkadot-nftaa-proposal/blob/main/LICENSE), [MIT NFTAA pallet src repo](https://github.com/decenzio/nftaa/blob/main/LICENSE)| MIT | 
| 0b.  | Documentation |[How to run?](https://github.com/decenzio/polkadot-nftaa-proposal/blob/main/README.md#how-to-run), [NFTAA doc](https://github.com/decenzio/nftaa/blob/main/README.md)| Readmes for all major parts of repository + inline documentation in each version of pallet + official documentation | 
| 0c. | Testing and Testing Guide |[Testing guide in readme](https://github.com/decenzio/polkadot-nftaa-proposal/blob/main/README.md#testing), [Unit tests file](https://github.com/decenzio/nftaa/blob/main/src/tests.rs)| Testing guide mentioned in readme & core unit tests | 
| 0d. | Docker |[Docker file](https://github.com/decenzio/polkadot-nftaa-proposal/blob/main/Dockerfile), [Docker guid in this readme](https://github.com/decenzio/polkadot-nftaa-proposal/blob/main/README.md#docker)| Docker file provided to test the functionality of the solution | 
|      1. | nftaa_pallet                                 | Initial version of the nftaa_pallet | Containing the functionalities described in the following lines |
|     1a. | reimplement functionalities from pallet_nfts | [lib.rs](https://github.com/decenzio/nftaa/blob/main/src/lib.rs) | Integration with the Substrate nfts pallet (for now only selected functions) |
|     1b. | nftaa address                                | pub fn create, pub fn mint, pub fn transfer, fn generate_nfta_address in [lib.rs](https://github.com/decenzio/nftaa/blob/main/src/lib.rs) | NFTAA creation and ownership management, construct keyless address for given NFT, create NFTAA address as future input to act as proxy |
|     1c. | nftaa attributes                      | [lib.rs](https://github.com/decenzio/nftaa/blob/main/src/lib.rs) | Attribute management for NFTAA is inherited from the nfts pallet functionality and fully compatible., bind NFT and its new keyless address to one entity consists of filling in the attributes contained in the NFT(AA) item |
|     1d. | nftaa act as proxy                                 | pub fn proxy_call in [lib.rs](https://github.com/decenzio/nftaa/blob/main/src/lib.rs) | Implement the proxy functionality to allow NFTs to act as proxy accounts, the owner of NFTAA can do a call via it; for this, we use pallet_utility special function as_derivate. We ensure that when an NFTAA is listed for sale, assets owned by the NFTAA cannot be withdrawn, effectively preventing fraudulent transfers. Therefore, if the NFTAA is listed, proxy calls are not possible. |
|     1e. | find owned assets                             | The default blockchain explorer can be used for this purpose | During the implementation, we realized that this is not possible in a pallet environment because the ownership of assets by the NFTAA entity is written onchain like any other ownership relationship we know from current accounts. However, the address of our NFTAA is fully compatible with existing blockchain explorer. |
|     1f. | find NFTAAs for account and owner              | It is possible to query storage to Find NFTs for an address using Polkadot.js API | Function to find owner of given NFTAA |

**Additional Information**

Every aspect of the project outlined in the proposal was implemented as specified. However, an exception exists in point 1e, where we had to deviate slightly from the intention, but the resulting solution fulfils the same purpose. The functions referenced in point 1a are those explicitly mentioned in [our proposal and the Milestone 1 section](https://github.com/w3f/Grants-Program/blob/master/applications/nftaa.md#milestone-1--basic-functionality); they are not arbitrarily chosen.
