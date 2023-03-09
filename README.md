# methodologies
auditing methodology and process


## WAYS WE CAN IMRPROVE IT

- more centralization of the toolkits, workflow (get codebase, generate callgraphs, run static analysis, get skeleton contract to see what functions exists, etc). There is no reason these things can be done in a few mouse clicks

- Data ingestion: half the job is building up team resources, keeping up with latest security news, making sure we are actively looking at everything we need to. There are tons of resources like old code4 reports, that we could parse and organize to better utilize.

- Note taking: while performing manual review, we are constantly taking notes and coming up with questions. The ability to mark up the codebase as comments and turn these into a more formal notes page would be amazing.

- Improvements to analyis: Slither and Mythril are great, but we want to build out some of our own static/dynamic tooling. Michael boutta be the static analysis monster.

- AI: I think there are a few places we can use it (analyzing code semantics, analyzing on-chain data including testnet.., code completion/security things in IDE setup)

## in the works

@immaterial cooking with gas fr

```
My current idea is to build a UI + plugin system.

- Everything is divided by "project" (good name?)

- Every project starts with a repository of code.

- You start this tool (which I haven't a name for yet), and it opens an interface, where you are asked some info (repo location, some description, configuration, etc.)

- Then you have a list of plugins; you can configure each plugin and run it.

- Each plugin has its UI where you can interact with the results, re-configure its parameters and re-run it, and see the history of the runs.

- On top of all this, there's a thing that lets you add notes and reference anything inside any of those results.

- And there's an editor for writing markdown.

Potentially, plugins could offload the computing on a remote machine.
```


@jason got the saucy report generator coming

```
 I found a way to use pure pandoc and LaTeX with Docker. Bl0ckPain Inc is gonna have a stellar looking PDF output with a single terminal command. I’m talking custom cover page with logo, headers and footers, pagination, can even underlay background images with modified opacity on the report pages
 We’ll also be able to have different types of PDF templates if we wanna do other types of reports
```


