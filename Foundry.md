# Foundry

# Who is Foundry:
* Foundry is a suite of tools/platform designed for developing, testing, and deploying smart contracts and dApps on blockchain networks, particularly popular in the Ethereum ecosystem.
* Known for its efficiency in compiling, testing, and deploying Solidity smart contracts.

# Interview
## Foundry Build Pipeline Overview:
* Parse dependencies under submodules.
* Detects dependencies across all contracts in the graph.
* Compile only changed dependencies.
* Handle conflicting dependencies by compiling parallel dependencies in SolC.
* Create artifact folder to store ABI, bytecode, etc.
* Aspires for a user experience similar to Cargo.


### Cargo Example:
* Desires features like dependency management and a locked file similar to Cargo's Cargo.toml.
* Aims to avoid duplicate dependencies.
* Appreciates Cargo's resolution algorithm based on version requirements, dependency tree, semantic versioning, and resolution algorithm.
### What is Cargo:
To give some background information: Cargo is the official package manager for Rust. It utilizes a cargo.toml file to specificity, resolve, and fetch dependencies. 
If you have duplicate dependencies nested under submodules, Cargo will deduplicate them during the dependency resolution process. Cargo ensures that each dependency is fetched and built only once, even if it is specified multiple times within your project's dependency tree. This helps reduce the size of the final build artifact and ensures that dependencies are not unnecessarily duplicated. 
If there are conflicting version requirements for a dependency, Cargo will attempt to find a compatible version that satisfies all requirements. The way cargo determines resolution is based off of: **Version Requirements, Dependency tree, semantic versioning and Resolution Algorithm.**
### Dependency Tree Flattening:
* Considered for worst-case scenarios to resolve conflicts.
* Advanced Caching and Compilation Optimization:
* Compile only when necessary.
* Parallelize Solidity compilation when dependencies are independent.
* Prefers EthPM to detect and compile only necessary parts rather than all linked files.
### Remapping Issues:
* Faces challenges with path-based and virtual filesystem.
* Suggests a standard naming scheme for path-based and virtual filesystem.
### Verification Issues:
* Offers verification through connection to Etherscan during forge script and forge create.
* Identifies the need for better diagnostic tools for support tickets.
### Wishlist:
* Multi Language support.
    * Vyper and Solidity share dependencies
* Solc improvements for compilation times and gas optimization.
* Plugin architecture for multiple languages using static compilation.
* Desire to unify dependencies and subdependencies, particularly addressing challenges with remapping and virtual filesystem.
# Conclusion:
Foundry aims to streamline the development process for Ethereum projects, addressing challenges such as dependency management, compilation optimization, and remapping issues. Integration with EthPM is seen as crucial for improved efficiency and compatibility across projects.


## What is Foundry
[Foundry](https://github.com/foundry-rs/foundry) is a suite of tools or a platform designed to facilitate the development, testing, and deployment of smart contracts and decentralized applications (dApps) on blockchain networks. Foundry itself is a popular development tool in the Ethereum ecosystem, known for its efficiency in compiling, testing, and deploying smart contracts written in Solidity, the programming language primarily used for Ethereum smart contracts.

