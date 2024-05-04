# Common Desires:

**Ease of Use:** Interviewees expressed a desire for a more intuitive and developer-friendly experience in the next iteration. This includes simplifying the onboarding process for new users and improving the overall usability of the format.

**Scalability:** Scalability was a common concern, with interviewees emphasizing the need for the format to handle 
* increasing request volumes and indexing needs 
* support for a growing user base without sacrificing performance.
* different types of deployments that don't follow standards.  

**Interoperability:** There was a consensus on the importance of interoperability, allowing for seamless integration with other blockchain networks and external systems.
* With different tools and new tools developing each day how can we intergrate them
* Forcing Solidity and Vyper to adopt it is not feasible since it is hard to make meaningful changes in a timely manner
* We should let dev tools and services adapt instead

**Community Engagement:** Interviewees highlighted the importance of community engagement and collaboration in driving the format's development forward. They expressed a desire for more opportunities for community involvement and feedback gathering.
* The best way for the community to adopt this format is to have dev tools promote the standard

**Guiding Principles:** EthPM is designed to support package management tasks like installing dependencies, building releases, and verifying public deployments of source contracts. The specification is driven by community-driven best practices and aims to encourage code reuse and software quality.


# Concerns for the Next Iteration of EthPM v4

**Complexity**: There were concerns about the format becoming too complex, potentially alienating less tech-savvy end-users and hindering adoption.
* Having a standard is important but when there are edges that are not standard how should we approach solving them?
* a common use case is that flattening the source files and dependencies within a build process. But when it has dependencies within dependencies and with same dependencies with different versions, how can we solve it?
    * Maybe a solution is to have naming conventions to point to the right dependcies and not compile it every time you need it. 

**Centralization**: Interviewees expressed concerns about the risk of centralization, emphasizing the importance of maintaining decentralization principles in the format's design and governance.
* keeping source file and metadata in a db is great for queries but it hinders one of the pillars of decentralization of web3. So how can we broaden access via technologies like ipfs?

**Pros and Cons:** EthPM offers benefits such as improved code reuse, simplified dependency management, and standardized package distribution. However, challenges include the need for careful consideration of dependency tracking, compatibility with existing tools and workflows, and promoting overall adoption of the format.

Overall, the interviews provided valuable insights into the developer community's desires, concerns, and priorities for the next iteration of smart contract tooling. By addressing these considerations, developers can work towards building a more robust, scalable, and user-friendly platform that meets the needs of its users while staying true to the principles of decentralization and open accessibility.

# Specific specifications for EthPM (Ethereum Package Management) v4 upgrade include:

**Compiler Versioning and Dependencies:** There must be an easy way to determine the complete build configuration of a package to be able to reliably reproduce a build, including compiler version and configurstion flags/ environment variables used.

**Package Metadata:** Packages may include metadata keywords, address, etc for additional information that would help downstream users and indexers trace deployment information.

**Sources:** All sources should be arranged in their original hierarchy, and it should be easy to extract only a subset of sources for use as downstream deoendencies

**Contract Types:** Packages should provide the complete build output artifacts for all the sources in included in the package, with details necessary for direct usage such as contract name and ABI accessible within the format. It may also metadata useful for re-verifying build integrity such as source ID, deployment bytecode, and runtime bytecode, either directly or as indirect links to other accessible package data. Build artifacts helpful for more advanced developer usage such as NatSpec documentation, storage layout, etc. should be provided as indirect links to minimize the size of a package.

**Deployments**: Information about deployed contract instances from ethPm v3 was generally seen to be outside the scope of determining a build configuration, and should instead be referenced in a separate standards development such as dpack.

**Build Dependencies:** Packages must define their build dependencies using easily accessible links to other EthPM packages, specifying their names and corresponding either via Content Addressable URIs (CAURIs) or containing information such as checksums to determine their integrity.

**Linking:** EthPM supports linking within bytecode using Link Reference and Link Value objects, allowing for specifying library dependencies. Since this relates to runtime deployment (as the address is used for deployment linking), this is left as an exercise for developer tooling, but it should be possible to independently verify the build output when proper substitutions have been made by the devtooling.

**Storage Format:** Previous versions of EthPM packages used a tightly packed JSON format with sorted keys and UTF-8 encoding. While metadata and build artifacts should be handled in this (or a similar) text format due to wide accessibility, the layout of sources in a virtual filesystem should instead be replaced with a local filesystem capable of communicating the build configuration more effectively.

**Backwards Compatibility:** EthPM v4 will contain a number of incompatible changes to its predecessor, however through careful consideration it should still be possible for future revisions to maintain backwards compatibility with the new revision. The name "ethPM" may change to a different name to reflect this incompatibility.