# Chain Integration Proposal

## Overview

### Project Overview

**Chain Name:** Sui  
**Project Description:** Sui is a high-performance Layer 1 blockchain designed to power decentralized applications (dApps) with an emphasis on scalability, low latency, and security. Built using the Move programming language, Sui aims to deliver a robust environment for building and deploying complex smart contracts and decentralized finance (DeFi) applications. Its architecture is optimized for high throughput and fast finality, making it ideal for applications requiring quick and efficient transaction processing.  
**Proposer:** Mysten Labs  
**Contact Information**:

* Email: [inga@mystenlabs.com](mailto:inga@mystenlabs.com)  
  * Slack: In Axelar’s Integrator Slack channel tag Inga Agibalova  
  * Discord: [https://discord.com/invite/sui](https://discord.com/invite/sui)  
  * Website: [https://sui.io/](https://sui.io/)

### Chain Overview

#### At-A-Glance

* **Justification for Sui:** Integrating Sui with the Axelar network will significantly enhance interoperability across blockchain ecosystems, creating seamless cross-chain communication and asset transfer capabilities. Sui's unique object-centric data model and Move-based smart contracts, combined with Axelar's secure and scalable infrastructure, provide a strong foundation for building interconnected decentralized applications (dApps) and DeFi protocols. This integration will empower Sui’s ecosystem to access broader liquidity, expand functionality, and facilitate efficient interactions with other blockchains, fostering a more interconnected decentralized economy. As of November 2024, Sui has achieved remarkable milestones, including a total value locked (TVL) of $1.63 billion, 28.4 million active accounts, and 6.7 billion transactions since its Mainnet launch in May 2023\.  
* **Management Team Credentials:** Sui is developed by Mysten Labs, a team composed of seasoned professionals with extensive experience in blockchain technology, distributed systems, and cryptography. The team includes former engineers and researchers from Meta's Novi Research, where they were instrumental in the development of the Diem blockchain and the Move programming language. The leadership team is spearheaded by experts such as:  
  * **Evan Cheng:** Co-Founder and CEO, with a background in programming languages and runtime systems.  
  * **Sam Blackshear:** Co-Founder and Chief Architect, creator of the Move programming language.  
  * **George Danezis:** Co-Founder and Chief Scientist, an expert in privacy, cryptography, and distributed systems and professor at University College London.

**Notable Use Cases:** Sui supports a variety of use cases across multiple industries, such as:

* **RECRD:** A decentralized application on Sui enabling users to create, share, and monetize audio recordings. It leverages Sui's fast and scalable infrastructure to provide seamless experiences for creators and audiences while ensuring secure rights management.  
* **Wave Wallet:** A user-centric wallet designed for Sui, offering easy access to dApps, staking, and asset management. Its intuitive interface and high transaction speeds make it a go-to solution for users engaging in DeFi and NFT ecosystems on the Sui network.  
* **Birds:** A blockchain-based gaming application that utilizes Sui’s high throughput and object-centric model to offer an engaging and interactive gaming experience. Players can collect, trade, and compete using in-game assets securely stored on the blockchain.  
* **FanTV:** A platform integrating streaming and NFT functionalities on Sui, allowing users to interact with exclusive digital content while securely trading digital assets. FanTV uses Sui's low latency and scalability to enhance the streaming experience.  
* **DeFi Protocols:** Sui hosts several DeFi applications, including top-performing protocols like Cetus and Turbos Finance, which boast significant TVL and trading volume. These protocols benefit from Sui's robust transaction finality and secure environment for liquidity provision, lending, and trading.

#### Technology Overview

* **Protocol Overview:** Sui employs an object-centric model, where data is represented as objects rather than accounts. This enhances flexibility and allows for efficient execution of transactions. Sui launched Mainnet with the Narwhal and Tusk consensus mechanism, separating transaction dissemination from consensus to achieve high throughput and scalability. Single-writer transactions benefit from instant finality, while multi-writer transactions are handled with high efficiency. Post Mainnet Sui introduced [Mysticeti](https://sui.io/mysticeti), the most advanced and fastest consensus mechanism of any blockchain.  
* **Smart Contract Platform:** Sui employs the Move programming language, which provides a secure and expressive environment for writing smart contracts. Move's resource-oriented design ensures that assets are only created, transferred, and destroyed in a controlled manner, preventing common vulnerabilities such as double-spending. Sui enhances Move with a focus on composability, enabling developers to create complex interactions between smart contracts and assets.  
* **Transaction Finality:** Sui offers instant finality for most transactions, especially single-writer transactions, which are finalized in under a second. This near-instant finality is critical for applications requiring rapid and irreversible transaction processing, such as in gaming and real-time asset exchanges.  
* **Additional Notable Features:**  
  * **Object-Centric Model:** Sui's unique object-centric data model allows for complex interactions and direct manipulation of objects, making it easier to develop interactive and dynamic dApps.  
  * **Horizontal Scalability:** The network is designed to scale horizontally, handling increased load by adding more nodes to the network without compromising performance.  
  * **Developer Tools:** Sui offers a comprehensive set of developer tools, including the Sui SDK, Sui Explorer, and Sui Playground, to facilitate building, testing, and deploying dApps on the Sui network.  
  *  **ZKLogin:** [ZKLogin](https://sui.io/zklogin) is a native integration mechanism that enables anonymous and private authentication using Google, Apple, or Twitch OAuth credentials. This innovative feature simplifies mass onboarding by allowing users to access Sui's ecosystem seamlessly while maintaining their privacy and security, bridging the gap between traditional Web2 platforms and the decentralized Web3 environment.

#### Security Considerations

* **Security Model:** Sui places a strong emphasis on security, leveraging the [Move programming language's](https://sui.io/move) resource-oriented design to enforce safety properties at the language level. This approach minimizes vulnerabilities by ensuring that assets are managed securely and consistently. Five out of the [OWASP top 10 vulnerabilities](https://owasp.org/www-project-smart-contract-top-10/) are [not possible in Move and 3 are partially mitigated](https://twitter.com/b1ackd0g/status/1749169512866607172?t=5JhAvWnsMPkyPUhPOALvhg&s=19). Classic wallet drainer attacks that exploit contract-level permissions are also [not possible](https://twitter.com/b1ackd0g/status/1747475205243715932?s=20) as all assets are protected by the account’s private key. Smart contract packages are [immutable objects](https://docs.sui.io/concepts/sui-move-concepts/packages#packages-are-immutable), preventing accidental or intentional changes to commonly referenced packages that could have network-wide security implications. Sui's consensus protocol, Mysticeti, is designed to be resilient against various attack vectors, ensuring the integrity and security of the network. The network has undergone rigorous internal testing and independent security audits to validate its robustness. Continuous security monitoring and a proactive approach to vulnerability management further enhance Sui's security posture.

### Axelar Integration Components

* **Amplifier and External Contracts:** Integrating Sui with Axelar will involve developing custom gateway contracts to bridge the Sui network with other blockchains. These contracts will leverage Sui’s object-centric data model and Move-based smart contracts to provide secure cross-chain communication and asset transfers. Axelar was responsible for the development of the Sui external contracts.  
  * [https://github.com/axelarnetwork/axelar-cgp-sui](https://github.com/axelarnetwork/axelar-cgp-sui)  
  * [https://github.com/axelarnetwork/axelar-amplifier/tree/main/ampd/src/sui](https://github.com/axelarnetwork/axelar-amplifier/tree/main/ampd/src/sui)

## Request for Security Council Review

### Purpose

The purpose of this review is to ensure that the integration of Sui with the Axelar network adheres to all security and technical standards, providing a secure and efficient cross-chain interaction mechanism.

### Additional Information

* GitHub Repository: [https://github.com/MystenLabs/sui](https://github.com/MystenLabs/sui)  
* Developer Documentation: [https://docs.sui.io/](https://docs.sui.io/)  
* Whitepaper: [https://docs.sui.io/paper/sui.pdf](https://docs.sui.io/paper/sui.pdf) 
* Independent Audit Reports: [https://sui.io/security](https://sui.io/security)

* [Sui Gateway Audit Report - June 2024](https://github.com/axelarnetwork/audits/blob/main/audits/2024-06%20Ottersec.pdf)
* [Sui Gateway Audit Report - November 2024](https://github.com/axelarnetwork/audits/blob/main/audits/2024-11%20Ottersec%20-%20Sui.pdf)

### Feedback and Questions

For any questions or feedback regarding this proposal, please contact the Mysten Labs team [inga@mystenlabs.com](mailto:inga@mystenlabs.com) or via Discord [https://discord.com/invite/sui](https://discord.com/invite/sui).
