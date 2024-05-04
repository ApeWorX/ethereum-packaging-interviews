# Common Desires:

**Ease of Use:** Interviewees expressed a desire for a more intuitive and user-friendly experience in the next iteration. This includes simplifying the onboarding process for new users and improving the overall usability of the platform.

**Scalability:** Scalability was a common concern, with interviewees emphasizing the need for the platform to handle 
* increased transaction volumes. 
* support for a growing user base without sacrificing performance.
* different types of transactions that don't follow standards.  

**Interoperability:** There was a consensus on the importance of interoperability, allowing for seamless integration with other blockchain networks and external systems.
* With different tools and new tool developing each day how can we intergrate them
* Forcing Solidity and Vyper to adopt it is not feasible since it is hard to make meaningful changes in a timely manner
* We should let dev tool adopt and adapt the ethpm format

**Security:** Security was a top priority, with interviewees stressing the importance of robust security measures to protect user funds and sensitive data from potential threats.
* Verification wants to make security a top priority in making this format

**Community Engagement:** Interviewees highlighted the importance of community engagement and collaboration in driving the platform's development forward. They expressed a desire for more opportunities for community involvement and feedback gathering.
* The best way for dev tools to adopt this format is to have the community create the standard

**Guiding Principles:** EthPM is designed to support package management tasks like installing dependencies, building releases, and verifying public deployments of source contracts. The specification is driven by community-driven best practices and aims to encourage code reuse and software quality.


# Concerns for the Next Iteration of EthPM v4

**Complexity**: There were concerns about the platform becoming too complex, potentially alienating less tech-savvy users and hindering adoption.
* Having a standard ethpm is important but when there are edges that are not standard how should we approach solving them?
* Cookbook use case is that flattening the source files and dependencies is their build process. But when it has dependencies within dependencies and with same dependencies with different version how can we solve it?
    * Maybe a solution is to have naming conventions to point to the right dependcies and not compile it very time you need it. 


**Privacy**: Privacy concerns were raised, particularly regarding the transparency of transactions and the exposure of sensitive information on the blockchain.

**Centralization**: Interviewees expressed concerns about the risk of centralization, emphasizing the importance of maintaining decentralization principles in the platform's design and governance.
* keeping source file and metadata in a db is great for queries but it hinders one of the pillars of decentralization of web3. So how much do we depend on db vs ipfs?

**Pros and Cons:** EthPM offers benefits such as improved code reuse, simplified dependency management, and standardized package distribution. However, challenges include the need for careful consideration of security risks, dependency tracking, and compatibility with existing tools and workflows.

Overall, the interviews provided valuable insights into the community's desires, concerns, and priorities for the next iteration of the blockchain platform. By addressing these considerations, developers can work towards building a more robust, scalable, and user-friendly platform that meets the needs of its users while staying true to the principles of decentralization and security.


# Specific specifications for EthPM (Ethereum Package Management) include:

**Compiler and Dependcy Versions:** They must include a field specifying the version of the EthPM manifest they conform to. If they are allowed to use the latest version, let it be. 

**Package Metadata:** Packages may include metadata keywords, address, etc for additional information that would help trace.

**Sources:** The sources field defines the source tree necessary to recompile the contracts contained in the package. It includes a map of source files with their corresponding checksums or URLs.

**Contract Types:** The contractTypes field hosts the contract types included in the package, with details such as contract name, source ID, deployment bytecode, runtime bytecode, ABI, user documentation (userdoc), and developer documentation (devdoc).

**Compilers:** Information about the compilers and their settings used to generate the contract types must be provided. This includes the compiler name, version, and settings. Settings are one of the most important piece of information that defines the difference between contracts made from the same factory.

**Deployments**: Information about deployed contract instances, including the contract type, address, transaction hash, block hash, and runtime bytecode.

**Build Dependencies:** Packages can define dependencies on other EthPM packages, specifying their names and corresponding Content Addressable URIs (CAURIs).

**Checksums and Hashing:** Checksums are used to verify the integrity of source files, and hashes are used for content addressing and linking. This will help keep the sensitive information secret on a digital ledger that is readable by everyone.

**Linking:** EthPM supports linking within bytecode using Link Reference and Link Value objects, allowing for modularization and code reuse. When the same or compatible dependencies are used in difference places, it should be linked and named properly and saved in a higher tier so all the contracts that require it will have access to it. 


**Document Format:** EthPM packages must adhere to a tightly packed JSON format with sorted keys and UTF-8 encoding. Line breaks and extra whitespace are not allowed.

**Backwards Compatibility:** EthPM v3 introduces changes to improve understanding and readability, such as renaming the manifest_version field to manifest. To ensure backwards compatibility, v3 packages must include a top-level manifest field with a value of "ethpm/3".

**Glossary:** EthPM includes a glossary of terms used in the specification, providing clear definitions and explanations for better understanding.

**BIP122 URI:** BIP122 URIs are used to define blockchain chains and distinguish between forks, providing a standard way to identify different blockchains. What is this?


# EthPM v4

## Simple Summary
A data format describing a smart contract package.

## Abstract
EthPM is designed to support package management tasks like installing dependencies, building releases, and verifying public deployments of source contracts. The specification is driven by community-driven best practices and aims to encourage code reuse and software quality.

## Motivation
The goal of this project is to align the implementation of EIP-2678 across the biggest developer tools in the Ethereum Ecosystem. We want to understand the shortcomings of the current process of development, hear the possible solutions, and implement the best practices.


