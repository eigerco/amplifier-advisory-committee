# Proposing a chain

## Process for Proposers

1. Chain integrators create a Proposal for a new chain.
    - A template for the proposal with the key criteria to be assessed can be found in [here](../chains//_TEMPLATE//PROPOSAL.md). Fork the repository and create a pull request with your proposal
    - Proposals must include technical details, evaluation criteria, and relevant documentation.
2. Once the pull request is merged, start a discussion in the [community](https://community.axelar.network/) with a link to the proposal to facilitate community discussion. 
    - **Duration**: Minimum of two weeks.
    - **Activities**: Community members review and discuss the proposal. Proposers engage with the community to address questions and feedback. Chain Integrator to update the proposal to reflect community feedback and address concerns.
3. Security Advisory Committee to initiate review
    - Chain Integrators are required to post a $[ ] bond in AXL-equivalent, secured in a multi-sig [wallet](./SECURITY_ADVISORY_MEMBERS.md#multisig-wallet) managed by the Committee
    - Chain Integrator to notify the Committee of the pledged amount (e.g. by submitting an Axelarscan link of the pledge)
    - Review will be posted in this Github repository in the same working directory as the chain's proposal, with a link posted to the community forum.
    - The bond will be released to the Committee for their review efforts according to this [mechanism](SECURITY_ADVISORY_MEMBERS.md#compensation)
4. Governance Proposals
    - With the security review under way, the Chain Integrator can put forward a governance proposal
        - Governance proposal examples are [here](https://docs.axelar.dev/dev/amplifier/chain-integration/governance-proposals/)
5. Ongoing concerns
    - [The chain's performance, underlying security, and overall activity will be monitored on a go-forwarded basis by the Committee]

## Evaluation Criteria

**Verifier Set Scrutiny:** For connections relying on an external validation model, a connection's security is closely tied to its verifier set's size and decentralization. We emphasize the importance of a robust verifier set, offering guidance for integrating connections that utilize economic or non-economic security mechanisms to achieve sufficient decentralization.

**Technological Assessment:** The committee examines the underlying technology of each connection, including the use of advanced cryptographic techniques like light-clients or zero-knowledge proofs, to ensure a solid security model is in place.

**Code Quality and Transparency:** The quality of the code, its public availability, documentation, and the results of independent audits are all crucial factors in the evaluation process. These elements help assess the reliability and maintainability of the connection.

**Deployment and Maintenance Plans:** The lifecycle of a connection, from its initial deployment to ongoing maintenance, is reviewed to ensure there is a comprehensive plan for addressing updates, bugs, and upgrades within the ecosystem.