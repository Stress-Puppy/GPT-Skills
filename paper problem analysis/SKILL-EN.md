---
name: paper-problem-analysis
description: Analyze papers in databases, big data, graphs, and graph theory supplied as PDFs, paper webpages, DOI links, or arXiv links. Explain the research problem, Input, and Output concretely, then explain the final optimized algorithm. Use for paper analysis and designated representative-paper learning, not for ordinary PDFs or requests only to download or convert files.
---

# Paper Problem Analysis

This is the default English skill document. A [Chinese companion](SKILL-CN.md) is available for reference; loading both versions is unnecessary.

Explain in Chinese by default exactly what task the paper addresses, then briefly explain the authors' final optimized method. Retain necessary English terminology and the paper's notation, explaining each on first use. The user's explicit language, scope, and level-of-detail preferences take precedence.

## Domain focus

The primary domains are databases, big data, graphs, and graph theory. Analyze the paper through its data or graph model, query semantics, assumptions, structural properties, and cost model. For database and indexing work, distinguish index construction, query processing, and update or maintenance; for big-data work, discuss I/O, communication, or distributed execution only when they matter to the paper. For graph theory, make the objects, constraints, and mathematical guarantees precise.

Connect the explanation as appropriate: problem bottleneck → useful property or invariant → final data structure or algorithm → correctness and cost. Use the paper's precise technical terms rather than replacing them with vague descriptions, and distinguish paper-specific terminology from established field terminology.

For temporal graphs, establish snapshot and path semantics before explaining the method: distinguish edge occurrences from distinct edges, window projection from persistence throughout a window, and snapshot connectivity from time-respecting reachability. For an index, explain what each record encodes, what redundant information is omitted, and how the query recovers the answer. Check which properties a compressed or transformed structure preserves rather than assuming it preserves the original edges or paths.

For temporal graph indexing, historical k-core queries, or historical connectivity, consult [the representative-paper notes](references/temporal-graph-indexing-EN.md) ([Chinese](references/temporal-graph-indexing-CN.md)). They contain source-grounded terminology, final-algorithm examples, and pitfalls from the supplied 2021 PVLDB and 2024 SIGMOD papers; they are not universal assumptions for all graph papers.

## Reading and evidence

1. Identify the title and the version being read. Read the body of uploaded files; for URLs, open the original page and obtain the corresponding full text. A public version of the same paper may help obtain the text, but do not conflate preprints, conference papers, and journal extensions. Clarify the target if a link identifies several papers or version differences would affect the answer.
2. Scan the abstract and introduction to locate the task, then read the relevant preliminaries, problem definition, methods, optimization sections, and any necessary theorems or appendices. Trace the progression from baselines and intermediate methods to the final optimized algorithm; do not stop at the first framework or pseudocode listing. Do not reconstruct formal inputs and outputs from titles, abstracts, or search snippets alone.
3. Record source locations for the problem definition, constraints, and core method. Support key statements with section names, Definition/Algorithm numbers, or page numbers, and link original web sources. For local PDFs, specify whether page references use PDF page order or printed page numbers; never guess identifiers.
4. Inspect the relevant PDF pages when text extraction loses formulas, subscripts, superscripts, tables, or information in figures. Use OCR for scanned pages and verify key content. Choose retrieval and extraction tools available in the current environment without requiring a particular third-party plugin.
   If definitions, examples, pseudocode, or complexity statements disagree, cross-check them and disclose consequential inconsistencies. Keep a reconstruction or derived bound distinct from what the paper actually states.
5. If the full text is unavailable, state what was actually read, report only supported information, and ask for the PDF or relevant passages. Mark unverified items as unconfirmed from the available material; do not invent definitions, algorithms, or conclusions.

## Analysis priorities

### Research problem

- State the concrete task as "Given ..., under ... conditions, find/decide/maintain ..." rather than describing only background goals such as improving efficiency or studying graph data.
- Explain the objects, key definitions, feasibility conditions, and any objective to maximize or minimize. Distinguish constraints from objectives, maximal from maximum, one solution from all solutions, and exact from approximate results when these distinctions apply to the paper.
- Briefly explain the difficulty and whether the paper defines a new task or proposes an algorithm, index, or system for an existing task. Do not claim it is the first to introduce something without sufficient evidence.

### Input

- List the data objects, data model, queries, parameters, and assumptions that affect the task's meaning. Explain what each item represents and its role.
- Do not substitute experimental dataset names for formal inputs. For example, "graph G, query vertex q, and threshold k" is more precise than "several real-world graph datasets."
- Separate the inputs to preprocessing/index construction and online querying when both exist. Likewise, distinguish training from inference when applicable. Describe only stages actually present in the paper.
- Explain parameter ranges, time-window boundaries, directionality, and similar details when they affect the answer. Do not supply conditions the paper leaves unspecified.

### Output

- Specify the returned object and its form: for example, a Boolean, value, path, vertex set, subgraph, all qualifying results, ranked list, or model. Include validity conditions and requirements on how many results are returned.
- Match the output to the Input: what does the user ultimately receive after supplying these inputs? Distinguish the final answer, intermediate artifacts, and the paper's contributions. An index commonly supports querying; whether it is itself a task output depends on the paper's definition.
- For decision, enumeration, optimization, and maintenance tasks, explain what is decided, enumerated, optimized, or preserved after updates. Briefly mention no-solution or empty-result behavior if the paper specifies it.
- For theoretical, empirical, or survey papers without algorithmic inputs and outputs, say so. Explain "research assumptions or materials → conclusions to establish or research findings" instead of inventing a computational task.

### Solution approach

- Center both brief and detailed technical explanations on the final optimized algorithm. Name that method or final variant explicitly and locate its defining sections. A baseline or initial idea may provide one or two opening sentences of intuition and motivation; it should not occupy the main technical explanation.
- Do not explain an intermediate framework in detail and append a list of optimization names at the end. Explain the final method as it actually operates, integrating the optimizations into its data structures and processing steps.
- Start with the final method's core idea in one sentence, then usually give 3–5 concise steps from input to output. Explain what information the final structure stores or deliberately omits, its key property or invariant, and the relevant construction, query, and update operations. If the user asks for more technical depth, expand these same parts of the final algorithm.
- For each important optimization, explain the bottleneck it addresses, the mechanism that removes or reduces the work, and why the resulting answers remain correct. Distinguish a data structure used inside the solution from the task's required output. Avoid merely listing algorithm names, acronyms, or words such as pruning, indexing, and optimization.
- If the paper has several final variants, distinguish them by their intended setting, guarantees, or reported practical performance. Use the authors' recommended method for the relevant setting when one exists; otherwise explain the common final framework and the material differences without inventing a single winner. Never combine one variant's steps with another variant's complexity or experimental results, and do not assume the last algorithm in the paper is automatically the final or preferred method.
- By default, omit detailed proofs, line-by-line pseudocode, full experimental coverage, and complexity derivations. When complexity helps explain the method, attribute it to the exact final variant and operation, state worst-case versus amortized bounds as applicable, and use readable notation such as `O(n + log^2 m)` with defined symbols.

## Default presentation

Identify the paper's title and the source/version read, then answer the following four questions. State when an item does not apply rather than forcing the format. Use headings in the response language.

1. **What problem does the paper study?** Give a plain explanation, then the precise task and key conditions. Briefly explain the difficulty.
2. **What is the Input?** Where helpful, use a compact table with columns for input item, meaning, and role or conditions.
3. **What is the Output?** Specify the returned object, validity conditions, and optimization objective. If the definition is abstract, a tiny constructed input/output example can help; label it as illustrative and verify that it satisfies the paper's constraints.
4. **How is it solved?** Name the final optimized method, give its core idea, and explain its processing steps with the key optimizations built in. Mention a baseline briefly at the beginning only if it helps establish the intuition or bottleneck.

Prioritize the problem, inputs, and outputs; keep the method explanation concise. Analyze multiple supplied papers separately unless a comparison is requested. Without an additional request, answer directly in the conversation rather than generating report files, research proposals, or literature surveys.

## Learning from representative papers

When the user explicitly supplies papers as representative material for improving this skill, read them for reusable technical terminology, explanation patterns, and ways of reasoning about problems and algorithms. Record English terms with appropriate Chinese equivalents and definitions, and connect each reusable lesson to a paper version and source location. Separate domain-level guidance from a paper's particular model or algorithm; do not generalize one paper's assumptions to the entire field.

Add focused reference notes only after reading the supplied papers, link them from this skill with a clear indication of when to consult them, and maintain English and Chinese counterparts. Do not copy large paper passages or claim to have learned from papers not yet supplied. An ordinary request to analyze a paper does not by itself request a skill update.

## Maintaining this skill

For user-requested improvements to this skill, update and validate the installed local skill first, then synchronize the corresponding files in [the GitHub skill directory](https://github.com/Stress-Puppy/GPT-Skills/tree/main/paper%20problem%20analysis). Keep the English documents, Chinese companion, relevant reference notes, and interface metadata consistent. Locally, `SKILL.md` is the discovery entrypoint and has the same content as `SKILL-EN.md`; the repository currently uses `SKILL-EN.md` and `SKILL-CN.md`. Verify the remote content after synchronization and report any incomplete synchronization. This maintenance workflow applies to skill-improvement requests, not ordinary paper analysis.

## Final check

Check that the explanation lets a reader decide whether a candidate object is a valid answer, that key parameters and output conditions have source support, and that the described method solves the stated problem. Confirm that the technical explanation reflects the final optimized algorithm's actual stored information and operations, with each bound attached to the correct variant. Separate explanatory inferences from the authors' explicit definitions, retain evidence gaps, and do not present unverified details as facts.
