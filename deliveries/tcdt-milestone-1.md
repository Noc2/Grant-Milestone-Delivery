# Milestone Delivery :mailbox:


**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** tcdt
* **Milestone Number:** 1

**Context** (optional)
This milestone delivers the initial functionality of the proposed blockchain DNS architecture in the form of two pallets, each used for different parts of the architecture.

**Deliverables**
> Please provide a list of all deliverables of the milestone extracted from the initial application and a link to the deliverable itself. Ideally all links inside the below table should include a commit hash, which will be used for testing. If you don't provide a commit hash, we will work off the default branch of your repository. Thus, if you plan on continuing work after delivery, we suggest you create a separate branch for either the delivery or your continuing work. 
> 
> If there is anything particular about any of the deliverables we or a future reader should know, use the respective `Notes` column.

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 0a. | License | Apache 2.0 | | 
| 0b.  | Documentation | [Link](https://github.com/tcdt-lab/bcdns/blob/master/polkadot-sdk-solochain-template/pallets/rootdns/src/lib.rs), [Link](https://github.com/tcdt-lab/bcdns/blob/master/polkadot-sdk-solochain-template/pallets/tld/src/lib.rs) | The documentation is provided at the beginning of each pallet along with inline comments throughout. | 
| 0c.  | Testing and Testing Guide | [Tests](https://github.com/tcdt-lab/bcdns/blob/master/polkadot-sdk-solochain-template/pallets/rootdns/src/tests.rs), [Tests](https://github.com/tcdt-lab/bcdns/blob/master/polkadot-sdk-solochain-template/pallets/tld/src/tests.rs)  | The pallets can also be tested by running the node and interacting with them through the [polkadot explorer](https://polkadot.js.org/apps/#/explorer) | 
| 0d.  | Docker  | [Link](https://github.com/tcdt-lab/bcdns/blob/master/polkadot-sdk-solochain-template/Dockerfile) | | 
| 1.  | pallet-root-dns | [Link](https://github.com/tcdt-lab/bcdns/blob/master/polkadot-sdk-solochain-template/pallets/rootdns/src/lib.rs) | | 
| 2.  | pallet-tld | [Link](https://github.com/tcdt-lab/bcdns/blob/master/polkadot-sdk-solochain-template/pallets/tld/src/lib.rs) | | 

**Additional Information**
