# Hardhat

## Who is Hardhat:
* Hardhat is a development environment for Ethereum, focusing on simplifying the process of developing, testing, compiling, deploying, and debugging smart contracts.
* It provides a local Ethereum network for development, automation of certain steps, and plugins for extending functionality.

## Interview Notes

### Build Process Management:
* Configurations are set up for each Solidity version.
* The highest version is chosen for compilation unless specified otherwise.
* Source files are triaged to determine the best compiler version.
* Every compilation is stored, including input data and compiler data.

### Handling Multiple Solidity Versions:
* A compilation process is created for each file, which can be inefficient due to data volume and dependency inclusion.
* The goal is to compile only user data, not dependencies, and link them instead.
* Solidity is integrated as a bundled plugin, while Vyper is available as an additional plugin.

### Problems with Current Process:
* Source map resolving and remapping of imports are challenging, limiting artifacts.
* The source names used by developers and the compiler can differ, causing issues.

### Solutions Proposed:
* Create a manifest for each contract and unpack sources under the user directory.
* EthPM should mandate a single directory that points to all necessary locations.
* Standardize the naming of packages with the context of the user to clarify dependency names.

### Dependency Management:
* Dependencies of dependencies are a recurring issue, with npm being used to declare dependencies in each deployment.
* EthPM should unify the list of dependencies, building from the bottom up in the user project.
* Conflicting dependencies are currently handled by remapping and context switching as needed.

### Compilation Output:
* The compilation output is deterministic based on the input but can be heavy due to potential conflicts.
* A wishlist item is to store only the compilation input and keep subsets of data separate for efficiency.

### Language Support and Compilation:
* Hardhat supports Solidity primarily, with Vyper as a plugin.
* There's a desire for a standardized format for compiler input and output across different languages.

### Long-Term Goals:
* Standardize a compiler standard for smart contracts.
* Improve artifact formats to facilitate language interoperability.
* Implement a tagging system for imports to clarify package sources.

### Challenges and Wishlist:
* Dependency management within nested dependencies is complex.
* A tagging system for imports could clarify package sources and dependencies.
* A "batteries included" concept would make dependency origins more explicit.

## Conclusion:
Hardhat seeks to enhance the Ethereum development experience by addressing build process management, multiple compiler version handling, dependency management, and compilation efficiency. The integration of a standardized format and improved artifact management is seen as key to achieving these goals.