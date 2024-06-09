Sourcify

The point of the interviews is to revive the EthPM for the modern issues that dev tools and future proof common build format. It is to help close the gap between dev tools and verification.

Security Alliance:
It is a group of like minded individuals that what to improve the sercurity of ETh as a whole. with a diverse group of people from different parts of the ecosystem come together to test, discuss, and build soultions of the current securtiy problem of today.


Sourcify should push toward where the dev tool can manage the metadata and publish the metadata. 

and to verify on deployment is to read the metadata on chain and do the index. So you dont need devloper input via the api to verify. You dont need outside material. Everything you need is on chain. 

When we say metadata, it is only the hash of the complete project context not the entire source code. 

In order to get this goal. One thing we need to do like we have been talking to all the other protocols about it championing a standardize formart for Project manifest to specificy builds agnotisc to dev tool or anything thing that wants to use metadata. 

one of the steps that would requires some work is the complie the format sourcify and etherscan uses and create the best versio of it.

One practical problem implementing the previous ethpmv3 was that when it came time to standardize after all the input. The compliers that were told to make a standard. Vyper and Solidity diverged from the json input.

So instead we are going to have dev tool implement the standard. building Standardize interfaces for etherscan and devs

We need to also future proof for other languages.

Interface that interacts with rest api for standarization

Specifiy the rest api object for security alliance verication team benefits

Souricy Verificaiton Process:
They are manily Solidity only
They have metadata related to solidity contracts such as source files.
If the build file does not have source files, it cannot create the metadata related to the project which in turn cannot verify. So by default it should output the metadata. Hardhat, foundry and etc should do this by default. 

Hardhat and Foundry did not have source files included in the build files by default, but since Souricy asked, it now by default. Which reenforces the idea that Dev tools should be the ones to use and create EthPM v4.

The metadata, the source files, libraie address, mutables all stored in a file system because, they want to plublish every thing in IPFS. 

But now Sourcify is transitioning to a Database in  resepct to Security alliance shcema and extension.

Now this will allow sourcify to have a huge data set to verify everthing. it is more powerfuil to use than to use IPFS. 

What are the Pros and Cons IPFS and DB.

Pros:
Being able to query, how many libraies does this use and can we verify that it is correct?

How many contracts have optimization turn off? you can find that number

Cons:
Additonal compenet to manage and backup and mantain.

Sourcify still has to publish the build files and project looking to verify on IPFS. It needs to ve public, so it is just an extra step. however it speeds up the process with a DB pros.

Byte code is also stored in DB for Sourciy, so you can do search operations even if the the source code are built from the same byte code with different settings. 

All the fields that are used for settings and constructor are stored in json column so you dont have to change the scheama. 

Any non classified data are stored in a new column so it doesnt break the already classififed data.


Sourcify Build process:
What starts it, what are the context anad how does metadata plays into it

We have options to verify without metadata. They have ways to abstract the metadata away so it doesnt affect the build process.

Verify from etherscan, you dont have the metadata. then you create the metadata file from the result of this. 

ANother option: Give sourcify the standard json output and from that create the metadata and then start the verification process.

From the metadata, you can get the compiler settings and the sources, build a standatd json input and put into the compiler and then it create the bytecode and compare it to the onchain bytecode. 

To get the runtime bytecode on chain is a simple RPC call, but the creation bytecode is tricky. 

if it is a stand alone contract it is easy, but if it is a factory contract created by a another contract, it is tricky since it is similar. 

then you have to trace it to an archive node. 

Discussing this idea brought about another idea to talk about. Once ethpm v4 is inplace, factory created contract are linked and can be traced by transactions. So in the manifest at the highest level, it should be known and traceable that fact that it has been created and verified by another contract that created this which is in this case 128 block which doesnt require an archive node. 


 Ultimately, we trace to find the initialiaztion code that created this contract. So having someting indicate that the internal contract is created by a parent contract helps with bi-directional tracing.

Metadata format so we can append it to ethpm: It will help trace creation of contracts: If it has this format and you can tell what has been created and do a verification.


Monitoring: Sourcify listens to certain blockchains and look at the transaction. If the transaction is an EOA or a creation contract bytecode. we pull it from IPFS and then fetch and compile and verify. 

it is very similar with filtering the transaction flow to exctract deployment.

something that sourcify wanted to do: DB of geth that could push the creation bytecode into DB and index them. 

Now that sourcify has it, sourcify can search for creation bytecode and find anything else.

Goals that EThPM and Sourcify can align with:
* Solididy the build context and standardize that
    * Do it with all the compiler not just solidity
* Once the build context is built, we can describe what on chain metadata should look like, A format, so you can extract information that you need like contructor arguments
* automate this hook into a database to verify it
    * verify it on difference DB

EOF stands for "EVM Object Format." It's a specification for describing changes and enhancements to the Ethereum Virtual Machine (EVM). The "Mega EOF Endgame" Specification, or EOFv1, is a comprehensive document outlining various changes proposed for EOF. It serves as a guide to understand the modifications suggested for the EVM Object Format.

EOFv1 is the initial version of the specification, and it provides a unified view of the proposed changes, consolidating discussions from previous versions like EOF 1.1 and EOF 2.0. While EOF is designed to be extensible, the document primarily focuses on the features and improvements outlined in EOFv1.






