# Chain Integration Proposal

## Overview

### Project Overview

- **Chain Name:** Flow
- **Project Description:** Flow is a Layer 1 blockchain built specifically for creating and managing digital assets and decentralized applications (dApps). It features a unique multi-node architecture designed for scalability without compromising decentralization, enabling fast, secure, and efficient execution of smart contracts. Flow is purpose-built for high-throughput use cases such as gaming, NFTs, and consumer applications.
- **Proposer:** Flow Foundation
- **Contact Information:**
  - **Email:** developers@flow.com
  - **Telegram:** @FlowCommunity

### Chain Overview

#### At-A-Glance

- **Justification for Flow:** Integrating Flow with the Axelar network will extend Flow’s interoperability capabilities across its diverse and growing set of use cases.
- **Management Team Credentials:** Flow is developed by Dapper Labs, the team behind CryptoKitties and NBA Top Shot. The team is composed of seasoned professionals in blockchain technology, cryptography, and application development, with deep experience in building scalable and user-friendly blockchain platforms.
- **Notable Use Cases:** Flow is a developer-friendly platform ideal for building and scaling Web3 apps across gaming, NFT, and defi use cases. Examples include:
  - **NBA Top Shot:** A marketplace for officially licensed NBA digital collectibles, where users can buy, sell, and trade NBA highlights as NFTs.
  - **Chainmonsters:** A massively multiplayer online RPG built on Flow, where players can catch, train, and trade digital creatures.
  - **MotoGP™ Ignition:** A digital collectibles platform for MotoGP fans, featuring officially licensed content from the world of motorcycle racing.

#### Technology Overview

- **Protocol Overview:** 
    Flow’s architecture is based on a unique multi-node design that separates the roles of consensus, verification, execution, and collection. This approach allows Flow to achieve high throughput and low latency, making it suitable for consumer-scale applications.

    The Flow network uses Cadence as its main execution environment. Cadence offers a safe, efficient, and developer-friendly experience for building smart contracts and decentralized applications. 

    EVM on Flow is designed with these major goals in mind:

    Supporting EVM equivalency: Ensure that any tools and applications deployed to or run on Ethereum can also be deployed and run on Flow.
    Minimizing breaking changes to the Cadence ecosystem, software and tools
    Maximum composability across environments: Allowing atomic and smooth interaction between EVM and Cadence environments.

- **Transaction Finality:** 
    Flow offers instant, deterministic finality, meaning that once a transaction is confirmed by the network, it is final and cannot be reversed. This ensures a secure environment for applications where quick and definitive transaction processing is critical.
- **Smart Contract Platform:** 
    Through the Crescendo upgrade, EVM on Flow is fully EVM-Compatible. With Flow offering full EVM support, existing applications and tools already deployed in the EVM ecosystem can simply onboard to the network with no code changes.
- **Additional Notable Features:**
  - **Cadence:** A resource-oriented programming language developed by Flow for writing secure and easy-to-understand smart contracts. Cadence is designed to prevent many of the vulnerabilities that exist in other smart contract languages.
  - **Upgradable Smart Contracts:** Flow allows developers to deploy smart contracts that can be updated or fixed after deployment, providing flexibility while maintaining security.
  - **Developer Tools:** Flow provides a rich set of tools and resources, including the Flow CLI, Flow Emulator, and Flow Playground, which make it easier for developers to build, test, and deploy dApps on the Flow blockchain.

#### Security Considerations

- Flow has been rigorously audited by third-party security firms to ensure the robustness and security of its protocol. The unique multi-node architecture reduces attack vectors by decentralizing transaction processing. Flow also uses Cadence, a language designed with security in mind, to further minimize risks associated with smart contracts. Continuous monitoring and a proactive approach to security ensure that any vulnerabilities are addressed promptly.

### Axelar Integration Components

- **External Gateway Contracts:** Because Flow is fully EVM-compatible, the Axelar integration for the Flow gateway contracts are those found here: https://github.com/axelarnetwork/axelar-gmp-sdk-solidity/blob/main/contracts/gateway/INTEGRATION.md. These contracts were developed by the Interop Labs team and fully audited.
- **Amplifier Contracts:** Similarly, the Amplifier contracts (Gateway, Voting Verifier, Multisig Prover) on the Axelar Virtual machine are those developed by the Interop Labs team, which can be found here: https://github.com/axelarnetwork/axelar-amplifier/tree/main/contracts

## Request for Security Council Review

### Purpose

The purpose of this review is to ensure that the integration of Flow with the Axelar network adheres to all security and technical standards, ensuring a secure and efficient connection.

### Additional Information

- **GitHub Repository:** https://github.com/onflow
- **Developer Documentation:** https://developers.flow.com/
- **Whitepaper:** https://flow.com/technical-paper
- **Independent Audit Reports:** [Insert Link to any audit reports]

## Community Involvement

### Discussion Forum

Community members are encouraged to participate in the discussion and provide feedback on this proposal through the Axelar community forum. [Insert Link to Forum]

### Voting

Following the Security Council's review, a community vote will be held to determine the approval of Flow's integration with the Axelar network.

### Feedback and Questions

For any questions or feedback regarding this proposal, please contact the Flow Development Team at developers@flow.com or via Telegram at @FlowCommunity.
