# Graph Algorithm References: Lijun Chang and Dong Wen

Read the matching example when analyzing cohesive-subgraph search, semi-external graph processing, temporal reachability, or fully dynamic connectivity. These notes complement the [historical graph indexing examples](temporal-graph-indexing-EN.md). The [Chinese companion](graph-algorithm-references-CN.md) contains the same material; loading both is unnecessary.

## Selection and evidence

Checked on 2026-09-28. Each selected paper has **Lijun Chang or Dong Wen as its first or second author** and belongs to a **CCF A/B conference venue, including B**. All five additions below qualify through an A-class venue. This is a filter for this reference collection, not a restriction on papers the skill can analyze.

The official [CCF database / data mining / information retrieval category](https://www.ccf.org.cn/Academic_Evaluation/DM_CS/) lists SIGKDD, ICDE, VLDB, and SIGMOD as A-class conferences. PVLDB and PACMMOD entries below qualify through the corresponding VLDB and SIGMOD research tracks; this does not assert that either publication is separately listed as an A-class journal. Author order comes from the linked paper's first page. Publication years and conference cycles are kept separate.

| ID | Paper and publication | Qualifying author | Venue basis |
| --- | --- | --- | --- |
| C19 | **Efficient Maximum Clique Computation over Large Sparse Graphs**. KDD 2019, pp. 529–538. [DOI](https://doi.org/10.1145/3292500.3330986) | Lijun Chang, sole author (first) | SIGKDD, CCF A |
| C22 | **Efficient Maximum k-Plex Computation over Large Sparse Graphs**. PVLDB 16(2), pp. 127–139, published 2022; VLDB 2023 cycle. [DOI](https://doi.org/10.14778/3565816.3565817) | Lijun Chang, first; followed by Mouyi Xu and Darren Strash | VLDB, CCF A |
| W16 | **I/O Efficient Core Graph Decomposition at Web Scale**. ICDE 2016, pp. 133–144. [DOI](https://doi.org/10.1109/ICDE.2016.7498235) | Dong Wen, first; Lu Qin, second | ICDE, CCF A |
| W20 | **Efficiently Answering Span-Reachability Queries in Large Temporal Graphs**. ICDE 2020, pp. 1153–1164. [DOI](https://doi.org/10.1109/ICDE48307.2020.00104) | Dong Wen, first; Yilun Huang, second | ICDE, CCF A |
| W24 | **Constant-time Connectivity Querying in Dynamic Graphs**. PACMMOD 2(6), Article 230, published December 2024; SIGMOD 2025 cycle. [DOI](https://doi.org/10.1145/3698805) | Lantian Xu, first; Dong Wen, second | SIGMOD, CCF A |

Additional publication checks: [KDD 2019 accepted papers](https://www.kdd.org/kdd2019/accepted-papers), [Lijun Chang's publication list](https://lijunchang.github.io/publication.html), [UTS record for W16](https://opus.lib.uts.edu.au/handle/10453/131193), and [SIGMOD 2025's PACMMOD 2(6) contents](https://2025.sigmod.org/toc-2-6.html).

## C19 — Exact maximum clique: MC-BRB

**Read:** [author PDF](https://lijunchang.github.io/pdf/2019-maxclique-kdd.pdf), §2–4; Algorithms 1–3. Page references, when needed, use the PDF's 10-page order.

- **Problem / Input / Output:** Undirected graph `G` → one largest clique. Maximum means largest cardinality; maximal means only that no vertex can be added.
- **Final technique:** **MC-BRB**, with **KCF-BRB** for local search. Reverse degeneracy order exposes bounded forward-neighbor ego-networks. Core/color bounds discard networks unable to improve the incumbent; small dense adjacency matrices support branching, reduction, and bounding inside the remaining networks.
- **Boundary:** **MC-EGO** supplies a heuristic incumbent; it is not the exact final solver. Distinguish the incumbent's lower bound from pruning upper bounds.

**Reading questions to transfer:** Which decomposition makes a large instance locally manageable? What certifies that a discarded region cannot improve the current answer? Is the returned object one optimum or an enumeration?

## C22 — Maximum k-plex with an explicit size regime: kPlexS

**Read:** [author PDF, including appendix](https://lijunchang.github.io/pdf/2022-Maximum-kPlex.pdf), §2 problem statement and §3–5; Algorithm 1 and the CTCP/BBMatrix sections. [Published PDF](https://www.vldb.org/pvldb/vol16/p127-chang.pdf) identifies the PVLDB version.

- **Problem / Input / Output:** Undirected `G`, integer `k ≥ 2` → largest k-plex of size at least `2k−1`, if one exists; otherwise an arbitrary k-plex. Feasibility is `degree_S(v) ≥ |S|−k`, allowing at most `k−1` other non-neighbors.
- **Final technique:** **kPlexS** combines repeated **core-truss co-pruning (CTCP)**, up-to-two-hop subproblems, and **BBMatrix**. Vertex/edge reductions interact; matrix search uses vertex and vertex-pair information with incremental maintenance.
- **Boundary:** An answer of size `2k−2` is also maximum; a smaller answer need not be. The paper specifies using another exact solver if the unrestricted small optimum is required. A polynomial reduction bound does not bound the whole exact search.

**Reading questions to transfer:** Does a structural lemma hold for every feasible solution or only above a size threshold? Does “no qualifying large solution” determine the smaller optimum? Separate a search-space reduction's cost from the complete algorithm's cost.

## W16 — Core numbers when edges do not fit in memory: SemiCore*

**Read:** [UTS accepted manuscript](https://opus.lib.uts.edu.au/rest/bitstreams/65874dc3-1e78-447b-bdef-afd45844bf51/retrieve), §IV.C, Lemma 4.2 and Algorithm 5, PDF pp. 7–8. This PDF has a cover page before the paper.

- **Problem / Input / Output:** Undirected graph with vertex state in RAM and edges on disk → every vertex's core number. This is semi-external decomposition, not one fixed-k core query.
- **Final technique:** **SemiCore*** decreases degree-initialized estimates using neighbor estimates. It maintains `cnt(v)`, the number of neighbors meeting `v`'s current estimate. After initialization, `cnt(v) < core(v)` triggers recomputation; threshold-crossing decreases update affected counts and scan ranges.
- **Boundary:** The `O(n)` bound is RAM, where `n` counts vertices; it does not describe disk storage or total CPU work. Count initialization needs its first pass. “Optimal node computation” should not become a claim of globally optimal I/O.

**Reading questions to transfer:** What resides in RAM and what must be read from disk? Which certificate makes a recomputation necessary? Are memory, I/O, and CPU bounds being attributed to the same operation?

## W20 — Reachability inside a projected interval: TILL

**Read:** [official ICDE PDF](https://conferences.computer.org/icde/2020/pdfs/ICDE2020-5acyuqhpJ6L9P042wmjY1p/290300b153/290300b153.pdf), §II, §IV–V; **TILL-Construct*** (Algorithm 3) and **Span-Reach** (Algorithm 4). PDF pp. 3, 5–8.

- **Problem / Input / Output:** Temporal directed `G`, vertices `u,v`, interval `I` → Boolean reachability in the graph projected onto `I`. Edge timestamps need not follow traversal order.
- **Final technique:** **TILL-Construct*** builds in/out labels `(hub,start,end)`, processing shorter spans first and pruning intervals/exploration already represented through processed hubs. **Span-Reach** matches a common hub with intervals contained in `I`, using ordered label groups and binary search.
- **Boundary:** Query parameter `θ` in the separate θ-reachability problem bounds a witnessing subinterval. Construction parameter `ϑ` limits index coverage; a truncated index does not establish completeness for arbitrary spans.

**Reading questions to transfer:** What does the interval constrain: edge membership, chronological traversal, or duration? What certificate permits an index record to be omitted, and how is its answer recovered? Are build parameters being confused with query parameters?

## W24 — Fully dynamic connectivity: DND-Trees

**Read:** [coauthor PDF](https://ronghuali.github.io/PaperFiles/Constant-time%20Connectivity%20Querying%20in%20Dynamic%20Graphs.pdf), §6, especially Theorem 6.2 on PDF p. 13 and the deletion procedures. The target is the 2024 PACMMOD article listed above; recheck author order and claims before substituting an extension.

- **Problem / Input / Output:** Undirected graph, arbitrary edge insertions/deletions, vertex-pair queries → maintained connectivity and Boolean query answers.
- **Final technique:** **DND-Trees** couples an **ID-Tree** spanning structure with a compressed **DS-Tree** using child lists. Queries compare DS roots. If deletion splits a component, isolate the smaller component's vertices and regroup them in DS; ID supplies structural information and replacement-edge search.
- **Boundary:** Explain DND-Trees, not only the intermediate ID-Tree. Theorem 6.2 states **amortized `O(α(n))`** querying, with inverse-Ackermann `α`, rather than strict worst-case `O(1)`. DS parent links need not be original graph edges.

**Reading questions to transfer:** Which structure answers queries and which repairs updates? What happens when a tree edge has no replacement? Do synthetic links preserve component membership, graph paths, or both?

## Using the examples

Use an example to sharpen terminology and ask better questions; establish the current paper's definitions and guarantees from its own text. Keep the final algorithm central and mention baselines only as short motivation. For a new version or an added reference, verify author order, publication venue, problem contract, final variant, and source locations again. Retain the existing historical-core and historical-connectivity notes rather than counting them as new additions.
