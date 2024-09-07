## Evaluation Criteria

- **Technological Assessment:** The committee examines the underlying technology of each connection, including the use of advanced cryptographic techniques like light-clients or zero-knowledge proofs, to ensure a solid security model is in place.

- **Code Quality and Transparency:** The quality of the code, its public availability, documentation, and the results of independent audits are all crucial factors in the evaluation process. These elements help assess the reliability and maintainability of the connection.

- **Deployment and Maintenance Plans:** The lifecycle of a connection, from its initial deployment to ongoing maintenance, is reviewed to ensure there is a comprehensive plan for addressing updates, bugs, and upgrades within the ecosystem.

## Committee Grants

The Committee may receive grants for their role in contributing to the technical and security review and report, with the grant amount reflecting the complexity of the integration. This can range from standard EVM-compatible chains to highly complex and nuanced blockchain designs, ensuring that compensation aligns with the scope and demands of the project.

| Integration Type | Complexity Level | Incentive Amount |
| --- | --- | --- |
| EVM Compatible Chains | Low | up to $10,000 |
| Less Common L1 Chains | Medium | up to $20,000 |
| Custom L1 Chains | High | up to $30,000 |
| Novel Blockchain Designs | Very High | up to $40,000+ |

### EVM Compatible Chains:

- **Description:** These are chains that are compatible with the Ethereum Virtual Machine (EVM), meaning they share a common execution environment with Ethereum. Typically, EVM compatible integrations involve around 5 standard contracts.
- **Grant:** The grant may be up to $10,000 to cover the full expected cost of auditing all necessary contracts. This amount is derived from an analysis of the average audit costs associated with EVM connections into Amplifier.
- **Justification:** The minimum expected cost to audit the standard contracts needed for an EVM connection is around $10,000. The review process for these chains is generally straightforward due to the familiarity and extensive existing knowledge of EVM operations. Tools and procedures for auditing these chains are well-established, reducing the resources needed for a comprehensive review. As the Security Council's role is akin to a technical business audit, it is priced similarly.

### Medium Complexity (Less Common L1 Chains):

- **Description:** This category includes Layer 1 chains that do not use EVM but are still somewhat similar to other well-known blockchains in terms of architecture and functionality.
- **Grant:** The grant may be up to $20,000 to cover the full expected cost of auditing these integrations. This amount is derived from an analysis of the average audit costs for such chains.
- **Justification:** These integrations generally involve more than 5 contracts, which may include custom components. The total estimated cost for these audits is about $20,000, reflecting the increased complexity and additional expertise required.

### High Complexity (Custom L1 Chains):

- **Description:** Custom L1 chains often feature unique architectures and may introduce novel consensus mechanisms or other fundamental changes not present in more standardized blockchains.
- **Grant:** The grant may be up to $30,000 to cover the full expected cost of auditing these integrations. This amount is derived from an analysis of the average audit costs for such chains.
- **Justification:** Custom L1 integrations often require in-depth reviews of many contracts and components, each potentially requiring custom analysis. The total audit costs are typically around $30,000, accounting for the unique technologies and potentially innovative security challenges presented.

### Very High Complexity (Novel Blockchain Designs):

- **Description:** This category includes innovative blockchain designs that deviate significantly from traditional blockchain architectures, potentially introducing radical new approaches to scalability, security, or consensus.
- **Grant:** The grant may be up to $40,000 or more to cover the full expected cost of auditing these integrations. This amount is derived from an analysis of the average audit costs for such designs.
- **Justification:** These projects might involve extensive audits of many contracts and components, featuring radically new designs and technologies. Given the complexity and the pioneering nature of these designs, audit costs can exceed $40,000. This incentive reflects the high level of technical expertise, time investment, and risk associated with auditing these innovative projects.
