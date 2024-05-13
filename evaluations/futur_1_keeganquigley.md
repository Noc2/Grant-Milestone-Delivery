# Evaluation

- **Status:** Accepted
- **Application Document:** https://github.com/w3f/Grants-Program/blob/master/applications/FuturFusion.md
- **Milestone:** 1

| Number | Deliverable | Link | Accepted | Notes |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| 0a. | License | [Apache 2.0](https://github.com/RELAI-Network/relai-network/blob/main/LICENSE) | <ul><li>[x] </li></ul> |  	Apache License 2.0 | 
| 0b. | Documentation | [Substrate Documentation](https://github.com/RELAI-Network/relai-network) | <ul><li>[x] </li></ul> | Thorough docs. | 
| 0c. | Testing and Testing Guide | [Relai Network Pallets](https://github.com/RELAI-Network/relai-network/blob/main/README.md#testing)| <ul><li>[x] </li></ul> | Good. | 
| 0d. | Articles |[Futur Protocol Stack](https://blog.relai.network/futur-protocol-stack)<br/> [Futur Console Account Creation](https://blog.relai.network/futur-console-account-creation-relai-network-devnet)<br/> [Futur Console Book Publishing](https://blog.relai.network/futur-console-book-publication-relai-network-devnet) <br/> [Futur Console App/Game Publishing](https://blog.relai.network/futur-console-appgame-creation-relai-network-devnet)<br/> [Futur Store App Guide](https://blog.relai.network/futur-store-app-devnet-relai-network)| <ul><li>[x] </li></ul> | Good. |
| 1 | Futur Store Mobile app |[Futur Store mobile app](https://github.com/RELAI-Network/futurstore-app)| <ul><li>[x] </li></ul> | Good. |
| 2 | Futur Protocol Runtime modules |[Futur-Asset-Reg and Futur-Creators-Reg](https://github.com/RELAI-Network/relai-network/tree/main/pallets)| <ul><li>[x] </li></ul> | Good. |
| 3 | SAST/DAST module |[Mobsf](https://mobsf.github.io/docs)| <ul><li>[x] </li></ul> | Good. |   
| 4 | Futur Console |[Futur Console](https://github.com/RELAI-Network/futur-console-react)| <ul><li>[x] </li></ul> | Good. |   
| 5 | Backend Server|[Cloud Functions](https://github.com/RELAI-Network/relai-fn)| <ul><li>[x] </li></ul> | Good. | 
| 6 | Storage Layer|`IPFS via Crust` and `Firebase Storage`| <ul><li>[x] </li></ul> | Good. | 
| 7 | Kaggu|[Kaggu Ebook Reader](https://github.com/RELAI-Network/kaggu)| <ul><li>[x] </li></ul> | Good. | 

# General Notes

Overall nice app, though more tests could be added and would be nice to see some error handling improvements. Also some UI glitches. Also would be nice to eventually see everything cleaned up and combined under a monorepo.

## Backend

11 unit tests passing:

```rust
warning: `futur-assets-reg` (lib) generated 2 warnings
   Compiling relai-network-runtime v4.0.0-dev (/home/ubuntu/relai-network/runtime)
warning: `futur-assets-reg` (lib test) generated 2 warnings (2 duplicates)
   Compiling relai-network v4.0.0-dev (/home/ubuntu/relai-network/node)
    Finished `test` profile [unoptimized + debuginfo] target(s) in 50.25s
     Running unittests src/lib.rs (target/debug/deps/futur_assets_reg-f95b237109e689e4)

running 5 tests
test mock::__construct_runtime_integrity_test::runtime_integrity_tests ... ok
test tests::submit_asset_works ... ok
test tests::update_asset_works ... ok
test tests::buy_asset_works ... ok
test tests::pub_unpub_asset_works ... ok

test result: ok. 5 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running unittests src/lib.rs (target/debug/deps/futur_creators_reg-01a66a544616f9a0)

running 4 tests
test mock::__construct_runtime_integrity_test::runtime_integrity_tests ... ok
test tests::set_registration_fees_works ... ok
test tests::register_developer_works ... ok
test tests::unregister_developer_works ... ok

test result: ok. 4 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.06s

     Running unittests src/lib.rs (target/debug/deps/nft-724c03744dc6c45d)

running 2 tests
test mock::__construct_runtime_integrity_test::runtime_integrity_tests ... ok
test tests::it_works_for_default_value ... ok

test result: ok. 2 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out; finished in 0.04s

     Running unittests src/lib.rs (target/debug/deps/relai_network-2123ea4549b0eb53)
```

Consider fixing cargo clippy warnings:

<details>
  <summary>Output</summary>

```rust
Checking futur-assets-reg v0.1.0 (/home/ubuntu/relai-network/pallets/futur-assets-reg)
warning: unused variable: `review_str`
   --> pallets/futur-assets-reg/src/lib.rs:295:9
    |
295 |                 let review_str =
    |                     ^^^^^^^^^^ help: if this is intentional, prefix it with an underscore: `_review_str`
    |
    = note: `#[warn(unused_variables)]` on by default

warning: associated functions `do_fetch_reviews` and `fetch_reviews` are never used
   --> pallets/futur-assets-reg/src/lib.rs:271:6
    |
216 |     impl<T: Config> Pallet<T> {
    |     ------------------------- associated functions in this implementation
...
271 |         fn do_fetch_reviews() -> Result<(), http::Error> {
    |            ^^^^^^^^^^^^^^^^
...
320 |         fn fetch_reviews() -> Result<(), &'static str> {
    |            ^^^^^^^^^^^^^
    |
    = note: `#[warn(dead_code)]` on by default

warning: equality checks against false can be replaced by a negation
   --> pallets/futur-assets-reg/src/lib.rs:163:12
    |
163 |             ensure!(maybe_asset.published == false, Error::<T>::AssetIsPublished);
    |                     ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ help: try simplifying it as shown: `!maybe_asset.published`
    |
    = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#bool_comparison
    = note: `#[warn(clippy::bool_comparison)]` on by default

warning: the borrowed expression implements the required traits
   --> pallets/futur-assets-reg/src/lib.rs:223:41
    |
223 |             AssetRegistry::<T>::insert(asset_id, &asset);
    |                                                  ^^^^^^ help: change this to: `asset`
    |
    = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#needless_borrows_for_generic_args
    = note: `#[warn(clippy::needless_borrows_for_generic_args)]` on by default

warning: this let-binding has unit value
   --> pallets/futur-assets-reg/src/lib.rs:321:4
    |
321 |             let _ = Self::do_fetch_reviews().map_err(|_| "Failed to Reviews")?;
    |             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ help: omit the `let` binding: `Self::do_fetch_reviews().map_err(|_| "Failed to Reviews")?;`
    |
    = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#let_unit_value
    = note: `#[warn(clippy::let_unit_value)]` on by default

warning: empty doc comment
  --> pallets/futur-assets-reg/src/lib.rs:48:12
   |
48 |     #[pallet::storage]
   |               ^^^^^^^
   |
   = help: consider removing or filling it
   = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#empty_docs
   = note: `#[warn(clippy::empty_docs)]` on by default

warning: empty doc comment
  --> pallets/futur-assets-reg/src/lib.rs:52:12
   |
52 |     #[pallet::storage]
   |               ^^^^^^^
   |
   = help: consider removing or filling it
   = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#empty_docs

warning: empty doc comment
  --> pallets/futur-assets-reg/src/lib.rs:61:12
   |
61 |     #[pallet::storage]
   |               ^^^^^^^
   |
   = help: consider removing or filling it
   = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#empty_docs

warning: `futur-assets-reg` (lib) generated 8 warnings (run `cargo clippy --fix --lib -p futur-assets-reg` to apply 3 suggestions)
    Checking handlebars v4.5.0
    Checking hyper-rustls v0.24.2
    Checking sc-consensus-slots v0.10.0-dev (https://github.com/paritytech/substrate.git?branch=polkadot-v1.0.0#948fbd2f)
    Checking pallet-grandpa v4.0.0-dev (https://github.com/paritytech/substrate.git?branch=polkadot-v1.0.0#948fbd2f)
    Checking futur-creators-reg v0.1.0 (/home/ubuntu/relai-network/pallets/futur-creators-reg)
warning: empty doc comment
  --> pallets/futur-creators-reg/src/lib.rs:42:12
   |
42 |     #[pallet::storage]
   |               ^^^^^^^
   |
   = help: consider removing or filling it
   = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#empty_docs
   = note: `#[warn(clippy::empty_docs)]` on by default

warning: empty doc comment
  --> pallets/futur-creators-reg/src/lib.rs:46:12
   |
46 |     #[pallet::storage]
   |               ^^^^^^^
   |
   = help: consider removing or filling it
   = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#empty_docs

warning: empty doc comment
  --> pallets/futur-creators-reg/src/lib.rs:50:12
   |
50 |     #[pallet::storage]
   |               ^^^^^^^
   |
   = help: consider removing or filling it
   = help: for further information visit https://rust-lang.github.io/rust-clippy/master/index.html#empty_docs

warning: `futur-creators-reg` (lib) generated 3 warnings
```
</details>

I'm able to request tokens with `curl "https://faucet-tskg7nm5aa-uc.a.run.app?requester=your_substrate_wallet_address"`

## Front-end UI

`futur-console-react` runs both locally and prod version:

```ts
  VITE v4.5.2  ready in 699 ms

  ➜  Local:   http://localhost:3030/
  ➜  Network: use --host to expose
  ➜  press h to show help
[ESLint] Found 0 error and 0 warning
```
App works and I am able to create a listing.

<img width="1409" alt="relai 2" src="https://github.com/w3f/Grant-Milestone-Delivery/assets/35080151/64d7ebad-61a5-4463-bb26-8dcb5a108cf1">

Cosmetic note: "Install Polkadot" seems a little confusing, I think this button could be relabled to something like "Install Polkadot-JS extension". Talisman button looks good.

Also some minor spelling errors:

<img width="589" alt="spelling" src="https://github.com/w3f/Grant-Milestone-Delivery/assets/35080151/2ec04d73-9034-4757-ba90-f5d0e0260ad9">

