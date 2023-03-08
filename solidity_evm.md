# EVM/Solidity Smart Contract Auditing Methodology

## General Approach

Regardless of the purpose behind the protocol we are auditing, our mission remains the same. It is our goal to provide clients with comrehensive code reviews, such that they are confident to safely deploy their protocol on mainnet. It is a false assumption that audits are a rubber stamp of perpertual security, but this is still a good target to aim for. Given it is likely a codebase will be updated, refactored, or otherwise altered after deployment, it's important to take security into consideration at every step of the development process. To assist clients with improving their overall security posture, it is our mission to clearly communicate ALL potential issues found in a way the development team can grow and learn from. Security is a constant process, and a good auditor should guide their clients towards safer develeopment practices over the course of a review/their partnership.

Now.. how do we do that? It's easy enough to say "we are going to make your codebase safer and your devs better," but in practice, it looks like the following:

a) ramp-up: get good feeling for codebase, generate call graphs, look at hotspots (external calls, "low-hanging fruit").

b) static analysis/dynamic analysis: use analysis tools such as slither, mythril, echidna on the codebase. This will help point out low hanging fruit, and give us hotspots to look at.

c) line-by-line manual review: this is where the fun happens. Now that we are familiar with the protocol, have some hotspots to look at, its time to dig into the logic. This is where we find the highs/crits that cannot be easily found using open source tooling. 

d) development of PoC to illustrate findings: after vulnerabilites in the codebase have been discovered, it is important to communicate them to the development team. Instead of providing theoretical evidence, it is often most effective just create a PoC exploit contract to illustrate the finding in black and white. 

e) re-review of code that was refactored due to audit findings: after the audit is complete, it is important to ensure the refactoring does not introduce new vulnerabiities.


## Timeline and Workflow

**ramp-up:**

the ramp-up period for an audit should be short, and aided by documentation and resources provided by the development team. This includes getting an idea for what the protocol is intended to do, generate additiona docs such as call graphs to help the audit, and find hotspots to pay close attention to later. This phase typically lasts 1-2 days.

**static and dynamic analysis:**

It is advantageous to perform static analysis immediately after ramp up, and disqualifying results is the first instance of true manual review being done on the codebase. Running static analysis does not take long at all, but confirming the results may take a day or two. Static and dynamic analysis (such as slither, mythril, and echidna) are incredibly useful for finding easier-to-spot vulnerabilities. This expedites the auditing process, and more attention can be paid attention to logic based vulnerabilities. These methods are also fairly comprehensive on their own, and can provide good data to reason about code hygeine and quality. 

**line-by-line, manual review:**

This is **the good stuff**. 

## Static Analysis, Dynamic Analysis/Fuzzing

## Line by Line, Manual Review 

## EVM/Solidity Specific Vulnerabilities (Low Hanging Fruit)




