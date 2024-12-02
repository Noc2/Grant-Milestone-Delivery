# Evaluation

- **Status:** accepted
- **Application Document:** [P2P State Channels](https://github.com/w3f/Grants-Program/blob/master/applications/P2PStateChannels.md)
- **Milestone:** 2
- **Previously successfully merged evaluation:** All by PieWol

| Number | Deliverable | Accepted | Link | Evaluation Notes |
| ------ | ----------- | :------: | ---- |----------------- |
| **0a.** | License | <ul><li>[x] </li></ul> | [License file](https://github.com/peer3to/state-channels-plus/blob/master/LICENSE)  | MIT, compiling the solidity contracts emits warnings about unspecified licenses. |
| **0b.** | Documentation | <ul><li>[x] </li></ul> |https://github.com/peer3to/state-channels-plus/blob/master/docs/mfsDocs.md | ok  |
| **0c.** | Testing and Testing Guide | <ul><li>[x] </li></ul> | https://github.com/peer3to/state-channels-plus/tree/master/test | ok |
| **0d.** | Docker | <ul><li>[x] </li></ul> | https://github.com/peer3to/state-channels-plus/blob/master/Dockerfile | ok |
| **0e.** | Article | <ul><li>[x] </li></ul> | https://docs.google.com/document/d/1qS7ZY8noaObP5Ze1mVOaydDBih4jHYym4qacAx46Fas | ok |
| **1** | Networking and Discovery | <ul><li>[x] </li></ul> | https://github.com/peer3to/state-channels-plus/blob/master/src/transport/HolepunchTransport.ts https://github.com/peer3to/state-channels-plus/blob/master/src/Holepunch.ts | ok |
| **2** | P2P State Machine | <ul><li>[x] </li></ul> | https://github.com/peer3to/state-channels-plus/blob/master/src/evm/EvmStateMachine.ts| ok |
| **3** | Agreement Tracking | <ul><li>[x] </li></ul> | https://github.com/peer3to/state-channels-plus/blob/master/src/AgreementManager.ts | ok |
| **4** | Dispute Handling | <ul><li>[x] </li></ul> | https://github.com/peer3to/state-channels-plus/blob/master/src/DisputeHandler.ts | ok |
| **5** | Virtual Clock | <ul><li>[x] </li></ul> | https://github.com/peer3to/state-channels-plus/blob/master/src/Clock.ts | ok |
| **6** | Observing & Notifying | <ul><li>[x] </li></ul> | https://github.com/peer3to/state-channels-plus/blob/master/src/P2pEventHooks.ts | ok |



## General Notes
Thanks for adding more inline documentation and enriching the article.

## Tests
the tests are still passing since there have been no changes since the delivery of m1


