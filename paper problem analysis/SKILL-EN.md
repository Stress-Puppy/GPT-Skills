---
name: paper-problem-analysis
description: Analyze an academic paper supplied as a PDF, paper webpage, DOI, or arXiv link. Explain the research problem, Input, and Output concretely, then briefly describe the solution approach. Use for requests to analyze a paper or explain its problem and inputs/outputs, not for ordinary PDFs or requests only to download or convert files.
---

# Paper Problem Analysis

This is the default English skill document. A [Chinese companion](SKILL-CN.md) is available for reference; loading both versions is unnecessary.

Explain in Chinese by default exactly what task the paper addresses, then briefly explain how the authors solve it. Retain necessary English terminology and the paper's notation, explaining each on first use. The user's explicit language, scope, and level-of-detail preferences take precedence.

## Reading and evidence

1. Identify the title and the version being read. Read the body of uploaded files; for URLs, open the original page and obtain the corresponding full text. A public version of the same paper may help obtain the text, but do not conflate preprints, conference papers, and journal extensions. Clarify the target if a link identifies several papers or version differences would affect the answer.
2. Scan the abstract and introduction to locate the task, then read the relevant preliminaries, problem definition, main method, and any necessary theorems or appendices. Do not reconstruct formal inputs and outputs from titles, abstracts, or search snippets alone.
3. Record source locations for the problem definition, constraints, and core method. Support key statements with section names, Definition/Algorithm numbers, or page numbers, and link original web sources. For local PDFs, specify whether page references use PDF page order or printed page numbers; never guess identifiers.
4. Inspect the relevant PDF pages when text extraction loses formulas, subscripts, superscripts, tables, or information in figures. Use OCR for scanned pages and verify key content. Choose retrieval and extraction tools available in the current environment without requiring a particular third-party plugin.
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

- Start with the core idea in one sentence, then usually give 3–5 brief steps from input to output: which properties are used, what information is stored, how candidates are computed or filtered, and how the answer is produced.
- Explain the difficulty each key technique addresses. Avoid merely listing algorithm names, acronyms, or words such as pruning, indexing, and optimization.
- If several algorithms are presented, identify the main method and its relationship to baselines or variants. Do not combine steps from different algorithms or papers into one method.
- By default, omit detailed proofs, line-by-line pseudocode, full experimental coverage, and complexity derivations. Include complexity only when it helps explain the method, identify whether it concerns construction, updates, or queries, and define symbols using readable notation such as `O(n + log^2 m)`.

## Default presentation

Identify the paper's title and the source/version read, then answer the following four questions. State when an item does not apply rather than forcing the format. Use headings in the response language.

1. **What problem does the paper study?** Give a plain explanation, then the precise task and key conditions. Briefly explain the difficulty.
2. **What is the Input?** Where helpful, use a compact table with columns for input item, meaning, and role or conditions.
3. **What is the Output?** Specify the returned object, validity conditions, and optimization objective. If the definition is abstract, a tiny constructed input/output example can help; label it as illustrative and verify that it satisfies the paper's constraints.
4. **How is it solved?** Give the core idea and brief steps that let the reader trace the process from input to output.

Prioritize the problem, inputs, and outputs; keep the method explanation concise. Analyze multiple supplied papers separately unless a comparison is requested. Without an additional request, answer directly in the conversation rather than generating report files, research proposals, or literature surveys.

## Final check

Check that the explanation lets a reader decide whether a candidate object is a valid answer, that key parameters and output conditions have source support, and that the described method solves the stated problem. Separate explanatory inferences from the authors' explicit definitions, retain evidence gaps, and do not present unverified details as facts.
