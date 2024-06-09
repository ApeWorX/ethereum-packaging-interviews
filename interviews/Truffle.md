Eth Debug

We need a way to descirbe all the highlevel types: (TYPE SCHEMA)
* This is a uint256, it has this many bits.
* This is an array of uint256 it has this many bits
A json schema to describe any high level types

You need to also be able to describe machine data (ALLOCATION SCHEMA)
* top of a stack
* point to memory offset
* point to memory offset that indicates that you are at the top of the stack
* at compile time 

Annotate each instruction, when you observe this insctrution, you know what you are looking in correlation to the schemas

The debugger would look at the instruction, look at the schema, look at the compiler know what is being executed and later know when it was changed via the annoation.

ABI is a very nice succient way to show the contract interface

ETHDebug is more related to langauge scemantics and it also agnostic to the language

usecase if you are speficiying a know type then you must adhere to the format else you represent whatever you want
The previous schema was to annotate EVM instructions

Pointer can help the debugger point to where the instruction is in memory. But dyanmic arrays will changes and it doesnt scale well.

So what if you can have complex expression point to instructions. 

For a debugger to function, the compiler needs to provide enough information at comile time so that a debugger maybe 5 years later can come back and find the instruction at the memory spot at this time. Comeplex expression can do that and save space. 

This apporach is a lot easier to read than source mapping. So Since it is so early in devlopement, we can take into consideration on how EthPM will play into this. 

This approach will make the sourrce mapping readable to a human and not just have a string of numbers and hexcode. 

So in terms of ETHPM: the concept of readablilty and transforming data into something readable at a glance.

We should consider making ETHPM a cascade of information:
So when you compile all the data is not hidden behind layers. it is all there.
but when you publish, you cascade the information, you hide non esstential data behind links so at a GLANCE it is readable and provides all the important infromation. 

So if you want just the sources, you can just compile the dependecies. If you want the highlevel you can just do that. etc

How would you handle older compiler information that doesnt have this format?
2 Ways approach: truffle debugger is an older compiler that has dealt with a lot of edge cases that require fining (I.E) if statement that resolves issues.

SO the first part is to extract all the if statement realted to edge cases and run it with the new compiler so it can create a new compiled artifact with the right format. 

SOlidiity storage output layout: is discreeet. This storage is this size and has these values. 

With Expressions, you can storage a range of values with an expression


EthDebug aims to solves compatiblity with expressions. Building old projects with output and input and fill in the blanks with newer and better tools with no loss of information.

You can do it manually but if the manifest provides all of the building blocks, you dont need to do it manually. 

As gnindian was working on this. The internal state of the tool's knowledge is different from representation the package. 

So his work to address the tooling (debug). Truffledb[truffle debug](https://archive.trufflesuite.com/docs/truffle/db/)
* Modeling the data
* "bytecodes" [resource: Bytecode; input: BytecodeInput]
* "compilations" [resource: Compilation; input: CompilationInput]
* "contracts" [named; resource: Contract; input: ContractInput]
* "contractInstances" [resource: ContractInstance; input: ContractInstanceInput]
* "nameRecords" [resource: NameRecord; input: NameRecordInput]
* "networks" [named; resource: Network; input: NetworkInput]
* "networkGenealogies" [resource: NetworkGenealogy; input: NetworkGenealogyInput]
* "projectNames" [mutable; resource: ProjectName; input: ProjectNameInput]
* "projects" [resource: Project; input: ProjectInput]
* "sources" [resource: Source; input: SourceInput]

use case: If you deploy a project to a newtork and the network forks, you should be aware of all the project deployed prior to your project deployment and how you project will affect others after yours

How does a dev tool enumerate this?

Network abstraction
Keeping track of blockchain networks is nontrivial if you want to handle network forks/re-orgs. To accommodate this, @truffle/db models blockchain networks as individual point-in-time slices at various historic blocks. As a result, a single blockchain network (e.g., "mainnet") can and will comprise many disparate DataModel.Network resources, one for each block previously added.

insistence on contract id might be a concept that we should consider when making ethpm

what is a bytecode, we can use the modeling in here to help descirbe ethpm

Besides what you worked on and what you are working on now? Are there any other ideas or thought you want to share to improve upon for ape or ethpm?

For ape, there might be a type you want to pass along this information. maybe data tranfer objects and stress test his work with out framework. Ape uses pydantic to serialiable format. 

Ape also use hypothesis, we can take a schema of a pydantic model and convert it to a random input gnerator. not the same as a json schema. Pydantic schema[generator](https://docs.pydantic.dev/latest/integrations/datamodel_code_generator/)

