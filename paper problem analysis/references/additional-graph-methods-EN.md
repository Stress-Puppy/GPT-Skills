# Additional Graph Method Notes

Read only the matching section. IDs refer to the [screened reference catalog](chang-wen-catalog-EN.md); the [Chinese companion](additional-graph-methods-CN.md) is equivalent. These nine notes were checked against the linked full texts on 2026-09-28. Page numbers below use PDF page order. They extend the existing five [graph examples](graph-algorithm-references-EN.md) and two [historical-index examples](temporal-graph-indexing-EN.md).

<a id="c003"></a>

## C003 — Maximum defective clique: kDC

Source: [author manuscript](https://lijunchang.github.io/pdf/2024-Maximum-kDC.pdf), §2–3, especially §3.1.3 and Algorithm 2, PDF pp. 5–8. The first page identifies PACMMOD 1(3), Article 209, **2023**, associated with SIGMOD 2024.

- **Contract:** Undirected `G` and missing-edge budget `k` → one maximum-cardinality vertex set missing at most `k` edges from a clique.
- **Final method:** **kDC** initializes a large feasible solution, reduces vertices/edges using its size, then branches with upper bounds and practical reduction rules. The non-fully-adjacent-first branching rule prioritizes a vertex already nonadjacent to the partial solution.
- **Boundary:** The budget is over the entire induced subgraph, unlike the per-vertex allowance in k-plex. Algorithm 1, **kDC-t**, only contains the theoretical core; the explanation should include Algorithm 2's practical improvements. The later **kDC-Two** paper is a separate catalog entry (X04).

<a id="c009"></a>

## C009 — All edge-connectivity levels: ECo-DC-AA

Source: [author technical report for PVLDB 2022](https://lijunchang.github.io/pdf/2022-ecd-tr.pdf), §4–5, Algorithms 3–4 and §5.2, PDF pp. 5–9.

- **Contract:** Undirected `G` → a hierarchy tree representing k-edge-connected components for all k values.
- **Final method:** **ECo-DC-AA** combines divide-and-conquer over connectivity levels with an adjacency-array implementation. At a split level, compute components, contract them for the lower-level subproblem, and recurse inside them for higher levels; derive the hierarchy from edge connectivity information. Arrays and compact auxiliary state control construction memory.
- **Boundary:** A hierarchy for all k differs from a fixed-k answer. The compact output tree and construction workspace have different sizes. Explain §5.2's implementation together with §4's recursion; do not attach its memory bound to the linked-list baseline. C060 is the later journal version.

<a id="c013"></a>

## C013 — Exact size-bounded community search: SC-BRB

Source: [author PDF](https://lijunchang.github.io/pdf/scs-tr.pdf), §2 and §4–5; Algorithm 4 and §4.4 on PDF p. 8.

- **Contract:** Undirected `G`, query vertex `q`, bounds `[ℓ,h]` → a connected community containing `q`, with `ℓ ≤ |S| ≤ h`, maximizing minimum degree.
- **Final method:** **SC-BRB** combines degree/distance reductions, successively stronger upper bounds, and domination-based branching. Branch selection favors connections to low-degree vertices in the partial solution and preserves connectivity. **SC-Heu** initializes a feasible incumbent.
- **Boundary:** Size bounds are constraints, not the objective; minimum degree is not average-degree density. SC-Heu appears later in the paper but does not replace the exact solver. “Maximum community size” would describe a different task.

<a id="c015"></a>

## C015 — Representing all densest subgraphs: ds-Index

Source: [author PDF](https://lijunchang.github.io/pdf/dds.pdf), §2–3, Definition 3, Theorems 1–4 and §3.4; PDF pp. 2–5.

- **Contract:** Under the paper's connected, undirected graph setting, represent all subgraphs maximizing `|E(S)|/|S|`; support enumeration of all or just minimal densest subgraphs.
- **Final method:** First prune safely using a density lower bound and core reduction. A parametric flow computation yields the critical residual graph; contract its strongly connected components into a DAG. **ds-Index** stores the relevant components, DAG, and induced graph. Descendant-closed component sets recover densest subgraphs; sink components give minimal ones.
- **Boundary:** `O(L)` enumeration delay is not `O(L)` total time for all solutions. Here `L` counts vertices plus edges of the maximal densest subgraph. Globally densest, locally densest, and merely dense are different notions.

<a id="c031"></a>

## C031 — Large independent sets: LinearTime and NearLinear

Source: [author PDF](https://lijunchang.github.io/pdf/2017-mis-sigmod.pdf), §4–5; Algorithms 4–5, PDF pp. 7–9.

- **Contract:** Undirected `G` → a large independent vertex set, extended to be maximal; the algorithms do not guarantee a maximum set or a formal approximation ratio.
- **Final methods:** **LinearTime** combines low-degree and degree-two-path reductions with high-degree peeling, then reconstructs a solution. **NearLinear** additionally maintains triangle information for dominance reductions. These variants trade running time for practical solution quality; choose according to the setting.
- **Boundary:** A safe reduction can preserve an optimum while the overall heuristic still lacks an optimality guarantee because of inexact peeling. Do not stop at baseline BDOne/BDTwo, or interpret “near-maximum” as a proved approximation ratio.

<a id="c034"></a>

## C034 — Exact structural clustering: pSCAN

Source: [author PDF](https://lijunchang.github.io/pdf/2016-pscan-icde.pdf), §II and §IV–VI; Algorithm 3, PDF p. 6.

- **Contract:** Undirected `G`, structural-similarity threshold `ε`, and core threshold `μ` → SCAN-style clusters and hub/outlier identification.
- **Final method:** **pSCAN** maintains bounds on similar-neighbor counts to settle core/non-core status without checking every similarity. A disjoint-set structure assembles core clusters; non-core vertices are assigned afterward. Degree bounds and early termination accelerate the remaining similarity checks.
- **Boundary:** “Core vertex” here is defined by structural similarity and `μ`, not a graph's k-core number. Distinguish exact clustering semantics from speedups that avoid unnecessary pair checks. The TKDE version C076 is a separate publication.

<a id="c063"></a>

## C063 — Graph-edit verification: AStar-BMao

Source: [author manuscript](https://lijunchang.github.io/pdf/2022-ged-tkde.pdf), §2 and §5, including §5.3; PDF pp. 3–4 and 7–10. The catalog uses the TKDE 2023 issue year.

- **Contract:** Labeled undirected graphs `q,g` and threshold `τ` → whether their graph edit distance is at most `τ`; this verifies candidates for database similarity search. Exact-distance computation is another supported operation.
- **Final method:** **AStar-BMao** searches partial vertex mappings using an optimized anchor-aware branch-match lower bound. Its relaxation permits cheaper computation across child mappings; early stopping and a maintained feasible upper bound further reduce work.
- **Boundary:** The tightest bound is not automatically the fastest algorithm: distinguish BMa from the cheaper BMao. An internal lower bound is not the returned GED, and pairwise verification is not the entire database filtering pipeline.

<a id="c088"></a>

## C088 — Closest community search: CCS

Source: [author PDF](https://lijunchang.github.io/pdf/2020-closest_community-dasfaa.pdf), §2 and §4.3; Algorithm 6, PDF p. 11.

- **Contract:** Undirected `G`, query set `Q` → a connected community containing `Q`, first maximizing minimum degree, then minimizing the maximum query distance, with the paper's maximality requirement. Query distance uses maximum distance to members of `Q` in `G`.
- **Final method:** **CCS** obtains the best feasible core level from an index, expands a working subgraph in query-distance order with geometric size growth, and applies **LinearOrder-S2** to its qualifying connected core until an answer is found.
- **Boundary:** Explain this final expansion strategy, not only the initial global shrink-and-peel baseline. Maximum distance to `Q` is not nearest-query-vertex distance; preserve the order of the objectives.

<a id="w005"></a>

## W005 — Distinct temporal core enumeration: CoreTime + Enum

Source: [published EDBT 2026 PDF](https://www.openproceedings.org/2026/conf/edbt/paper-175.pdf), problem statement, §4–5; Algorithms 2, 4–5, PDF pp. 3–9.

- **Contract:** Temporal graph, `k`, and query range `[Ts,Te]` → distinct temporal k-core edge sets across its subwindows, rather than one fixed-window answer.
- **Final method:** **CoreTime** derives edge core-window skylines from vertex core times. **Enum** maintains an end-time-ordered linked list of active minimal windows while advancing the start time; **AS-Output** uses tightest-interval conditions to emit distinct results. EnumBase is only the baseline.
- **Boundary:** Separate repeated edge occurrences, vertex sets, and temporal edge sets. The paper states `O(|VCT|·deg_avg + |R|)` overall, with `|R|` the total output size; its `O(|R|)` enumeration claim assumes the skyline is available. Do not drop preprocessing or interpret output size as the number of answers alone.
