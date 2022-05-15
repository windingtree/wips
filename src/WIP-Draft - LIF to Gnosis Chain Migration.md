# WIP-Draft: LIF to Gnosis Chain Migration

  > * WIP: <to be assigned when moved to phase 2>
  > * title: LIF to Gnosis Chain Migration
  > * author: mfw78 <mfw78@protonmail.com>

## Summary

Determine the path forward with migrating `LIF` liquidity from mainnet to Gnosis Chain.

## Motivation

To give certainty to the market, establishing a process by which the `LIF` liquidity will be migrated to Gnosis Chain. Gnosis Chain allows for stablecoin-denominated transactions, delivering certainty to service providers and consumers when onboarding real-world services.

This `WIP` provides clarity over the process by which this migration is to happen.

## Specification

At the implementation block, the following will happen:

1. `LIF1` is paused.
2. `LIF2` is stopped (claimable) and paused.
3. A snapshot is taken of all `LIF2` holders.
4. A snapshot is taken of all `LIF1` holders.
5. A snapshot is taken of all `LIF1` holders in `etherdelta` and `IDEX`.
6. A snapshot is taken of all `LIF1` holders who haven't claimed their "stuck balances" from the `LIF2` contract.
7. All smart contracts from (4), excluding those from (5) have their corresponding `LIF2` airdropped on Ethereum mainnet. **WARNING: NO ADDITIONAL SMART CONTRACTS FROM THE DATE OF RELEASE OF THIS DRAFT WILL BE CONSIDERED FOR DIRECT AIRDROP OF `LIF2` ON ETHEREUM MAINNET IN ORDER TO PREVENT ABUSE OF THIS MIGRATION.**
8. The sum of tokens for all non-smart contract holders from (3) will be bridged in one batch to a permissionless airdropper contract on Gnosis Chain so tokens are never in the custody of an `EOA`. The team will then execute all the airdrops, such that any existing `LIF2` holder does not need to take any action to have their tokens available on Gnosis Chain.
9. The sum of `LIF2` tokens to meet claimable requirements for non-smart contract `LIF1` holders from (4), (5), and (6) will be bridged to a permissioned airdropper contract on Gnosis Chain (requiring a signature from the claimant), so tokens are never in the custody of an `EOA`. It will be the responsibility of any (4), (5), or (6) entitled `LIF2` holder to claim their `LIF2` on Gnosis Chain. **NOTE: THE CLAIM PROCESS WILL BE FREE.**
10. `LIF2` is unpaused.

## Rationale

Signalling in the Winding Tree community has supported [moving](https://snapshot.org/#/windingtree.eth/proposal/0x139b8f3e69a392ccc868de08fcd268b508cbde8f06fed02e383a9ef955fc3d63) the liquidity in bulk to [Gnosis Chain](https://snapshot.org/#/windingtree.eth/proposal/QmNMtnoR2qrNj4xy4pGe6yuQcAwLRmxyhszFAWVZnPa1fZ).

In line with future DAO governance goals, this proposal is designed to ensure as fair and easy a claim process as possible for to-be `LIF2` holders. This assists with decentralizing ownership and subsequent voting power for a DAO migration.

The migration process is to be funded by Winding Tree, saving all `LIF` holders the cost of bridging. The process also allows for the fair claiming of tokens even for those that either accidentally had their tokens stuck in the `LIF1` contract, or tokens in `etherdelta` / `IDEX`.

## Execution

TBD

### Safe Transaction Hash (TBD)

  <tx hash> (*optional)

### Safe Transaction Data

Mandatory for every proposal that requires transaction from Winding Tree DAO.

  <payload>

### Tenderly Simulation

Mandatory for every proposal that requires transaction from Winding Tree DAO.

Link to Tenderly simulation

## Snapshot

*Phase 2 Proposal: Add a link to the corresponding Winding Tree Snapshot poll you’ve created.*