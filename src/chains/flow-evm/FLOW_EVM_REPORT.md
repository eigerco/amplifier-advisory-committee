# Report on Flow EVM

## Project Overview

- **Chain Name**: Flow  
- **Proposal Reviewed**: [Flow Github Proposal](PROPOSAL.md)

### Table of Contents
  #### [Section 1: Assessment Methodology](#section-1-assessment-methodology-1)
  #### [Section 2: Network and Protocol Integrity](#section-2-network-and-protocol-integrity-1)
  #### [Section 3: Security and Risks](#section-3-security-and-risks-1)
  #### [Section 4: Axelar Integration Components](#section-4-axelar-integration-components-1)
  #### [Conclusion](#conclusion-1)
---

## Section 1: Assessment Methodology

### 1.1 Integration Overview

Flow’s EVM integration to Axelar Amplifier aims to facilitate seamless cross-chain interoperability, leveraging Axelar's General Message Passing (GMP) protocol. This integration provides Flow developers access to broader liquidity pools and decentralized applications (dApps) on other networks.

### 1.2 Evaluation Approach

The Committee’s assessment methodology consisted of these elements:

- **Research and Documentation Review**: The committee reviewed technical documentation, reports, whitepapers, GitHub repositories, and Flow Improvement Proposals (FLIPs) related to the EVM integration and other related topics.  
- **Security Audits and Testing**: The codebases and audits were reviewed for vulnerabilities, and key components were tested for compliance with best practices and security standards.
- **Collaboration with the Flow Team**: The committee worked closely with the Flow team to understand the Amplifier deployment and maintenance plans. This included reviewing their incident response protocols, upgrade procedures, and amplifier integration components.

### 1.3 Assessment Framework

- **Protocol Integrity**:  Focused on Flow’s consensus mechanism (Jolteon, a variant of HotStuff), validator decentralization, and the structural integrity of the multi-role architecture.  
- **Security Risks**: Evaluation of potential exploits in Flow’s infrastructure, security audits for the EVM bridge, and the handling of smart contract vulnerabilities.  
- **Operational Risks**: Potential risks for developers using Flow’s EVM integration, including challenges related to stability, smart contract language constraints, network halts, and untested components of Flow's upgrades like the Crescendo initiative.  
- **Compliance & Governance Risks**: Determine if the protocol team, members, or other stakeholders are under investigation or facing legal action. Additionally, conduct a review of Flow's governance framework (FLIPs) and its ability to address regulatory compliance issues.  
- **Code Quality and Transparency**: A detailed examination of the codebase for quality, including audit reports, documentation, and adherence to best practices. Transparency in the development process and open-source contribution practices were also considered.  
- **Integration Plan**: A thorough review of Flow’s deployment and maintenance strategies for the Amplifier integration. This includes evaluating ongoing monitoring systems, incident response plans, data collection protocols, and external threat detection mechanisms.

### 1.4 Assessment Criteria

Desirable properties for a protocol’s architecture include:

- **Security**: Protection against exploits (e.g., cryptographic guarantees, consensus resilience).  
- **Scalability and Performance**: Handling increasing load and transaction throughput.  
- **Decentralization**: Distribution of control across validators and participants.  
- **Governance**: Mechanisms for upgrades, decision-making, and dispute resolution.  
- **Fault Tolerance**: Ability to recover from failures without affecting the system.  
- **Transparency**: Openness of the codebase, team, and audit results.

---

## Section 2: Network and Protocol Integrity

### 2.1 Network Architecture

Flow is a Layer-1 Proof-of-Stake (PoS) network developed by [Dapper Labs](url) to facilitate a wide range of applications, including gaming, NFTs, and digital assets. Its multi-role architecture splits traditional validator roles into four types: Collection, Consensus, Execution, and Verification nodes, enhancing scalability and security. 

Flow uses a variant of the [Jolteon Byzantine Fault Tolerant (BFT)](https://flow.com/engineering-blogs/jolteon-advancing-flows-consensus-algorithm) consensus algorithm, a flavor of [Hotstuff](https://arxiv.org/pdf/1803.05069).

Each node has strict staking requirements and operates within Flow’s permission system, maintaining high standards for security and integrity. Flow’s upgrade to [Cadence 1.0](https://flow.com/upgrade/crescendo/cadence-1) through the Crescendo initiative introduced EVM equivalency, allowing developers to leverage Ethereum tooling on Flow.

The EVM equivalence components are described in their respective FLIPs: [FLIP223 EVM Core](https://github.com/onflow/flips/blob/main/protocol/20231116-evm-support.md), [FLIP237 Flow VM Bridge](https://github.com/onflow/flips/blob/main/application/20231222-evm-vm-bridge.md), and FLIP235 EVM Gateway (unmerged). The source code and tests are open source: [EVM Core](https://github.com/onflow/flow-go/tree/master/fvm/evm), [Flow VM Bridge](https://github.com/onflow/flow-evm-bridge), and [EVM Gateway](https://github.com/onflow/flow-evm-bridge). The Flow VM Bridge has been audited by [Quantstamp](https://quantstamp.com/). The remaining components of the EVM have not been audited.

- **Multi-Role Architecture:**
   - Consensus Nodes determine the inclusion and sequencing of transactions on the blockchain, requiring a minimum stake of 500,000 FLOW (~$285,000 USD at the current price of $0.57).
   - Verification Nodes ensure the accuracy of computations performed by Execution Nodes, requiring a minimum stake of 135,000 FLOW (~$76,950 USD).
   - Execution Nodes handle the processing and execution of each transaction's computations, requiring a minimum stake of 1.25 million FLOW (~$712,500 USD).
   - Collection Nodes improve network connectivity and ensure data availability for decentralized applications (dapps), requiring a minimum stake of 250,000 FLOW (~$142,500).
- *The current price of the FLOW token is $0.57, with a yearly high of $1.64 and a low of $0.50. All the USD amounts above use $0.57, the price of FLOW on September 20, 2024.*

Consensus, Verification, and Collection nodes are more decentralized than Execution nodes. Since Execution nodes perform deterministic tasks, they require less decentralization. Additionally, Execution nodes rely on high-performance hardware, which emphasizes scalability over decentralization. Flow currently operates with approximately [451 nodes](https://www.flowdiver.io/). The total number of staked assets on Flow is approximately 713.2M FLOW (46.5% of total assets) with [Coinbase](https://www.coinbase.com/en-gb/), [Dapper Labs](https://www.dapperlabs.com/), and the[ Flow Foundation](https://flow.com/flow-foundation) operating a significant portion of the network's staked assets (approx. 35% of the total staked assets). *(713.2M FLow is equal to $406.52 million as of September 20, 2024)*.

Flow’s protocol integrity is overseen by a highly experienced team led by [Dapper Labs](https://www.dapperlabs.com/), known for their work on NBA Top Shot and pioneering NFT standards. The Flow team is well-funded and includes experts in blockchain technology. The team actively maintains and upgrades the network’s core infrastructure, ensuring robust security, scalability, and performance.

### 2.2 Governance and Compliance

Flow operates on an off-chain governance model using Flow Improvement Proposals (FLIPs), which are voted on by staked FLOW token holders. Governance decisions involve the Flow Review Committee, which can be overridden through majority community consensus. Token holders can participate in the governance process by staking their FLOW to submit and vote on FLIPs​.

Despite Flow’s governance structure, regulatory compliance has been scrutinized. For example, the U.S. SEC investigated Coinbase, with allegations that [FLOW might be considered a security](https://www.sec.gov/files/litigation/complaints/2023/comp-pr2023-102.pdf). Furthermore, [Dapper Labs](https://www.dapperlabs.com/) has faced class-action lawsuits regarding NBA Top Shot:

- **October 2021**: Dapper Labs was [accused](https://www.classaction.org/media/fan-v-nba-properties-inc-et-al.pdf) of violating the Video Privacy Protect Act (VPPA) by collecting and sharing sensitive video consumption data of basketball fans without consent. The case is ongoing as of June 2024.
- **May 2021**: A [class action lawsuit](https://www.dandodiary.com/wp-content/uploads/sites/893/2021/06/Dapper-Labs-lawsuit-complaint.pdf) accused Dapper Labs and Roham Gharegozlou of selling NBA Top Shot Moments as unregistered securities, violating federal laws. A $4 million settlement was reached in June 2024. 

---

## Section 3: Security and Risks

### 3.1 Smart Contracts Security and Vulnerability

Flow's native smart contract language, [Cadence](https://cadence-lang.org/docs/language), was built for safety and usability. It incorporates resource-oriented programming, minimizing common vulnerabilities like reentrancy attacks, a frequent issue in Solidity-based contracts. 

Flow's smart contract testing coverage varies depending on the component being tested. For example, the Flow-Go repository, which handles consensus and node implementation, employs comprehensive unit and integration tests to ensure its components are robust and secure​ ([GitHub](https://github.com/onflow/flow-go))​([Go Packages](https://pkg.go.dev/github.com/onflow/flow-go)). Additionally, testing best practices for Cadence smart contracts include using the `--cover` flag during tests to track coverage, aiming for high percentages, often over 90% for critical components. This allows developers to identify which parts of the code are well-covered and which require more testing​ ([Flow Dev Portal](https://developers.flow.com/build/smart-contracts/testing)).

For Axelar’s integration with Flow, Flow EVM is required to be stable without issues in testnet for at least 1 week, while non-EVM chains must remain stable for 2 weeks. Additionally, contracts that involve token deployment are not released until at least 1 week after the mainnet release, ensuring additional caution and stability during the onboarding process.

Flow does not impose a strict minimum requirement or enforce a mandatory review period length for smart contracts. However, the platform encourages developers to use the review period as a security best practice. While the specific length of the review period is left to the discretion of the developer, it is recommended to use a period that allows sufficient time for thorough testing, monitoring, and potential community feedback. In general, the Flow team advises using the review period for critical contracts, particularly those involving significant assets or high-risk functionalities. This process ensures developers can address issues before a contract becomes immutable. However, Flow does not provide an official minimum duration—it’s up to the developer to decide based on their specific needs and risk profile.

However, Flow experienced network halts prior to the Crescendo Upgrade due to security bugs in its node operations. Three notable instances of Flow being halted include:

- **June 2022**: "Sealing halt" which caused the network to pause. Block production resumed, and the mainnet was restarted approximately five hours later. 
- **October 2021**: "Consensus finalization issue" led to another network halt, which was resolved within two hours.
- **January 2021**: Network halted due to a "consensus node safety mechanism" being triggered. [Dapper Labs](https://www.dapperlabs.com/) corrected the issue by removing the erroneous execution result, enabling the network to resume within an hour.

There have also been several instances in which Flow was impacted by performance issues, including Access Node outage, Execution Node instability, an epoch transition failure that led to an [emergency spork](https://forum.flow.com/t/emergency-mainnet-spork-on-2023-02-22/4325),  [cluster finalization degradation](https://forum.flow.com/t/flow-node-operatores-please-add-the-flag-gossipsub-peer-scoring-enabled-false/5419), and an [epoch fallback](https://forum.flow.com/t/flow-mainnet-is-in-the-epoch-fallback-mode/5283). 

Additionally, Halborn [discovered vulnerabilities](https://www.halborn.com/disclosures/halborn-cadence-flow-vulnerability-discovery) related to Flow's Cadence, including logic errors in the resource management model that could lead to denial-of-service (DoS) attacks​. Flow addresses these vulnerabilities promptly, though some issues may persist depending on network conditions or software bugs, as demonstrated by past network halts.

Flow has engaged with third-party auditors, including **Quantstamp**, **Halborn**, **NCC Group**, **Oak Security**, and others, which conducted multiple audits focusing on core smart contracts, staking, and token vesting.
- [Quantstamp Flow VM Bridge Audit](https://certificate.quantstamp.com/full/flow-foundation-cross-vm-token-bridge/77244753-4ef5-4ecd-b936-a0b38d3c2dfd/index.html)
- [Quantstamp Epoch Functionality Audit](https://certificate.quantstamp.com/full/epoch-functionality-contracts.pdf)
- [Quantstamp Hotstuff Audit](https://certificate.quantstamp.com/full/hot-stuff/fb01273d-6f99-4f98-a9db-fdfab636d2d9/index.html)
- [Oak Security Audit](https://github.com/oak-security/audit-reports/blob/master/Dapper%20Labs/Audit%20Report%20-%20Hybrid%20Custody%20Smart%20Contracts.pdf)


### 3.2 Risks and Concerns

Flow minimizes risks for developers and users by utilizing [Cadence](https://cadence-lang.org/docs/language), a resource-oriented smart contract programming language designed for safety and efficiency. Cadence features a strong static-type system and guarantees resource management, helping developers avoid common vulnerabilities such as reentrancy attacks. This makes writing, testing, and deploying contracts more secure and predictable, significantly reducing the risk of bugs and vulnerabilities. The language supports easy contract upgrades, offering a more flexible and reliable development environment compared to traditional blockchains like [Ethereum](https://ethereum.org/en/)​. Additionally, developers can leverage EVM smart contract languages like Solidity, further broadening their development options and compatibility.

For users, Flow offers a major advantage with its low gas fees. Transactions on Flow are designed to be cost-effective, which is especially beneficial for applications involving high volumes of interactions, such as gaming or NFTs. Low gas costs enhance the user experience by making frequent transactions more affordable without sacrificing the network security and performance.

The Flow team has shared a detailed list of [best practices for Cadence developers](https://github.com/HalbornSecurity/Security-Best-Practices-for-Cadence-Developers-Flow-) to ensure security and efficiency in smart contract development. These guidelines cover common security considerations and optimisations for developers using Cadence. The team has made available the audits of both the Cadence smart contract language and the Flow Virtual Machine (FVM), providing further assurance of the platform's reliability and safety. 

Additional notable considerations worth bringing up to the Axelar community:
- The Jolteon consensus protocol that Flow relies on is a variant of [HotStuff](https://arxiv.org/pdf/1803.05069) that originated from Facebook’s Diem project. Its correctness was formally proven in the DiemBFT v4: [State Machine Replication in the Diem Blockchain](https://developers.diem.com/papers/diem-consensus-state-machine-replication-in-the-diem-blockchain/2021-08-17.pdf) paper. A more concise description of the consensus algorithm with some performance optimizations was formalized in the [Jolteon and Ditto: Network-Adaptive Efficient Consensus with Asynchronous Fallback](https://arxiv.org/pdf/2106.10362) paper. Jolteon and Ditto includes rigorous safety and liveness proofs and was [published](https://link.springer.com/chapter/10.1007/978-3-031-18283-9_14) to a peer-reviewed conference (Financial Cryptography 2022). Flow implements the Jolteon protocol with some performance optimizations. Jolteon’s security proofs should carry over, but the Flow team has [written their own rigorous safety and liveness proofs](https://www.notion.so/flowfoundation/Architecture-for-Active-PaceMaker-59a0f90a3a584cd3a4cd67420898b11e?pvs=4), which have not been peer-reviewed. Flow’s main consensus innovation is their concurrent processing of consensus votes using multiple cores. Flow has written [safety and liveness proofs](https://www.notion.so/flowfoundation/Architecture-for-Concurrent-Vote-Processing-41704666bc414a03869b70ba1043605f?pvs=4) for their concurrent vote processing (also not peer-reviewed).
- Quantstamp has performed an audit of Flow’s implementation of the vanilla HotStuff consensus algorithm ([Quantstamp Hotstuff Audit](https://certificate.quantstamp.com/full/hot-stuff/fb01273d-6f99-4f98-a9db-fdfab636d2d9/index.html)). The additional components that Jolteon introduces (i.e., mainly the pacemaker component for active coordination of timeouts in the consensus committee) have not been audited.
- Flow’s recent Crescendo upgrade enabled EVM equivalence, by introducing some heavy and complex machinery. These new components have not been audited.
- The EVM equivalence introduced in the Crescendo upgrade results in liquidity fragmentation between the EVM layer and the Cadence layer. EVM tokens need to be bridged to the EVM side via the VM bridge, as wrapped Cadence tokens, and vice versa.


---

## Section 4: Axelar Integration Components

The Flow integration deploys the EVM contracts as-is. No Flow-specific features are used, and EVM compatibility is tested through Axelar integration tests and reviewing Flow documentation. The Axelar Amplifier Gateway is open-source on [GitHub](https://github.com/axelarnetwork/axelar-amplifier) and security audits were performed by [Ackee Blockchain](https://github.com/axelarnetwork/audits/blob/main/audits/2024-07%20Ackee%20Blockchain.pdf) (7/2024), [Hallborn](https://github.com/axelarnetwork/audits/blob/main/audits/2024-05%20Halborn.pdf) (5/2024), and [NCC](https://github.com/axelarnetwork/audits/blob/main/audits/2024-06%20NCC.pdf) (6/2024).

### 4.1 Code Quality and Transparency

Summary of findings from Amplifier Gateway audits:

| Company         | Critical | High | Medium | Low | Warning | Info |
|-----------------|----------|------|--------|-----|---------|------|
| **Ackee**       | 1-1-0    | 2-1-1| 3-2-1  |     |         |      |
| **Hallborn**    |          | 1-0-1| 4-1-3  |     | 6-0-6   |      |
| **NCC**         |          |      | 2-2-0  |     | 3-3-0   |      |

### 4.2 Deployment and Maintenance Plans

The Amplifier threat model for Flow EVM is derived from the [Amplifier Threat Model](docs/Integrators/AMPLIFIER_THREAT_MODEL.md), and focuses on securing seamless interoperability while mitigating risks associated with cross-chain interactions. Since Axelar directly developed the Flow integration, it assumes responsibility for monitoring contract security for contracts developed by the Axelar team, transaction performance on the Axelar Network, and overall network integration health. Key threats include unauthorized message manipulation, cross-chain replay attacks, and potential vulnerabilities within the smart contract logic.

To address these, Axelar employs high security standards, regular contract audits, and proactive monitoring for irregular transactions. Verifiers and Validators enhance security by independently monitoring network performance, providing decentralised checks to help detect and respond to anomalies quickly. This layered approach ensures a secure and resilient Flow EVM integration within Amplifier’s cross-chain ecosystem.

Axelar oversees monitoring and incident response, focusing on:

- **Real-Time Transaction Monitoring**  
- **Performance Analytics**  
- **Security Alerts**  

**Incident Response Protocol**
In the event of a security incident or performance anomaly within the Amplifier integration, Axelar’s designated response team, in collaboration with committee members, will activate a predefined response framework. The incident response is structured to ensure rapid detection, containment, and mitigation of threats, with clear accountability at each stage:
   
1. **Initial Detection and Alerting:** Monitoring tools and alerting systems will notify relevant stakeholders of any unusual activity or potential security threats.

2. **Assessment and Containment:** Axelar’s incident response team will assess the severity and scope of the threat, enacting containment measures to limit exposure or system degradation.
   
3. **Resolution and Recovery:** The team will coordinate with verifiers and other stakeholders to remediate affected components, validate the resolution, and ensure system stability.
  
4. **Post-Incident Review:** After an incident is resolved, Axelar will conduct a thorough review to identify root causes, implement preventative measures, and enhance monitoring protocols where needed.

The committee serves in an advisory capacity, providing guidance on response protocols and ensuring that the framework aligns with Axelar’s security standards. However, primary responsibility for direct incident handling lies with Axelar’s response team, which coordinates with committee representatives as needed.

**Monitoring and Alerting Responsibilities**
Given Axelar’s role in the direct development and integration of protocols like Flow into Amplifier, Axelar is responsible for implementing and maintaining ongoing monitoring and alerting mechanisms specific to the integration’s contracts, transaction security, and overall performance. This involves:

- **Real-Time Transaction Monitoring:** Axelar monitors cross-chain transactions to detect irregularities in contract execution, latency issues, or security anomalies that may arise.
- **Performance Analytics:** Continuous performance tracking to ensure that the integration operates within expected parameters, providing early warning signals if resource consumption, transaction throughput, or latency exceeds threshold limits.
- **Security Alerts:** Axelar’s monitoring infrastructure includes detection capabilities for potential security threats, including unauthorized access attempts, replay attacks, and contract manipulations.

To supplement Axelar’s internal monitoring efforts, verifiers such as [Node.Monster](https://node.monster/) actively observe network performance, focusing on the Amplifier ecosystem’s broader stability. These verifiers play a crucial role by contributing an additional layer of vigilance, analysing metrics related to node health, message validation, and chain connectivity. Their independent monitoring provides decentralised oversight and helps to identify performance or security issues that might otherwise be missed.

In this capacity, [Node.Monster](https://node.monster/) and the other verifiers act as independent watchdogs, complementing Axelar’s monitoring protocols by offering a decentralised check on system integrity and reliability. Axelar maintains accountability for the ongoing security, performance, and functionality of the Flow integration. 

[Node.Monster](https://node.monster/), as a key member of the committee and an active verifier for the Amplifier integration, plays a critical role in supporting the ongoing monitoring of the Flow EVM integration.


---

## Conclusion

In conclusion, the Committee finds that the Flow EVM integration with Axelar’s Amplifier represents a promising step toward enhancing cross-chain interoperability. The integration grants Flow developers with access to broader liquidity pools and decentralised applications across other networks, leveraging Axelar's General Message Passing (GMP) protocol for seamless cross-chain interoperability.
The Committee highlights areas that require further attention, including:

- **Security audits** for untested EVM components.  
- **Execution node centralization risks**.  
- **Liquidity fragmentation** between EVM and Cadence layers.

The Committee advises the community to continue monitoring the stability and performance of the integration, with a particular focus on addressing unresolved security risks and ensuring transparency in ongoing updates.


---

## Next Steps

- Continue monitoring integration stability and performance.  
- Address unresolved security risks.
- Review new smart contracts such as Flow ITS.

---

## Committee Members

- **Node.Monster**: Technical Assessment  
- **Common Prefix**: Technical Assessment  
- **Ackee**: Code Quality & Assurance Assessment
