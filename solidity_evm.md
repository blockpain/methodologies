# EVM/Solidity Smart Contract Auditing Methodology

## Objective and General Approach

In our eyes, the purpose of an audit is to provide security guidance and recommendations such that a protocol can be safely deployed on the EVM. An audit is an opportunity to prepare your contracts for mainnet, and also learn secure development practices to implement in future work. It is necessary that an audit be seen as an interactive process, opposed to just a final report, and communication between the auditor and development team of the protocol is fundamental to this idea.

Now.. how does that work? It's easy enough to say *"We are going to make your codebase safer and your devs better."* Well for us, an audit looks like the following:

a) **ramp-up**: get good feeling for codebase, generate call graphs, look at hotspots (external calls, "low-hanging fruit").

b) **static analysis/dynamic analysis**: Use analysis tools such as Slither, Mythril, and Echidna on the codebase. This will help point out "low-hanging fruit", and give us hotspots to look at. These issues can also manifest into more serious issues depending on contract logic.

c) **line-by-line manual review**: This is the fun part. Now that we are familiar with the protocol and have some hotspots to look at, its time to dig into the logic. This is where we find the highs/crits that cannot be easily found using open source tooling. 

d) **development of PoC to illustrate findings**: While vulnerabilites in the codebase are being discovered, it is important to communicate them to the development team. Instead of providing theoretical evidence, and a paragraph in Telegram, it is most effective to create a PoC exploit contract to illustrate the finding. 

e) **re-review of code that was refactored due to audit findings**: After the audit is complete, it is important to ensure the refactoring does not introduce new vulnerabiities.


## Timeline and Workflow

**Ramp-Up:**

The ramp-up period for an audit should be short, and aided by documentation and resources provided by the development team. This includes getting an idea for what the protocol is intended to do, generating additional docs such as call graphs to help the audit, and finding hotspots to pay close attention to later. This phase typically lasts 1-2 days.

**Static and Dynamic Analysis:**

It is advantageous to perform static analysis immediately after ramp up, and disqualifying results is the first instance of true manual review being done on the codebase. Running static analysis does not take long at all, but confirming the results may take a day or two. Static and dynamic analysis (such as slither, mythril, and echidna) are incredibly useful for finding easier-to-spot vulnerabilities. This expedites the auditing process, and more attention can be paid attention to logic based vulnerabilities. These methods are also fairly comprehensive on their own, and can provide good data to reason about code hygeine and quality. Good analysis tools can be very powerful. 

**Line-by-Line, Manual Review:**

This is **the fun stuff**. While analyis tools can very often detect or point us in directions where existing code is insecure, manual review allows us to find the vulnerabilities which come from code **that should be there, but isn't**. These include things like missing authorization checks in permissioned functions, or missing intitialization of upgradable parent contracts. Manual review also allows us to find **logic based** vulnerabilities in a codebase. These are issues that arise specifically from the protocol design itself, and are often tagged with high and critical ratings. They lead to things like locked tokens, stolen funds, completely failing functionality, and so on, and so on. It is also during this part of a review where some of the "low-hanging fruit" can manifest into more serious vulnerabilities. This is why meticulous manual review of a codebase is necessary, and the most imporant part of any audit. It is often very useful to analyze a codebase from the perspective of call flow, in the way a user or admin would interact with the protocol, making a note of testing and creating PoC as necessary.


**Development of PoC**

Creating Proof of Concept exploit contract to demonstrate vulnerabilites in the codebase is, without a doubt, the best way to communicate their impact to the development team. These vulnerabilites should be presented to the development team as soon as possible, to either give ample time to present a patch, or maybe disqualify it as not an issue off the bat.


**Re-Review of Refactored Codebase**

After a review, it is necessary to ensure the **updates** to a codebase are also secure. Although rare, it is possible for developers to introduce new bugs while patching vulnerabilities discovered during an audit. As long as the refactoring is not of considerable size, such that a more thorough re-review should be organized, we will audit the refactored code if given the commit hash within 10 business days, and take at maximum 10 business days to do so. 

## Static Analysis, Dynamic Analysis/Fuzzing (In Depth)


## EVM/Solidity Specific Vulnerabilities (Low Hanging Fruit)




