# Chain Integration Proposal

## Overview

### Project Overview

- **Chain Name:** Hedera EVM
- **Project Description:** Hedera is a public distributed ledger that uses the unique Hashgraph consensus algorithm to offer a fast, fair, and secure platform for creating and running decentralized applications (dApps). It’s designed for enterprises and large-scale applications, featuring high throughput, low latency, and a high degree of security. Hedera aims to provide a stable and trusted infrastructure for industries such as finance, healthcare, and supply chain management.

- **Proposer:** Hedera Hashgraph
- **Contact Information:**
  - **Email:** ___@hedera.com
  - **Telegram:** @hederahashgraph
  - **Website:** https://hedera.com/

### Chain Overview

#### At-A-Glance

- **Justification for Hedera:** Integrating Hedera with the Axelar network will significantly expand Hedera's interoperability, allowing its ecosystem to seamlessly connect with other blockchain networks. This integration will facilitate cross-chain communication and asset transfers, enhancing the utility of dApps and services built on Hedera.
- **Management Team Credentials:** Hedera is governed by the Hedera Governing Council, comprising a diverse group of global enterprises, universities, and non-profits, including Google, IBM, and Boeing. The council ensures the network’s decentralized governance and decision-making. The team behind Hedera includes Dr. Leemon Baird, co-founder and Chief Scientist, who invented the Hashgraph consensus algorithm, and Mance Harmon, co-founder and CEO, who has extensive experience in technology and cybersecurity.
- **Notable Use Cases:** Hedera supports a variety of use cases across multiple industries, such as:
  - **Avery Dennison:** Uses Hedera for real-time supply chain transparency and product authentication.
  - **ServiceNow:** Integrates Hedera for verifiable and tamper-proof records within its digital workflows.
  - **Standard Bank:** Employs Hedera for cross-border payments and efficient tokenization of assets.

#### Technology Overview

- **Protocol Overview:** 
Hedera is built on the Hashgraph consensus algorithm, a form of distributed consensus that provides high throughput (over 10,000 transactions per second), low latency, and security through asynchronous Byzantine Fault Tolerance (aBFT). The Hashgraph algorithm uses a "gossip about gossip" protocol and virtual voting to achieve consensus rapidly and fairly.
- **Smart Contract Platform:** 
Hedera supports Solidity-based smart contracts with its Hedera Smart Contract Service. The network is now EVM-compatible, enabling developers to deploy Ethereum-based dApps on Hedera without modification. This EVM support allows for seamless interoperability with Ethereum tools and applications, maximizing the composability within the ecosystem.
- **Transaction Finality:** 
    Hedera provides deterministic finality with transactions being finalized within 3-5 seconds, ensuring immutability and reducing the risk of double-spending or rollbacks. This quick finality is ideal for applications that require fast and secure transaction processing.
- **Additional Notable Features:**
  - **Hedera Token Service (HTS):** Enables the creation, management, and transfer of native fungible and non-fungible tokens (NFTs) with low fees and high throughput.
  - **Hedera Consensus Service (HCS):** Offers a decentralized and tamper-proof log for tracking and ordering events, providing transparency for applications requiring auditability.
  - **Developer Tools:** Hedera offers a range of tools including the Hedera SDKs (Java, JavaScript, Go), Hedera Testnet, and extensive documentation to support developers in building, testing, and deploying dApps on Hedera.

#### Security Considerations

  - **Security Model:** Hedera's security model is based on the Hashgraph consensus algorithm, which is designed to be resilient to DDoS attacks and other malicious activities. The network has been independently audited, and the Hedera Governing Council provides a transparent and decentralized approach to network governance. Hedera’s asynchronous Byzantine Fault Tolerance ensures that even in the presence of malicious nodes, the network can still achieve consensus securely. Additionally, Hedera employs continuous monitoring and has implemented a bug bounty program to proactively identify and mitigate potential security risks.
  - **Hedera Governing Council:** The Hedera Governing Council is a diverse group of global organizations that govern the Hedera network, contributing to its stability and decentralization. The council includes prominent companies and institutions across various sectors, such as:
  - Google
  - IBM
  - Boeing
  - LG Electronics
  - Deutsche Telekom
  - Tata Communications
  - University College London (UCL)
  - Shinhan Bank
  - Nomura
  
The council members are responsible for making key decisions about the network, including its roadmap, network rules, and policies, ensuring a decentralized and transparent governance model.

### Axelar Integration Components

- **External Gateway Contracts:** With Hedera's EVM compatibility, the Axelar integration will leverage the standard gateway contracts available at Axelar's GitHub Repository. These contracts have been developed and thoroughly audited by the Interop Labs team to ensure secure and reliable cross-chain operations.

- **Amplifier Contracts:** The integration will also utilize the Amplifier contracts (Gateway, Voting Verifier, Multisig Prover) on the Axelar Virtual Machine, as provided here. These components facilitate efficient communication between Hedera and other networks supported by Axelar.

## Request for Security Council Review

### Purpose

The goal of this review is to validate the security and technical compliance of integrating Hedera with the Axelar network, ensuring a robust and secure interoperability solution.

### Additional Information

- **GitHub Repository:** https://github.com/hashgraph
- **Developer Documentation:** https://docs.hedera.com/hedera
- **Whitepaper:** https://hedera.com/papers
- **Independent Audit Reports:** https://hedera.com/audits-and-standards

## Community Involvement

### Discussion Forum

Community members are encouraged to participate in the discussion and provide feedback on this proposal through the Axelar community forum. [Insert Link to Forum]

### Voting

Following the Security Council's review, a community vote will be held to determine the approval of Flow's integration with the Axelar network.

### Feedback and Questions

For any questions or feedback regarding this proposal, please contact the Flow Development Team at support@hedera.com or via Telegram at @hederahashgraph.

