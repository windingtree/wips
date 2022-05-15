# WIP-Draft: End LIF2 Claim Period

  > * WIP: <to be assigned when moved to phase 2>
  > * title: End LIF2 Claim Period
  > * author: mfw78 <mfw78@protonmail.com>

## Summary

Introduces soft and hard claim periods for LIF2.

## Motivation

Allowing unlimited claim periods for `LIF2` from `LIF1` present issues from a security perspective when developing DAO voting strategies using `LIF2` and future tokenomic strategies for `LIF2`.

Therefore, this `WIP` seeks to outline firm timelines by which the claim will expire.

## Specification

After the Gnosis Chain migration, once the claimants' tokens are placed into permissed airdropper contract, their claim:

1. 100% claimable until the **soft claim time limit**.
2. Linearly reduces to 0% claimable until the **hard claim time limit**.
3. All unclaimed tokens, or portion thereof are **claimable by the community multi-sig**.

It is proposed that the *soft claim time limit* be set to 90 days and the *hard claim time limit* be set to 180 days. These times are from the time of the Gnosis Chain claim contract deployment.

## Rationale

It takes time for market participants to get information surrounding claims / events. This allows for both a reasonable period of time for such information to propagate, balanced with creating a time incentive for claimants.

## Dependencies

This `WIP` depends on:

* `WIP-Draft: LIF to Gnosis Chain Migration`

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