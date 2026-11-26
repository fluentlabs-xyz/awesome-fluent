# Awesome Fluent [![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

> A curated list of resources, tools, libraries, and guides for building with [Fluent](https://www.fluent.xyz/).

Fluent is an Ethereum L2 with blended execution: EVM (Solidity, Vyper) and Wasm (Rust) contracts compile to one runtime, rWasm, share one account space, and call each other directly. Fluent mainnet is live.

## Contents

- [Start here](#start-here)
- [Networks](#networks)
- [Fluent Connect](#fluent-connect)
- [Developer tools](#developer-tools)
- [Developer guides](#developer-guides)
- [Examples and templates](#examples-and-templates)
- [Core protocol](#core-protocol)
- [Specs and security](#specs-and-security)
- [Ecosystem](#ecosystem)
- [Community](#community)
- [Contribute](#contribute)

## Start here

- [Fluent documentation](https://docs.fluent.xyz/) - Official docs for builders: networks, guides, SDKs, architecture.
- [Blended 101](https://docs.fluent.xyz/knowledge-base/blended-101) - What blended execution is and why it matters.
- [Fluent overview](https://docs.fluent.xyz/knowledge-base/fluent-overview) - How Fluent works, in one page.
- [Glossary](https://docs.fluent.xyz/glossary) - Terms used across the Fluent ecosystem.
- [Builder Hub](https://portal.fluent.xyz/builder) - Fluent Portal for builders: testnet faucet and app submission.

## Networks

All network parameters, kept current: [Connect to Fluent](https://docs.fluent.xyz/connect-to-fluent).

- **Mainnet** (chain ID 25363)
  - RPC: `https://rpc.fluent.xyz/`
  - [FluentScan](https://fluentscan.xyz/) - Block explorer.
  - [Native bridge](https://portal.fluent.xyz/user/bridge) - Bridge ETH and tokens between Ethereum and Fluent.
  - [Nexus Bridge](https://nexus.hyperlane.xyz/) - Hyperlane-powered cross-chain bridge.
- **Testnet** (chain ID 20994)
  - RPC: `https://rpc.testnet.fluent.xyz/`
  - [FluentScan Testnet](https://testnet.fluentscan.xyz/) - Block explorer.
  - [Faucet](https://portal.fluent.xyz/builder/faucet) - Testnet and devnet ETH.
- **Devnet** (chain ID 20993, experimental, may be reset at any time)
  - RPC: `https://rpc.devnet.fluent.xyz/`
  - [FluentScan Devnet](https://devnet.fluentscan.xyz/) - Block explorer.

## Fluent Connect

Fluent Connect lets an app sign people in with a Fluent ID smart account or an external wallet, then run batched and sponsored transactions with it.

- [Fluent Connect docs](https://docs.fluent.xyz/fluent-connect/) - Getting started, concepts, configuration, guides, API reference.
- [@fluent.xyz/connect](https://www.npmjs.com/package/@fluent.xyz/connect) - The React widget on npm.
- [fluent-connect-sdk](https://github.com/fluentlabs-xyz/fluent-connect-sdk) - Source of the widget and the headless SDK, with a chess demo app.
- [Fluent Connect](https://connect.fluent.xyz/) - The Fluent ID wallet that people sign in with.
- [Access request](https://tally.so/r/5XbrAE) - Request an `appId` and a login client for your app.

## Developer tools

- [gblend](https://github.com/fluentlabs-xyz/gblend) - Foundry fork for Fluent: build, test and deploy Solidity and Rust/Wasm contracts. Install with `gblendup`. [Docs](https://docs.fluent.xyz/gblend/).
- [Fluentbase SDK](https://docs.fluent.xyz/fluentbase-sdk/build-w-fluentbase-sdk) - Write Rust smart contracts for Fluent ([fluentbase-sdk on crates.io](https://crates.io/crates/fluentbase-sdk)).
- [Goldsky](https://docs.goldsky.com/chains/fluent) - Indexing and subgraphs for Fluent.
- [Infrastructure partners](https://docs.fluent.xyz/infrastructure/) - RPC, wallets, oracles, account abstraction, indexing and on-ramps live on mainnet.

## Developer guides

- [Rust contracts](https://docs.fluent.xyz/developer-guides/smart-contracts/rust) - A guide to building Rust-based Wasm contracts on Fluent.
- [Solidity contracts](https://docs.fluent.xyz/developer-guides/smart-contracts/solidity) - A guide to building with Solidity on Fluent.
- [Building a blended app](https://docs.fluent.xyz/developer-guides/building-a-blended-app/) - Solidity and Rust contracts calling each other, from quickstart to deploy.
- [EIP-7702 on Fluent](https://docs.fluent.xyz/developer-guides/account-abstraction/eip-7702) - Account abstraction with EIP-7702.

## Examples and templates

- [examples](https://github.com/fluentlabs-xyz/examples) - Example projects for `gblend init --template`: counter, ERC-20 in Rust, chess puzzle, tiles.
- [Blended template](https://github.com/fluentlabs-xyz/blended-template-foundry-cli) - Starter project with a Solidity contract calling a Rust/Wasm module.
- [Rookrift](https://rookrift.xyz/) - Chess on Fluent: a live game platform built on Fluent.
- [Uniswap V2 Foundry](https://github.com/fluentlabs-xyz/uniswapV2_foundry_deploy) - Foundry deploy scripts for Uniswap V2 on Fluent testnet.
- [Uniswap V2 frontend](https://github.com/fluentlabs-xyz/uniswapV2_frontend_testnet) - Simple Uniswap V2 frontend on Fluent testnet ([live](https://fluentlabs-xyz.github.io/uniswapV2_frontend_testnet/)).

## Core protocol

- [fluentbase](https://github.com/fluentlabs-xyz/fluentbase) - Fluent's execution stack: runtimes, system contracts, SDK crates, and the `fluent` node ([run a node](https://github.com/fluentlabs-xyz/fluentbase#run-a-node), [releases](https://github.com/fluentlabs-xyz/fluentbase/releases)).
- [rwasm](https://github.com/fluentlabs-xyz/rwasm) - rWasm: a zk-friendly, Rust-based WebAssembly VM and its compilers.
- [solidity-contracts](https://github.com/fluentlabs-xyz/solidity-contracts) - L1/L2 bridge contracts: message bridge, ERC-20 and ETH gateways, L1 rollup contract.
- [blend-token](https://github.com/fluentlabs-xyz/blend-token) - The BLEND ERC-20 token with gasless permits and transfers.
- [fluent-stf](https://github.com/fluentlabs-xyz/fluent-stf) - Fluent's state transition function compiled to the SP1 zkVM.
- Forks Fluent maintains as part of the stack:
  - [reth-rwasm](https://github.com/fluentlabs-xyz/reth-rwasm) - Reth, patched for the Fluent node.
  - [revm-rwasm](https://github.com/fluentlabs-xyz/revm-rwasm) - revm, patched for rWasm.
  - [rwasm-zkvm](https://github.com/fluentlabs-xyz/rwasm-zkvm) - SP1 zkVM, adapted for rWasm.

## Specs and security

- [Fluentbase docs](https://github.com/fluentlabs-xyz/fluentbase/tree/devel/docs) - Protocol docs for contributors and auditors: routing, syscalls, gas and fuel, security invariants, RPC differences.
- [System architecture](https://docs.fluent.xyz/system-architecture/overview) - Rollup architecture, execution model, precompiles, bridge.
- [Fluent Tech Book](https://github.com/fluentlabs-xyz/tech-book) - Specs for Fluent, Fluentbase and rWasm ([read online](https://book.gblend.xyz/)).
- [Audits](https://github.com/fluentlabs-xyz/fluentbase/tree/devel/audits) - Audit reports of Fluentbase.

## Ecosystem

- [Fluent Portal](https://portal.fluent.xyz/) - Showcase of apps building on Fluent.
- [Submit your app](https://portal.fluent.xyz/builder) - Get your app into the ecosystem through the Builder Hub.

## Community

- [X: Fluent](https://x.com/fluentxyz)
- [X: Fluent Labs](https://x.com/fluentlabsxyz)
- [X: Blended Builders Club](https://x.com/BlendedBldrs)
- [Discord](https://discord.com/invite/fluentxyz)
- [GitHub](https://github.com/fluentlabs-xyz)
- [Contribute to the docs](https://github.com/fluentlabs-xyz/docs-docusaurus) - Source of docs.fluent.xyz; pull requests welcome.

## Contribute

Contributions welcome! Read the [contribution guidelines](contributing.md) first.
