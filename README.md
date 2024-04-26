# README for Eip-2678

## What is EIP-2678 EthPM v3
ERC-2678 proposes a revised Ethereum Smart Contract Packaging Standard, also known as EthPM v3. The standard defines a data format for package manifest documents, representing a package of one or more smart contracts, including source code and deployed instances across multiple networks. These manifests are minified JSON objects, distributed via content addressable storage networks like IPFS and published to on-chain EthPM registries. 

**Key components** include package name and version, metadata, sources, contract types, compilers, deployments, and build dependencies. Conventions ensure strict serialization rules and encoding, while a glossary clarifies terminology such as ABI, bytecode, and chain definition. The standard aims to promote code reuse, best practices, and security considerations within the Ethereum development ecosystem.

## Motivation of this proposal:

The goal of this project is to align the implementation of EIP-2678 across the biggest developer tools in the Ethereum Ecosystem. We want to understand the shortcomings of the current process of development, hear the possible solutions, and implement the best practices.


ApeWorX was tasked with the job to improve and champion the Unification of Standardization. 

We have a set of general interview questions that we asked developer tools to answer. These questions really dove into the main aspects of the process and how each tool helped and where it was difficult for them to make the process easier or better for the developers. 

## Here are the list of questions:

1. How do you manage your build process?
    1. What are some problems with the current process?
1. How does your framework manage solidity compilation?
1. How do you store it?
1. What is the structure of the folders?
1. How do you manage dependencies from different frameworks
    1. How do you add dependencies to your project, config files?
    1. What ways of fetching project dependencies do you support, github local file tree?
    1. What are some problems with the current process?
1. How do you manage deployments?
    1. How do you fetch previous publish contracts type information?
    1. When you run local testing how do you know that contract type information, is there something cached?
    1. What are some problems with the current process?
1. How do you publish code after it is deployed?
    1. What problems do you have there?

While every interview is different, the questions are more of a guideline of how the conversation should go. The importance of hearing each interviewee speak in a way that allows them to be themselves brings the heart of the conversation out. We want to listen to what is important to them and understand their perspective.

