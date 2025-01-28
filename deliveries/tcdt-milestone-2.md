# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** tcdt 
* **Milestone Number:** 2

**Context** 

This milestone defines the protocols that must be adhered to by clients for various types of interactions with the architecture. The milestone also deelivers packages for interacting with the architecture along with sample clients implemented on top of them.

**Deliverables**

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- |------------- |
| 0a. | License | Apache 2.0 | | 
| 0b.  | Documentation | [NodeJS Client](https://github.com/tcdt-lab/bcdns/blob/master/dns_client/README.md), [Golang Client](https://github.com/tcdt-lab/bcdns/blob/master/dns_client_golang/README.md), [Overview](https://github.com/tcdt-lab/bcdns/blob/master/README.md#enabling-blockchain-interoperability-through-discovery) | | 
| 0c.  | Testing and Testing Guide | | The clients should be tested by interacting with a live node and setting up the chain specifications stored such that they point to the node itself to simulate the layered architecture. | 
| 0d.  | Docker | | Since the clients are used for one-time run commands such as resolving a domain, they should be compiled and ran without docker. | 
| 1.  | Domain Resolution Protocol | [Link](https://github.com/tcdt-lab/bcdns/blob/master/README.md#domain-resolution-protocol) | | 
| 2.  | Domain Registration Protocol | [Link](https://github.com/tcdt-lab/bcdns/blob/master/README.md#domain-registration-protocol) | | 
| 3.  | Domain Revocation Protocol | [Link](https://github.com/tcdt-lab/bcdns/blob/master/README.md#domain-revocation-protocol) | | 
| 4.  | Domain Transfer Protocol | [Link](https://github.com/tcdt-lab/bcdns/blob/master/README.md#domain-transfer-protocol) | | 
| 5.  | bcdns-adapter-node | [Link](https://github.com/tcdt-lab/bcdns/blob/master/dns_client) | | 
| 6.  | bcdns-adapter-golang | [Link](https://github.com/tcdt-lab/bcdns/blob/master/dns_client_golang) | | 

**Additional Information**
