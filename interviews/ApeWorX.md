ERC-2678

Ape has modified for ease of use:
Managing and compiling artifiacts

Build Dev Cycle
Building locally, and add dependencies
Cache compilations


Publishing Cycle
Taking your and putting through a registration (Etherscan)

Verification
Ethercan will taking published code and reproduce the build


You are either making a dev tool or you are making verification structure meaning you are in Build or verify

What steps can automate and key off and perform verification. Sourcify

These 3 phase is a mess, ape has done it already fixed the issue

Lets get everyone on board

EthPM streamline the building information so we dont build the a different tool for  each project to do the same thing across the board.

Similar to the USB to Type C


Questions:
Dev tool questions:


How do you manage your build process
What are some problems with the current process


	How does your framework manage solidity compilation
How do you store it
What the structure of the folder
	Big Manifest json file
	Every single contract is a different file
	What kind of data is stored in these files
		ABI byte code
		We havea lot a compileire debugge output ast, help out more advance dev tool

		That majority of the data is the debug features, so we have all these extra use data if you want want it. So 

		Sources has this soft link ability can link to a online or local and that level of support is a possible solution
		Some network support older compiler version for older fork rules
		Arb doesnt sup



How do you manage dependencies from different frameworks
	How do you add dependencies to your project, config files?
	What ways fetching project dependencies do you support, github local file tree

	What are some problems with the current process:
		Too many type of project tools , too many structures of project, host it all from any registry of these types. 

	Manifest file encapsulate the files into 1 way and then you can reference them with all tool. 
	Source mapping is a issue, for solidity there is import mapping is awful, it is similar to project structure
	
	
How do you manage deployments
	How do you fetch previous publish contracts type information
	And for testing and internal testing, when you run local testing how do you know that contract type information, is there something cached
	

What are some problems with the current process

How do you publish code after it is deployed
How problems do you have there
How bad etherscan api is, it is inconsistent and hard to use


List of Interview

Devtools
Ape
Foundry
Hardhat
Remix


Slither 
	Static analysis tool where they look at the publish solidity code


Verification:
How do you receive input that you need to start a verification
	
Do you have any manual or automation trigger:
	Proxy contract 
Do you have any automation for part of the verification
Do you pull in information to fill in the gaps for your database
What are some issues in this process
What interfaces to support querying the information


Cookbook



Sourcify  ( spoke but we can solve their issue )
	Their registry will automatically verify, metadata is able to replicate their build
	This is an end goal
	They dont have the entire build context
Tenderly

Etherscan
	White label etherscan clones
	ETH pm streamline the interface and downloading

Blockscout

Truffle: Gideon 

Upload to github to track info
