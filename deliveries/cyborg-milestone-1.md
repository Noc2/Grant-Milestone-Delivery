# Milestone Delivery :mailbox:

**The delivery is according to the official [milestone delivery guidelines](https://github.com/w3f/Grants-Program/blob/master/docs/Support%20Docs/milestone-deliverables-guidelines.md).**  

* **Application Document:** https://github.com/w3f/Grants-Program/blob/master/applications/Cyborg.md
* **Milestone Number:** 1

**Context**

## Task Verification System

A task verification system that verifies off-chain compute task results on-chain using parallel execution and hash equations. This forms the base infrastructure for our enterprise-ready product for machine learning training.

**Deliverables** 

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | [License](https://github.com/Cyborg-Network/cyborg-parachain/blob/master/LICENSE) | GPLv3 |
| **0b.** | [Documentation](https://github.com/Cyborg-Network/cyborg-parachain/blob/master/INSTRUCTIONS.md#cyborg-network---milestone-1-delivery) | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how users can (for example) deploy docker images using our interface. |
| **0c.** | [Testing and Testing Guide](https://github.com/Cyborg-Network/cyborg-parachain/blob/master/INSTRUCTIONS.md#testing-guide) | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | [Docker](https://github.com/Cyborg-Network/cyborg-parachain/tree/9685a55711b2e1ec63fdbc6603965e7b3784f8d6) | We will provide a Dockerfile that can be used to deploy a local substrate chain for testing. |
| 1. | [Working Demo](https://drive.google.com/file/d/1URMopsQZBgGCsZYqiznWOxwmg9wDIdfH/view?usp=sharing) | We will provide video documentation to help developers understand the process of deploying containered tasks.|
| 2. | [Task Examples](https://github.com/Cyborg-Network/cyborg-parachain/blob/master/README.md#task-examples) | We will provide example containers and data sets to help programmers understand and execute batch processes. Currently we provide Examples for Docker, Bash, Terraform etc.. |
| 3. | [Substrate Module: Task Management](https://github.com/Cyborg-Network/cyborg-parachain/tree/9685a55711b2e1ec63fdbc6603965e7b3784f8d6/pallets/task-management) | This pallet will be responsible for assign the task to a secondary cluster for result verification. Once verifed the accepted result will be added to the block. |
| 4. | [Substrate Module: Edge Connect](https://github.com/Cyborg-Network/cyborg-parachain/tree/9685a55711b2e1ec63fdbc6603965e7b3784f8d6/pallets/edge-connect)| This pallet will posses the logic for schedluing tasks to a specific cluster that matches the required specifications|
| 5. | [Worker K3S Operator](https://github.com/Cyborg-Network/Worker) | The k3s worker acts as a trusted controller. It securely stores deployment states, including manifests and defined secrets. Based on the manifests, the Worker uses remote attestation to authenticate the task exceution process.. |
| 6. | [Worker logs](https://github.com/Cyborg-Network/cyborg-parachain/blob/master/INSTRUCTIONS.md#worker-logs) | The execution logs of the deployed container to serve as a proof of work. |
