# Collaboration Between Cookbook and ApeWorX

## Who is Cookbook
Cookbook is an open-source smart contract marketplace that facilitates the search, upload, download, deployment, management, and integration of Solidity smart contracts into applications. They are expanding their marketplace to include Vyper contracts and are interested in incorporating Python due to their developers' interest in the language.

## Vision and Goals
Connor from Cookbook envisions the platform as more than just a marketplace; it aims to establish a system of best practices by analyzing smart contract code across various languages. Cookbook's approach aligns with ApeWorX's project with the Ethereum Foundation, which focuses on unifying project manifests through EthPM.

## How EthPM Can Help Cookbook
EthPM standardizes the description of projects, their source files, dependencies, and provides a streamlined index of sources. This is particularly useful for Cookbook, as it can help address the interoperability issues caused by protocols managing projects in their own unique ways.

## Cookbook's State of Affairs
Cookbook's current challenges include:
* Parsing information from compiled contracts for tools like HardHat or Foundry.
* Managing dependencies and downstream tools with multiple workarounds.
* Improving the EthPM format for readability and parsing.
* Supporting multiple compiler versions and contracts with varying compiler requirements.
* Verifying entire protocols as single entities.
* Obtaining verified contracts before building a protocol.

## Proposed Solutions
ApeWorX proposes the following solutions to address Cookbook's challenges:
* Standardize parsing and formatting of information from compiled contracts.
* Enhance the EthPM format for better readability and handling of multiple compiler versions.
* Develop a standard method for verifying entire protocols and obtaining verified contracts.

## Cookbook's Use Case
Dependencies are crucial for EthPM. The manifest should enable parsing dependencies from main contract files, allowing for the separation of workload and verification. Dependencies are currently referenced by absolute paths, while main contracts use relative paths.

## Proposed Standard for Dependencies
* Use relative paths for main packages to represent the entire project structure.
* Name dependencies for easy reference within the project.
* Simplify source rectification using names to make it easier to read and understand.
* Maintain relative paths for custom files and absolute paths for reusable libraries.

## Conclusion
ApeWorX is open to collaborating with Cookbook to standardize EthPM and tackle the challenges identified. The goal is to create a more streamlined and interoperable system for managing Ethereum project manifests, which will benefit the wider Ethereum development community.

# Summary
Cookbook, an open-source smart contract marketplace, is collaborating with ApeWorX to enhance their platform by adding Vyper contracts and potentially incorporating Python. They share a vision of creating a system of best practices by analyzing smart contract code from various languages. ApeWorX's work on unifying project manifests with EthPM aligns with Cookbook's goals, addressing interoperability issues and standardizing project management across different protocols. Together, they aim to overcome challenges related to parsing compiled contracts, managing dependencies, and verifying protocols, with the ultimate goal of establishing a more efficient and unified Ethereum development ecosystem.