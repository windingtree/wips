# WIP-Draft: LIF Token Feature-set Finalization

  > * WIP: <to be assigned when moved to phase 2>
  > * title: LIF Token Feature-set Finalization
  > * author: mfw78 <mfw78@protonmail.com>

## Summary

Establishes a final feature set that the LIF token would implement.

## Terminology

* `LIF` token is taken to be the token contract that will be used within Winding Tree protocols.
* `LIF1` token is taken to mean the `LIF` token issued at `ICO`.
* `LIF2` token is taken to mean the `LIF` token issued to address `ERC20` issues relating to `LIF1`.

## Motivation

As there is a 1:1 claim ratio beween `LIF1` and `LIF2`, enforced by smart contract, as well as `LIF2` smart contract upgradeability to consider, this WIP sets out the final feature set and subsequent renouncement of upgradability privileges. Intermediate steps in finalization, such as Layer 2 migration are outside of scope for this WIP.  

## History

Historically, the [LIF1](https://etherscan.io/token/0xeb9951021698b42e4399f9cbb6267aa35f82d59d) did not implement optional features of the ERC20 contract that have come to be relied upon in the Ethereum ecosystem. Notably `name`, `symbol`, and `decimals` were placed in uppercase instead of lowercase, in violation of the [`EIP-20`](https://eips.ethereum.org/EIPS/eip-20) standard. Thus `LIF2` was born to remedy this.

`LIF2` currently implements a custom `Claimable` interface that honors the redemption of `LIF2` for `LIF1`. `LIF2` is also implemented using the EIP-1967 Proxy pattern, which therefore means implementation logic can be arbitrarily changed. Both of these are security risks that require consideration when developing tokenomic structures, needlessly increasing complexity.

## Current Specification

Currently the `LIF2` contract supports:

* ERC20
* ERC20Metadata
* ERC20Permit (ERC2612) / EIP712
* Pausable
* Ownable
* Claimable

### ERC20

The standard balance keeping mechanisms / transfer functions that are specified in `EIP-20`.

### ERC20Metadata

Provides the standard metadata mechanisms such as `name()`, `symbol()`, `decimals()` specified as optional in `EIP-20`.

### ERC20Permit (ERC2612) / EIP712

A draft specification that is widely used in the Ethereum ecosystem allowing gasless transactions where the owner can instead 'sign' an `approve` instead of having to send an explicit transaction for the approve. This is getting increased utilization through the likes of Uniswap that permit EIP-712 signatures instead of an `approve` transaction, saving the user gas fees.

### Pausable

An ERC20 feature that allows the token's `transfer` functions to be paused by the `owner` of the contract. Currently `LIF2`'s owner is set to the community multi-sig. This may be a useful function in the event of an emergency such as a hacked bridge, centralized exchange, implementation error, or related system malfunction.

### Ownable

A simple access control interface to restrict privileged contract actions to that of the contract owner (currently set to the community multi-sig).

### Claimable

This is a custom interface that allows for a user holding `LIF1` to claim the same amount of `LIF2`. It's this interface that has been facilitating the token swap.

## Proposed Specification

It's proposed that the specification of the `LIF2` token be changed to:

* ERC20
* ERC20Metadata
* ERC20Permit (ERC2612) / EIP712
* Pausable
* AccessControl
* Mint / ERC20Burnable

With the above feature set, the `LIF2` token's `ProxyAdmin` (ie. the community multi-sig) would **RENOUNCE** administrative privileges on `LIF2`, effectively making this the **FINAL, IMMUTABLE SPECIFICATION OF LIF2**, delivering certainty with respect to token features / implementation and **REMOVING CLAIMABLE** functionality.

### AccessControl

The `Ownable` authorization mechanism would be replaced with the OpenZepplin `AccessControl` authorization mechanism, providing the following roles:

* `DEFAULT_ADMIN_ROLE` - To be set to the community multi-sig.
* `PAUSER_ROLE` - To be set to the community multi-sig.
* `MINTER_ROLE` - **RESERVED**.

### Mint / Burning variable supply

Allows for creation / destruction of `LIF`.

## Rationale

This proposal aims to meet the following key points for a transition towards a DAO:

1. Feature stabilization.
2. No claims from the token contract.
3. Future expansion for custon tokenomic functionality.

The overall desire is to finalize the contract, and simplify the code-base for audit purposes. This will grant token holders / ecosystem participants feature certainty.

When considering future DAO governance configurations, having `LIF1` to consider is burdensome from a strategy / implementation perspective, therefore there is the strong desire to close claims *from the token contract*. A separate WIP is in draft status with regards to the `LIF1` to `LIF2` claiming.

If the contract is to be finalized without enabling `mint` and `burn` functionality, this would preclude a number of future tokenomic strategies that may be implemented (inflationary / deflationary etc).

Minting is restricted to addresses that possess the `MINTER_ROLE`, of which this will be **RESERVED** and **NO MINTING PERMISSIONS WILL BE ASSIGNED BY THIS WIP**. Future tokenomics strategies are out of scope for this WIP and any addition to the `MINTER_ROLE` in the future is expected to attract significant debate about the merits of such.

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