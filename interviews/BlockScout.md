# BlockScout

## Who is BlockScout
Blockscout is the first fully-featured open-source blockchain explorer available for use by any Ethereum Virtual Machine (EVM) chain.  Blockscout gives everyone access to essential on-chain data, the ability to interact with smart contracts, and the tools to view and verify transactions quickly and easily. 

## Iterview Notes

### Build Process Management
* Approach Verification from multiple angles
* Deploy contract on a tool then go through UI and go through UI form and manually fill out information including byte code -> submit request -> server compiles and checks for matching byte code 
* Part of [Verifier Alliance](https://verifieralliance.org/who.html) that works with other proejcts that have verification mechanisms to develop a shared database of contracts' source code to create a publicly accessible database
* Uses foundry for local source development
* For backend side for automation: use external library 
    * updates depending on contract binaries on demand
### Problems with Current Progress 
* Supporting multiple versions of the compiler and certain chains deviate a bit (ZkSync, Tron)
* Legacy side of solidity that are no longer being maintained
    * Using the same logic between the old version and the latest version no longer work 
* EthDebug is specifiying the advanced data
    * Standardizing it should help manage some of the breaks in the past versions
### Dependency Management
* Source mapping is a common problem 
* Standard JSON is the only way to apply the dependencies to the UI form. Which is hard.
    * Explaining to UI form how all dependencies are connected is complicated if not using standardized JSON
* Flatten the JSON but it is not very useful for complex multi contract issues
    * Most of the tools now support multi file verification without big issues so flattening is no longer needed 
* We treat them as a single source map and figure it out. 

### Managing Verification
* API Schema for verification:
    * Keep as close to Etherscan as possible 
    * Have own API that doesn't have as many issues with legacy Etherscan API
* All traffic goes UI goes through newer API compared, verification using foundry and hardhat 
* EthPM Goal: Hoping to make 3rd version that goes through standardized interface 
### Challenges and Wishes 
* 2 issues: schema and storage of compilation artifacts 
    * Storage of complication bugs
        * What is the ideal way to store 
    * Advanced need for AST decoding issue with Tenderly as well 
        * Cascade structure to how files are specifiedL manifest = root level obj, compiler setting built in with specified links to artifact files 
* Proxy Contracts implementation relationship - too many proxy and nonproxy implementation 
## Conclusions
BlockScout gives users an accessible EVM blockchain explorer by giving everyone access through a UI system and allows users to verify their contracts through multiple methods.The key challenges lie in the schema and storage of compilation aritifacts. 