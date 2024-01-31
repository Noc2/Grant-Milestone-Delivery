# Evaluation

- **Status:** Accepted
- **Application Document:** https://github.com/w3f/Grants-Program/blob/master/applications/Plutonication.md
- **Milestone:** 2
- **Previously successfully merged evaluation:** All by keeganquigley

| Number | Deliverable | Accepted | Link | Notes |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| 0a. | Licence | <ul><li>[x] </li></ul> | [Plutonication](https://github.com/RostislavLitovkin/Plutonication/blob/Grant-delivery/LICENSE) | MIT |
| 0b. | Documentation | <ul><li>[x] </li></ul> | Docs for running all codes is in the [Readme](https://github.com/RostislavLitovkin/Plutonication/blob/main/README.md).  | Good.
| 0c. | Testing and Testing guide | <ul><li>[x] </li></ul> | Guide for running tests is in the [Readme](https://github.com/RostislavLitovkin/Plutonication/blob/main/README.md). | Good. |
| 0d. | Docker | <ul><li>[x] </li></ul> | [Sample React dApp Dockerfile](https://github.com/RostislavLitovkin/Plutonication/blob/Grant-delivery/example_dapp/Dockerfile) | Runs successfully. |
| 1. | PlutonicationDAppClient | <ul><li>[x] </li></ul> | [PlutonicationDAppClient.ts](https://github.com/RostislavLitovkin/Plutonication/blob/Grant-delivery/src/PlutonicationDAppClient.ts) | Works as expected. |
| 1a. | initializePlutonicationDAppClient | <ul><li>[x] </li></ul> | [initializePlutonicationDAppClient] | Works as expected. |
| 1b. | onReceivePubkey | <ul><li>[x] </li></ul> | [onReceivePubkey](https://github.com/RostislavLitovkin/Plutonication/blob/b2dde7b8c0b387259a459163d436e83d3c7862c4/src/PlutonicationDAppClient.ts#L20C3-L20C3) | Works as expected. |
| 1c. | signPayload | <ul><li>[x] </li></ul> | [signPayload](https://github.com/RostislavLitovkin/Plutonication/blob/b2dde7b8c0b387259a459163d436e83d3c7862c4/src/PlutonicationDAppClient.ts#L64C13-L64C24) |  Works as expected. |
| 1d. | SendRawAsync | <ul><li>[x] </li></ul> | [SendRawAsync](https://github.com/RostislavLitovkin/Plutonication/blob/b2dde7b8c0b387259a459163d436e83d3c7862c4/src/PlutonicationDAppClient.ts#L77) | Works as expected. |
| 2. | PlutonicationWalletClient | <ul><li>[x] </li></ul> | [PlutonicationWalletClient](https://github.com/RostislavLitovkin/Plutonication/blob/Grant-delivery/src/PlutonicationWalletClient.ts) | Works as expected. |
| 2a. | SendAddress | <ul><li>[x] </li></ul> | [SendAddress](https://github.com/RostislavLitovkin/Plutonication/blob/b2dde7b8c0b387259a459163d436e83d3c7862c4/src/PlutonicationWalletClient.ts#L54) | Works as expected. |
| 2b. | sendPayloadSignature | <ul><li>[x] </li></ul> | [sendPayloadSignature] | Works as expected. |
| 2c. | sendRawSignature | <ul><li>[x] </li></ul> | [sendRawSignature] | Works as expected. |
| 3. | PlutonicationModal | <ul><li>[x] </li></ul> | [PlutonicationModal](https://github.com/RostislavLitovkin/Plutonication/blob/Grant-delivery/src/components/PlutonicationModal.ts) | Works as expected. |
| 4. | NPM package | <ul><li>[x] </li></ul> | [NPM package](https://www.npmjs.com/package/@plutonication/plutonication) | Works as expected. |
| 5. | Sample React dApp | <ul><li>[x] </li></ul> | [Sample React dApp](https://github.com/RostislavLitovkin/Plutonication/tree/Grant-delivery/example_dapp) | Works as expected. |

# General Notes

Great work! I can use the QR codes to pass payloads between the wallet and plutonication server. Functions all work as expected. I hope to see this utilized by wallet devs.

## Tests

E2E tests working:

<img width="994" alt="test" src="https://github.com/w3f/Grant-Milestone-Delivery/assets/35080151/35a1121d-825e-4ebe-a9f8-f6354050224c">

<img width="1000" alt="test 2" src="https://github.com/w3f/Grant-Milestone-Delivery/assets/35080151/ef018075-7271-41a5-a5c3-3c277d048e6b">



<details>
  <summary>Docker builds and runs sucessfully.</summary>

```sh
docker run -p 3000:3000 plutonication-react-dapp-example

> example_dapp@0.1.0 start
> react-scripts start

(node:36) [DEP_WEBPACK_DEV_SERVER_ON_AFTER_SETUP_MIDDLEWARE] DeprecationWarning: 'onAfterSetupMiddleware' option is deprecated. Please use the 'setupMiddlewares' option.
(Use `node --trace-deprecation ...` to show where the warning was created)
(node:36) [DEP_WEBPACK_DEV_SERVER_ON_BEFORE_SETUP_MIDDLEWARE] DeprecationWarning: 'onBeforeSetupMiddleware' option is deprecated. Please use the 'setupMiddlewares' option.
Starting the development server...

Compiled successfully!

You can now view example_dapp in the browser.

  Local:            http://localhost:3000
  On Your Network:  http://172.17.0.2:3000

Note that the development build is not optimized.
To create a production build, use npm run build.

webpack compiled successfully
Compiling...
No issues found.
Compiled successfully!
webpack compiled successfully
No issues found.
^C
```
</details>

<details>
  <summary>Playwright tests pass</summary>

```ts
npx playwright test

Running 2 tests using 2 workers
[chromium] › plutonication.spec.ts:33:5 › Communication between dApp and Wallet
2024-01-22 17:04:42        API/INIT: RPC methods not decorated: alephNode_emergencyFinalize, alephNode_getBlockAuthor, alephNode_ready
2024-01-22 17:04:42        API/INIT: aleph-node/68: Not decorating unknown runtime apis: 0x2be3f75b696ad1f6/1
Connected to api
Plutonication received message: Someone connected <3
Plutonication received message: Someone connected <3
Received message: Someone connected <3
Wallet connected
Receive payload
Payload to Sign 0xac050700004769bbe59968882c1597ec1151621f0193547285125f1c1337371c013ff61f0f0080c6a47e8d03481c0400430000001100000005d5279c52c484cc80396535a316add7d47b1c5b9e0398dd1f584149341460c5d12ff783a76a5e07156d2a3ff61745b3a1f892bf6247c1b3bf0fd7ba2085eda6
Received raw: [object Object]
  2 passed (11.4s)
```
</details>


Example app starts successfully:
```
npm start
Compiled successfully!

You can now view example_dapp in the browser.

  Local:            http://localhost:3000
  On Your Network:  http://10.0.0.131:3000

Note that the development build is not optimized.
To create a production build, use npm run build.

webpack compiled successfully
Files successfully emitted, waiting for typecheck results...
Issues checking in progress...
No issues found.
```
