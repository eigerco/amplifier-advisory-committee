# **Threat Model for Amplifier Protocol**

## **Overview**

The Amplifier protocol enables seamless interoperability between blockchains with different consensus mechanisms and execution models. Its decentralized, programmable architecture allows for universal communication between blockchains via General Message Passing (GMP). This threat model identifies potential security risks, vulnerabilities, and mitigation strategies for each component, ensuring the secure integration of external chains into the Axelar network.

---

## **1. Amplifier Contracts**

- **Assumption**: Contract admins are currently controlled via a multi-signature mechanism, with Axelar governance overseeing contract uploads. Admins can invoke emergency mechanisms (e.g., freezing connections) as needed.
- **Threat**: If the multi-signature account or governance is compromised, emergency functions may be abused.
- **Mitigation**: Axelar governance retains ultimate control, and any misuse of powers can be overridden by governance votes.

### **1.1 Verifier Contracts**
- **Assumption**: 
- **Attack Surface**: 
- **Mitigation**: 

### **1.2 Prover Contracts**
- **Assumption**: The prover generates a proof, and the external gateway verifies it 
- **Threat**: Vulnerabilities in proof verification could lead to incorrect validation of cross-chain messages.
- **Attack Surface**: Malicious actors could manipulate cryptographic proofs to bypass verification checks.
- **Mitigation**: Use well-established cryptographic libraries, conduct regular audits, and apply formal verification of cryptographic logic.

### **1.3 Gateway Contracts**
- **Assumption**: Gateway contracts are deployed on external chains to facilitate cross-chain transactions, acting as entry and exit points. They interact with the verifier contract and relayers to route cross-chain messages.
- **Threat**: Unauthorized message routing or transaction tampering at the gateway level.
- **Attack Surface**: Gateways managing cross-chain messages could be targeted for unauthorized access or logical vulnerabilities.
- **Mitigation**: Implement strict input validation, replay protection mechanisms, and audit non-reentrant logic. Emergency mechanisms, such as freezing connections, provide damage control.

---

## **2. External Chain Contracts**

### **2.1 External Chain Gateway Contracts**

- **Threat**: Gateway contracts on connected chains may contain vulnerabilities that allow malicious transactions, disrupt message integrity, or allow replay attacks.
- **Attack Surface**: External chains with weaker security assumptions could expose the protocol to cross-chain risks.
- **Mitigation**: External chains must meet predefined security criteria before integration. Verifiable cryptographic proofs are required for all messages passed between chains.

### **2.2 App Contracts (e.g., Interchain Token Standard - ITS)**

- **Threat**: Vulnerabilities in app contracts may lead to manipulation of token balances or cross-chain transactions.
- **Attack Surface**: Application-level contracts, such as ITS, could allow malicious withdrawals exceeding deposited amounts.
- **Mitigation**: Implement balance-limiting mechanisms and conduct frequent auditing of token-related logic.

---

## **3. Axelar Network**

- **Assumption**: Axelar governance is trusted. If governance is compromised, both the Amplifier protocol and the entire Axelar network could be affected.
- **Threat**: A governance attack may lead to malicious upgrades or changes to the protocol.
- **Attack Surface**: Compromised validators, relayers, or governance structures may introduce network-wide vulnerabilities.
- **Mitigation**: Strong governance policies, decentralized decision-making, and multi-signature mechanisms protect governance from hostile takeovers. Validator accountability and slashing mechanisms deter malicious behavior.

---

## **4. Verifiers**

- **Assumption**: A majority of verifiers are honest. The threshold for this is defined by the voter/prover contract parameters.
- **Threat**: If the majority of verifiers are compromised, malicious transactions may be approved.
- **Attack Surface**: Majority verifier attacks could result in unauthorized cross-chain message approvals.
- **Mitigation**: Use multi-signature schemes and quorum-based validation to reduce the risk of verifier collusion.

---

## **5. Cryptographic Primitives**

- **Threat**: Cryptographic failures may allow message forgery or unauthorized transactions.
- **Attack Surface**: Weak cryptographic primitives or flawed implementations could be exploited.
- **Mitigation**: Use battle-tested cryptographic libraries and apply formal verification of cryptographic proofs to ensure security.

---

## **6. Relayers**
- **Assumption**: Relayers only need to guarantee liveness, not security. Liveness relies on the availability of at least one honest relayer.
- **Threat**: Relayers could delay messages, affecting liveness but not the security of the protocol.
- **Attack Surface**: Delayed messages could disrupt cross-chain operations.
- **Mitigation**: Relayers are permissionless, ensuring that any party, including users, can relay messages. The availability of at least one honest relayer ensures the system’s liveness.

---

## **Risk Assessment and Summary**

| Threat                       | Likelihood | Impact  |
|-------------------------------|------------|---------|
| Governance Compromise          | Low        | Critical|
| Verifier Majority Attack       | Low        | High    |
| Relayer Censorship             | Medium     | Medium  |
| Replay Attacks                 | Low        | Medium  |
| Insert Logical Contract Bug 1  | Low        | Medium  |
| Insert Logical Contract Bug 2  | Low        | Medium  |
---
