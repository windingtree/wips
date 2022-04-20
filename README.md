# Governance Process

This document gives an overview of the WindingTree DAO governance processes, and how *you* can get
involved.

It outlines a suggested process for developing and advancing WindingTree Governance Proposals.

The purpose of this process is to encourage discussion and help the community to get the needed
information and sufficient time in order to review and vote on proposals.

**Note**: this is a living document intended to be owned, modified and enforced by the WindingTree
community.

## What is WindingTree DAO

WindingTree DAO is an open organization of developers, traders, industry professionals and many
more community members aligned with its vision. WindingTree is focused on fair and decentralised
*real-world service* trading systems - in particular building, maintaining and advancing the 
WindingTree protocol. WindingTree protocol powers a network of service providers, consumers, and
solvers, enabling trustless and efficient real-world service trading, reducing reliance on
centralised siloed market aggregators.  Providing uniform *open* access to service provider
inventory, reducing market information assymetry, are core to WindingTree's practices.

## Vision

We foresee a future where service providers across all service-oriented industries will be able to
librate not just their data and wealth, but also their income stream through decentralized
blockchain-based marketplaces. WindingTree's vision is a decentralized world where
*real-world services* can be traded in a **fair, efficient, and reliable manner** among people and
communities around the world. Our mission is to build a protocol that places it's users - service
providers and consumers - in direct connection with one another, reducing intermediaries, enabling
all users to act in the marketplace knowing that they have *supreme transparency and fair price
discovery*.

We are determined to make WindingTree Protocol the **canonical marketplace** for the trading of 
*real-world services* by applying continuous innovation, encouraging intellectual discourse and
expanding the WindingTree Protocol ecosystem - inviting the brightest minds to join the community. 

## Forum

WindingTree DAO's `wips` Github repository discussion page is the main venue for governance-related
discussion. Anyone with a Github account can post and participate in discussions.

Ad-hoc discussion may take place on [Discord](https://discord.gg/fGqeXzqKVU).

## Snapshot

[WindingTree DAO's snapshot space](https://snapshot.org/#/windingtree.eth) is a simple voting
interface that allows users to vote on proposals. Votes on WindingTree are weighted by the number
of LIF1 and LIF2 held by the address used to vote.

## Governance Process

The WindingTree DAO governance process includes two steps for proposals to get approved.

**Phase 1**: Draft Proposal — Community Discussion (*min 7 days*)
The purpose of the Draft Proposal phase is to establish formal discussion around a potential
proposal. To create a Draft Proposal please follow these steps:

* Create a new draft WIP using the template in the repository and submit via PR.
* Engage in discussion to build support for the proposal.
* If your proposal requires any additional on chain interaction by 
  [WindingTree DAO](https://etherscan.io/address/0x876969b13dcf884C13D4b4f003B69229E6b7966A), you
  will need to write the code for your proposal while it is in draft stage. You may wish to wait
  until the proposal gathers some support before doing this.

Once you are confident the proposal is in a stable state, and *at least 7 days* have passed since
the proposal was first published, you can ask a code reviewer (moderator) to move the proposal to
phase 2 (merge into `main` branch).

**Phase 2**: Active Proposal — Forum / Snapshot

* Request that a code reviewer (moderator) advance your proposal to a vote by tagging them in the
  PR issue.
* If the proposal has successfully finished phase 1, a moderator will:
  * Assign the proposal a proposal number in the form `WIP-###`.
  * Change the topic from `Draft Proposal` to `Active Proposal`.
  * Create a [snapshot](https://snapshot.org/#/windingtree.eth) vote with a duration of 7 days, and
    cross link the snapshot and forum post.
  * If your proposal should include an executable transactions, you will now need to provide the
    proposed transactions to be included in the proposal.
* [Gnosis Safe transaction builder](https://help.gnosis-safe.io/en/articles/4680071-transaction-builder) 
  could be used to craft transactions to be included in a proposal.

## Governance Parameters

* Final approval of proposals will be made through `LIF1` and `LIF2` token voting on the 
  [windingtree.eth snapshot space](https://snapshot.org/#/windingtree.eth).
* The required quorum for a *WindingTree Improvement Proposal (WIP)* to pass is defined by a set
  limit of `999057.5780542548` `LIF1` and `LIF2` (4%) tokens required to vote **YES**.
* Additionally, in order for a proposal to be approved, **YES** votes should account for **>50%**
  of total participating votes. (simple majority)
* Once a proposal is approved, if this proposal includes executable transactions, WindingTree's 
  multisig signers will meet and execute the proposal.
