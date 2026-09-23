## Core model
 in a number of sucessive stages some with multiple passes in a staged arrangement taylored to using python tools, scripts and lowest cost agentic ai 


core stages
0 get the foundation of the analyser part of this project sorted
0.1 - Define the core requirements
  - a staged development of the analyser and staged code analasis, all with a discussion of each point before its committed
 - how this repo is both the development of the tools required to analyse code and an actual but of code being assessed - both are going to be done in stages - as the analyser implementation is developed it will be tested against the sourve code
 - minimum requirements eg. documentation standards - minimum metadata block at the start of every file with doc type 
0.2 - work out at a high level what steps are needed to analyse the code while assessing the requirements and adding addional requirements along the way, once an overall system emerges it needs to be documented in a high level document
0.3 - start breaking the steps down into stages using the requirements - both step requirements and core requirements
   - document this in a doc like "Analyser_structure.md - add tags to the stages with implementation status (complete, testing, implementation, concept, etc)
0.4 - design the first stage


   
1 - Chunk the source code (put the implentation details in "Stage 1 - Chunk"
2 - 



The following needs to go into relevent documents - ask before moving it:
A Python script reads C# syntax to identify **selected major artifacts**, such as forms, substantial functions, dictionaries, and other important structures. Small declarations remain in their containing artifact until a later pass determines that they need separate treatment.

Processing starts at the source-file level. A later invocation opens one selected parent and handles only its immediate children. This continues recursively as far as useful. The source name of an artifact is retained; a type prefix and stable ID disambiguate its files and references.

The tool maintains one manifest above two parallel folder trees:

- **Source tree:** cut source fragments containing the original C# text, boundary comment tags, and references at the positions of extracted children. These fragments are evidence for analysis, not independently compilable C# files.
- **Analysis tree:** corresponding documents at the same relative positions. They begin as minimal structural records and gain definitions, pseudocode, data descriptions, and relationships in later stages.

The original source remains available. It may be annotated progressively with begin/end comment tags to make boundaries explicit. Every source edit must remain traceable to a revision and be checked for unintended behavioural changes.

## Intended stages
1. Chunk the source and record 
1. **Establish the baseline.** Record the source identity and revision, and define stable artifact IDs and naming rules.
2. **Cut the structure.** Select major artifacts one level at a time, mark their boundaries, create paired source and analysis files, and update the manifest. Do not infer behaviour during this stage.
3. **Inventory individual artifacts.** Identify definitions, signatures, inputs, outputs, data structures, calls, and state access within each bounded fragment.
4. **Describe mechanisms.** Record decisions, transformations, side effects, error handling, ordering constraints, and language-independent pseudocode for important behaviour.
5. **Resolve relationships.** Join the local findings into call, data, state, and initialization relationships across artifacts.
6. **Specify portable behaviour.** Define the contracts and verification material needed to reproduce selected capabilities in another language or architecture.

Each stage is reviewable before proceeding. The manifest tracks cutting and analysis progress separately, so an artifact with an established boundary is not mistaken for an analysed artifact.


## Integrity requirements

- Stable artifact IDs survive renaming and line-number changes.
- Parent/child references preserve source order and nesting.
- Expanding child references recursively reproduces the tagged source without lost or duplicated content.
- The source and analysis trees contain matching artifact IDs and paths.
- One manifest links each artifact's source fragment, analysis document, type, original name, parent, order, and separate processing states.
- Syntax boundaries and uncertain cases are reviewed rather than guessed; a mechanical cut never silently changes program behaviour.
