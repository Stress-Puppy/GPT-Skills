# Screened References: Lijun Chang and Dong Wen

## Scope and reading status

Checked on **2026-09-28**. This catalog contains **75 publication records: 64 CCF A and 11 CCF B**, each with **Lijun Chang or Dong Wen as first or second author**. It includes the seven papers already referenced by the skill, adding **68 records**. Conference and journal versions are separate publications, not automatically separate research problems; repeated listings of the same publication are deduplicated. The two authors' public lists are selective and not equally up to date, so 75 is the verified coverage of this pass, not a claim that no further qualifying work exists.

**16 records have problem/input/output/final-method notes** linked in the last column (nine newly added). The other **59 are bibliography-checked references** for retrieval: their inclusion does not mean the full method has been read. Open their full texts before asserting formal definitions, final algorithms, correctness, or complexity. Topic groups are navigation aids, not reconstructed problem definitions. Do not load all entries or all notes for an ordinary single-paper analysis.

## Sources and qualification

- Author identity/order and discovery: [Lijun Chang's publication list](https://lijunchang.github.io/publication.html), [Dong Wen's UNSW homepage](https://cgi.cse.unsw.edu.au/~dwen/), and the [UNSW publication records, page 0](https://research.unsw.edu.au/people/dr-dong-wen/publications?page=0) and [page 1](https://research.unsw.edu.au/people/dr-dong-wen/publications?page=1). Institutional feeds contain occasional homonyms and incorrect fields; match the graph/database researcher and cross-check the specific paper. DBLP is used for bibliographic discovery/checks, not as evidence for algorithmic claims.
- Venue grades: official CCF [database category](https://www.ccf.org.cn/Academic_Evaluation/DM_CS/), [theory category](https://www.ccf.org.cn/Academic_Evaluation/TCS/), and [cross-disciplinary category](https://www.ccf.org.cn/Academic_Evaluation/Cross_Compre_Emerging/). A: SIGMOD, VLDB, ICDE, KDD, WWW conferences; TKDE and VLDB Journal. B: CIKM, EDBT, DASFAA conferences; Algorithmica, World Wide Web Journal, and JCST. WWW conference and World Wide Web Journal are different venues.
- The [CCF seventh-edition announcement](https://www.ccf.org.cn/Academic_Evaluation/By_category/) specifies full/regular conference papers. Short papers, extended abstracts, tutorials, demos, and workshops are not counted here. PVLDB/PACMMOD research papers are classified through VLDB/SIGMOD, not by inventing a separate A-journal classification.
- Years prefer the publication/issue year when verified; a different conference cycle or online year is stated explicitly. For example, kDC is PACMMOD 2023 / SIGMOD 2024, and C060 is online 2023 / VLDB Journal issue 2024. Preprints and accepted-only listings are not additional counted publications.

The author column shows the first two authors in order (initials retained where the source uses them) and identifies the qualifying position. Titles link to a DOI, full text, or source record; “source” links to the supporting author/institutional record. The A/B filter belongs to this reference collection, not to all papers the skill may analyze.

## Contents

- [Temporal and streaming graphs](#group-1)
- [Connectivity and graph decomposition](#group-2)
- [Cohesive subgraphs and community search](#group-3)
- [Clustering, matching, and graph similarity](#group-4)
- [Paths and road-network queries](#group-5)
- [Scalable processing and numerical summaries](#group-6)
- [Database ranking and other graph analytics](#group-7)

<a id="group-1"></a>

## Temporal and streaming graphs

| ID | Paper | Publication | CCF | First two authors; qualifying position | Reading status |
| --- | --- | --- | --- | --- | --- |
| W005 | **[Accelerating K-Core Computation in Temporal Graphs](https://doi.org/10.48786/EDBT.2026.25)** · [source](https://www.openproceedings.org/html/pages/2026_edbt.html) | EDBT, 2026 | B | Z. Ma; Dong Wen; Dong Wen #2 | [Method notes](additional-graph-methods-EN.md#w005) |
| W002 | **[Maintaining Biconnected Components in Streaming Graphs](https://doi.org/10.1145/3802084)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2026 | A | Z. Lu; Dong Wen; Dong Wen #2 | Bibliography checked |
| W060 | **[On Querying Historical Connectivity in Large-scale Temporal Graphs](https://doi.org/10.1007/s00778-025-00951-7)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2026 (online 2025) | A | L. Xu; Dong Wen; Dong Wen #2 | Bibliography checked |
| W057 | **[On Querying Minimum Spanning Tree in Temporal Graphs](https://doi.org/10.1007/s00778-026-00989-1)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2026 | A | Y. Yu; Dong Wen; Dong Wen #2 | Bibliography checked |
| W062 | **[Querying Historical K-Cores in Large Temporal Graphs](https://doi.org/10.1007/s00778-025-00903-1)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2025 | A | Y. Yu; Dong Wen; Dong Wen #2 | Bibliography checked |
| W030 | **[On Compressing Historical Cliques in Temporal Graphs](https://doi.org/10.1007/978-981-97-5552-3_3)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | DASFAA, 2024 | B | K. Chen; Dong Wen; Dong Wen #2 | Bibliography checked |
| W031 | **[On Querying Historical Connectivity in Temporal Graphs](https://doi.org/10.1145/3654960)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2024 | A | J. Song; Dong Wen; Dong Wen #2 | [Method notes](temporal-graph-indexing-EN.md) |
| W033 | **[Querying Structural Diversity in Streaming Graphs](https://doi.org/10.14778/3641204.3641213)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | PVLDB / VLDB, 2024 | A | K. Chen; Dong Wen; Dong Wen #2 | Bibliography checked |
| W066 | **[Span-Reachability Querying in Large Temporal Graphs](https://doi.org/10.1007/s00778-021-00715-z)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2022 | A | Dong Wen; B. Yang; Dong Wen #1 | Bibliography checked |
| W046 | **[On Querying Historical K-Cores](https://doi.org/10.14778/3476249.3476260)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | PVLDB / VLDB, 2021 | A | M. Yu; Dong Wen; Dong Wen #2 | [Method notes](temporal-graph-indexing-EN.md) |
| W049 | **[Efficiently Answering Span-Reachability Queries in Large Temporal Graphs](https://doi.org/10.1109/ICDE48307.2020.00104)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2020 | A | Dong Wen; Y. Huang; Dong Wen #1 | [Method notes](graph-algorithm-references-EN.md) |

<a id="group-2"></a>

## Connectivity and graph decomposition

| ID | Paper | Publication | CCF | First two authors; qualifying position | Reading status |
| --- | --- | --- | --- | --- | --- |
| W024 | **[Minimum Spanning Tree Maintenance in Dynamic Graphs](https://doi.org/10.1145/3709704)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2025 | A | L. Xu; Dong Wen; Dong Wen #2 | Bibliography checked |
| W020 | **[Preserving K-Connectivity in Dynamic Graphs](https://doi.org/10.1109/ICDE65448.2025.00019)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2025 | A | G. Zhao; Dong Wen; Dong Wen #2 | Bibliography checked |
| C060 | **[A Near-Optimal Approach to Edge Connectivity-Based Hierarchical Graph Decomposition](https://doi.org/10.1007/s00778-023-00797-x)** · [source](https://lijunchang.github.io/publication.html) | VLDBJ, 2024 (online 2023) | A | Lijun Chang; Zhiyi Wang; Lijun Chang #1 | Bibliography checked |
| W025 | **[Constant-time Connectivity Querying in Dynamic Graphs](https://doi.org/10.1145/3698805)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2024 (conference 2025) | A | L. Xu; Dong Wen; Dong Wen #2 | [Method notes](graph-algorithm-references-EN.md) |
| C009 | **[A Near-Optimal Approach to Edge Connectivity-Based Hierarchical Graph Decomposition](https://doi.org/10.14778/3514061.3514063)** · [source](https://lijunchang.github.io/publication.html) | PVLDB / VLDB, 2022 | A | Lijun Chang; Zhiyi Wang; Lijun Chang #1 | [Method notes](additional-graph-methods-EN.md#c009) |
| W050 | **[Fully Dynamic Depth-First Search in Directed Graphs](https://doi.org/10.14778/3364324.3364329)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | PVLDB / VLDB, 2020 | A | B. Yang; Dong Wen; Dong Wen #2 | Bibliography checked |
| C022 | **[Enumerating k-Vertex Connected Components in Large Graphs](https://doi.org/10.1109/ICDE.2019.00014)** · [source](https://lijunchang.github.io/publication.html) | ICDE, 2019 | A | Dong Wen; Lu Qin; Dong Wen #1 | Bibliography checked |
| C035 | **[Computing Connected Components with Linear Communication Cost in Pregel-like Systems](https://lijunchang.github.io/publication.html)** | ICDE, 2016 | A | Xing Feng; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| C038 | **[Index-based Optimal Algorithms for Computing Steiner Components with Maximum Connectivity](https://lijunchang.github.io/publication.html)** | SIGMOD, 2015 | A | Lijun Chang; Xuemin Lin; Lijun Chang #1 | Bibliography checked |
| C046 | **[Efficiently Computing k-Edge Connected Components via Graph Decomposition](https://lijunchang.github.io/publication.html)** | SIGMOD, 2013 | A | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | Bibliography checked |

<a id="group-3"></a>

## Cohesive subgraphs and community search

| ID | Paper | Publication | CCF | First two authors; qualifying position | Reading status |
| --- | --- | --- | --- | --- | --- |
| W015 | **[Covering K-Cliques in Billion-Scale Graphs](https://doi.org/10.1145/3696410.3714897)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | WWW, 2025 | A | K. Chen; Dong Wen; Dong Wen #2 | Bibliography checked |
| X02 | **[Estimating Biclique Counts with Accuracy Guarantees](https://doi.org/10.1145/3769791)** · [source](https://dblp.org/rec/journals/pacmmod/GamageC25) | PACMMOD / SIGMOD, 2025 (conference 2026) | A | Rashmika Gamage; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| X03 | **[Identifying Maximum Defective Bicliques in Large Bipartite Graphs](https://doi.org/10.1109/ICDE65448.2025.00277)** · [source](https://research.cuhk.edu.hk/en/publications/identifying-maximum-defective-bicliques-in-large-bipartite-graphs/) | ICDE, 2025 | A | Zhiyi Wang; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| X05 | **[Efficient k-Clique Count Estimation with Accuracy Guarantee](https://doi.org/10.14778/3681954.3682032)** · [source](https://www.vldb.org/pvldb/vol17/p3707-chang.pdf) | PVLDB / VLDB, 2024 | A | Lijun Chang; Rashmika Gamage; Lijun Chang #1 | Bibliography checked |
| C061 | **[Identifying Large Structural Balanced Cliques in Signed Graphs](https://doi.org/10.1109/TKDE.2023.3295803)** · [source](https://lijunchang.github.io/publication.html) | TKDE, 2024 (online 2023) | A | Kai Yao; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| X04 | **[Maximum Defective Clique Computation: Improved Time Complexities and Practical Performance](https://doi.org/10.14778/3705829.3705839)** · [source](https://www.vldb.org/pvldb/vol18/p200-chang.pdf) | PVLDB / VLDB, 2024 (conference 2025) | A | Lijun Chang; Lijun Chang #1 | Bibliography checked |
| C002 | **[Maximum k-Plex Computation: Theory and Practice](https://lijunchang.github.io/Maximum-kPlex-v2/)** | PACMMOD / SIGMOD, 2024 | A | Lijun Chang; Kai Yao; Lijun Chang #1 | Bibliography checked |
| W040 | **[Distributed Near-Maximum Independent Set Maintenance over Large-scale Dynamic Graphs](https://doi.org/10.1109/ICDE55515.2023.00195)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2023 | A | X. Wang; Dong Wen; Dong Wen #2 | Bibliography checked |
| C003 | **[Efficient Maximum k-Defective Clique Computation with Improved Time Complexity](https://doi.org/10.1145/3617313)** · [source](https://lijunchang.github.io/publication.html) | PACMMOD / SIGMOD, 2023 (conference 2024) | A | Lijun Chang; Lijun Chang #1 | [Method notes](additional-graph-methods-EN.md#c003) |
| C005 | **[Verification-Free Approaches to Efficient Locally Densest Subgraph Discovery](https://lijunchang.github.io/publication.html)** | ICDE, 2023 | A | Tran Ba Trung; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| C066 | **[Computing K-Cores in Large Uncertain Graphs: An Index-based Optimal Approach](https://doi.org/10.1109/TKDE.2020.3023925)** · [source](https://lijunchang.github.io/publication.html) | TKDE, 2022 | A | Dong Wen; Bohua Yang; Dong Wen #1 | Bibliography checked |
| C012 | **[Computing Maximum Structural Balanced Cliques in Signed Graphs](https://lijunchang.github.io/pdf/icde22-msbc-tr.pdf)** · [source](https://lijunchang.github.io/publication.html) | ICDE, 2022 | A | Kai Yao; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| C004 | **[Efficient Maximum k-Plex Computation over Large Sparse Graphs](https://doi.org/10.14778/3565816.3565817)** · [source](https://lijunchang.github.io/publication.html) | PVLDB / VLDB, 2022 (conference 2023) | A | Lijun Chang; Mouyi Xu; Lijun Chang #1 | [Method notes](graph-algorithm-references-EN.md) |
| C010 | **[Identifying Similar-Bicliques in Bipartite Graphs](https://lijunchang.github.io/publication.html)** | PVLDB / VLDB, 2022 | A | Kai Yao; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| C013 | **[Efficient Size-Bounded Community Search over Large Networks](https://doi.org/10.14778/3457390.3457407)** · [source](https://lijunchang.github.io/publication.html) | PVLDB / VLDB, 2021 | A | Kai Yao; Lijun Chang; Lijun Chang #2 | [Method notes](additional-graph-methods-EN.md#c013) |
| C015 | **[Deconstruct Densest Subgraphs](https://doi.org/10.1145/3366423.3380033)** · [source](https://lijunchang.github.io/publication.html) | WWW, 2020 | A | Lijun Chang; Miao Qiao; Lijun Chang #1 | [Method notes](additional-graph-methods-EN.md#c015) |
| C088 | **[Efficient Closest Community Search over Large Graphs](https://lijunchang.github.io/pdf/2020-closest_community-dasfaa.pdf)** · [source](https://lijunchang.github.io/publication.html) | DASFAA, 2020 | B | Mingshen Cai; Lijun Chang; Lijun Chang #2 | [Method notes](additional-graph-methods-EN.md#c088) |
| C069 | **[Efficient Maximum Clique Computation and Enumeration over Large Sparse Graphs](https://lijunchang.github.io/publication.html)** | VLDBJ, 2020 | A | Lijun Chang; Lijun Chang #1 | Bibliography checked |
| C019 | **[Efficient Maximum Clique Computation over Large Sparse Graphs](https://lijunchang.github.io/pdf/2019-maxclique-kdd.pdf)** · [source](https://lijunchang.github.io/publication.html) | KDD, 2019 | A | Lijun Chang; Lijun Chang #1 | [Method notes](graph-algorithm-references-EN.md) |
| W072 | **[I/O Efficient Core Graph Decomposition: Application to Degeneracy Ordering](https://doi.org/10.1109/TKDE.2018.2833070)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | TKDE, 2019 | A | Dong Wen; L. Qin; Dong Wen #1 | Bibliography checked |
| C021 | **[Index-based Optimal Algorithm for Computing K-Cores in Large Uncertain Graphs](https://doi.org/10.1109/ICDE.2019.00015)** · [source](https://lijunchang.github.io/publication.html) | ICDE, 2019 | A | Bohua Yang; Dong Wen; Dong Wen #2 | Bibliography checked |
| C024 | **[An Optimal and Progressive Approach to Online Search of Top-K Influential Communities](https://lijunchang.github.io/publication.html)** | PVLDB / VLDB, 2018 | A | Fei Bi; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| W055 | **[K-Connected Cores Computation in Large Dual Networks](https://doi.org/10.1007/978-3-319-91452-7_12)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | DASFAA, 2018 | B | L. Yue; Dong Wen; Dong Wen #2 | Bibliography checked |
| C031 | **[Computing A Near-Maximum Independent Set in Linear Time by Reducing-Peeling](https://lijunchang.github.io/pdf/2017-mis-sigmod.pdf)** · [source](https://lijunchang.github.io/publication.html) | SIGMOD, 2017 | A | Lijun Chang; Wei Li; Lijun Chang #1 | [Method notes](additional-graph-methods-EN.md#c031) |
| W056 | **[I/O Efficient Core Graph Decomposition at Web Scale](https://doi.org/10.1109/ICDE.2016.7498235)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2016 | A | Dong Wen; L. Qin; Dong Wen #1 | [Method notes](graph-algorithm-references-EN.md) |
| C083 | **[Fast Maximal Cliques Enumeration in Sparse Graphs](https://lijunchang.github.io/publication.html)** | Algorithmica, 2013 | B | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | Bibliography checked |

<a id="group-4"></a>

## Clustering, matching, and graph similarity

| ID | Paper | Publication | CCF | First two authors; qualifying position | Reading status |
| --- | --- | --- | --- | --- | --- |
| X01 | **[Graph Edit Distance Estimation: A New Heuristic and A Holistic Evaluation of Learning-based Methods](https://doi.org/10.1145/3725304)** · [source](https://2025.sigmod.org/toc-3-3.html) | PACMMOD / SIGMOD, 2025 | A | Mouyi Xu; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| C063 | **[Accelerating Graph Similarity Search via Efficient GED Computation](https://lijunchang.github.io/pdf/2022-ged-tkde.pdf)** · [source](https://lijunchang.github.io/publication.html) | TKDE, 2023 | A | Lijun Chang; Xing Feng; Lijun Chang #1 | [Method notes](additional-graph-methods-EN.md#c063) |
| C014 | **[Speeding Up GED Verification for Graph Similarity Search](https://lijunchang.github.io/pdf/2020-ged-icde.pdf)** · [source](https://lijunchang.github.io/publication.html) | ICDE, 2020 | A | Lijun Chang; Xing Feng; Lijun Chang #1 | Bibliography checked |
| C071 | **[Efficient structural graph clustering: an index-based approach](https://doi.org/10.1007/s00778-019-00541-4)** · [source](https://lijunchang.github.io/publication.html) | VLDBJ, 2019 | A | Dong Wen; Lu Qin; Dong Wen #1 | Bibliography checked |
| C028 | **[Efficient Structural Graph Clustering: An Index-Based Approach](https://doi.org/10.14778/3157794.3157795)** · [source](https://lijunchang.github.io/publication.html) | PVLDB / VLDB, 2017 (conference 2018) | A | Dong Wen; Lu Qin; Dong Wen #1 | Bibliography checked |
| C076 | **[pSCAN: Fast and Exact Structural Graph Clustering](https://lijunchang.github.io/publication.html)** | TKDE, 2017 | A | Lijun Chang; Wei Li; Lijun Chang #1 | Bibliography checked |
| C033 | **[Efficient Subgraph Matching by Postponing Cartesian Products](https://lijunchang.github.io/publication.html)** | SIGMOD, 2016 | A | Fei Bi; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| C090 | **[Ranking Weighted Clustering Coefficient in Large Dynamic Graphs](https://lijunchang.github.io/publication.html)** | World Wide Web Journal, 2016 | B | Xuefei Li; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| C034 | **[pSCAN: Fast and Exact Structural Graph Clustering](https://lijunchang.github.io/pdf/2016-pscan-icde.pdf)** · [source](https://lijunchang.github.io/publication.html) | ICDE, 2016 | A | Lijun Chang; Wei Li; Lijun Chang #1 | [Method notes](additional-graph-methods-EN.md#c034) |
| C092 | **[Efficient String Similarity Search: A Cross Pivotal Based Approach](https://lijunchang.github.io/publication.html)** | DASFAA, 2015 | B | Fei Bi; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| C039 | **[Optimal Enumeration: Efficient Top-k Tree Matching](https://www.vldb.org/pvldb/vol8/p533-chang.pdf)** · [source](https://opus.lib.uts.edu.au/handle/10453/35410) | PVLDB / VLDB, 2015 | A | Lijun Chang; Xuemin Lin; Lijun Chang #1 | Bibliography checked |

<a id="group-5"></a>

## Paths and road-network queries

| ID | Paper | Publication | CCF | First two authors; qualifying position | Reading status |
| --- | --- | --- | --- | --- | --- |
| W004 | **[High-Throughput k Nearest Neighbors Search in Road Networks](https://doi.org/10.1145/3786656)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2026 | A | Y. Kong; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| W017 | **[Weight-Constrained Simple Path Enumeration in Weighted Graph](https://doi.org/10.1145/3690624.3709310)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | KDD, 2025 | A | D. Ouyang; Dong Wen; Dong Wen #2 | Bibliography checked |
| W039 | **[Efficient and Effective Path Compression in Large Graphs](https://doi.org/10.1109/ICDE55515.2023.00237)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2023 | A | Y. Huang; Dong Wen; Dong Wen #2 | Bibliography checked |
| C062 | **[When hierarchy meets 2-hop-labeling: efficient shortest distance and path queries on road networks](https://doi.org/10.1007/s00778-023-00789-x)** · [source](https://lijunchang.github.io/publication.html) | VLDBJ, 2023 | A | Dian Ouyang; Dong Wen; Dong Wen #2 | Bibliography checked |
| W041 | **[Efficient Shortest Path Counting on Large Road Networks](https://doi.org/10.14778/3547305.3547315)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | PVLDB / VLDB, 2022 | A | Y. Qiu; Dong Wen; Dong Wen #2 | Bibliography checked |
| C065 | **[Efficient Sink-Reachability Analysis via Graph Reduction](https://lijunchang.github.io/publication.html)** | TKDE, 2022 | A | Jens Dietrich; Lijun Chang; Lijun Chang #2 | Bibliography checked |
| W042 | **[GPU-accelerated Proximity Graph Approximate Nearest Neighbor Search and Construction](https://doi.org/10.1109/ICDE53745.2022.00046)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2022 | A | Y. Yu; Dong Wen; Dong Wen #2 | Bibliography checked |
| C017 | **[Progressive Top-K Nearest Neighbors Search in Large Road Networks](https://doi.org/10.1145/3318464.3389746)** · [source](https://lijunchang.github.io/publication.html) | SIGMOD, 2020 | A | Dian Ouyang; Dong Wen; Dong Wen #2 | Bibliography checked |
| C042 | **[Efficiently Computing Top-K Shortest Path join](https://lijunchang.github.io/publication.html)** | EDBT, 2015 | B | Lijun Chang; Xuemin Lin; Lijun Chang #1 | Bibliography checked |
| C085 | **[The Exact Distance to Destination in Undirected World](https://lijunchang.github.io/publication.html)** | VLDBJ, 2012 | A | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | Bibliography checked |

<a id="group-6"></a>

## Scalable processing and numerical summaries

| ID | Paper | Publication | CCF | First two authors; qualifying position | Reading status |
| --- | --- | --- | --- | --- | --- |
| X06 | **[Optimal Matrix Sketching over Sliding Windows](https://doi.org/10.14778/3665844.3665847)** · [source](https://research.unsw.edu.au/people/dr-dong-wen/publications?page=0) | PVLDB / VLDB, 2024 | A | H. Yin; Dong Wen; Dong Wen #2 | Bibliography checked |
| C064 | **[ScaleG: A Distributed Disk-based System for Vertex-centric Graph Processing](https://doi.org/10.1109/TKDE.2021.3101057)** · [source](https://lijunchang.github.io/publication.html) | TKDE, 2023 | A | Xubo Wang; Dong Wen; Dong Wen #2 | Bibliography checked |
| W067 | **[General Graph Generators: Experiments, Analyses, and Improvements](https://doi.org/10.1007/s00778-021-00701-5)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2022 | A | S. Xiang; Dong Wen; Dong Wen #2 | Bibliography checked |
| W047 | **[Efficient Matrix Factorization on Heterogeneous CPU-GPU Systems](https://doi.org/10.1109/ICDE51399.2021.00169)** · [source](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2021 | A | Y. Yu; Dong Wen; Dong Wen #2 | Bibliography checked |

<a id="group-7"></a>

## Database ranking and other graph analytics

| ID | Paper | Publication | CCF | First two authors; qualifying position | Reading status |
| --- | --- | --- | --- | --- | --- |
| C051 | **[Finding information nebula over large networks](https://lijunchang.github.io/publication.html)** | CIKM, 2011 | B | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | Bibliography checked |
| C095 | **[Context-Sensitive Document Ranking](https://lijunchang.github.io/publication.html)** | JCST, 2010 | B | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | Bibliography checked |
| C053 | **[Probabilistic Ranking over Relations](https://lijunchang.github.io/publication.html)** | EDBT, 2010 | B | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | Bibliography checked |

## Version families and exclusions

Read the requested version, and borrow later techniques only with explicit attribution. Related publication families include C019/C069 (maximum clique), C004/C002 (k-plex), C003/X04 (defective clique), C009/C060 (edge-connectivity hierarchy), C034/C076 (pSCAN), C028/C071 (indexed structural clustering), C014/C063/X01 (GED methods and evaluation), C021/C066 (uncertain cores), W056/W072 (external-memory cores), W049/W066 (span reachability), W046/W062 (historical cores), and W031/W060 (historical connectivity). A later paper's author order must be checked independently.

Examples deliberately not counted: Scalable Top-K Structural Diversity Search (ICDE 2017 short paper); Context-Sensitive Document Ranking (CIKM 2009 short paper, while the JCST 2010 journal article is included); ScaleG's ICDE 2022 extended abstract (the TKDE paper is included); Efficient Sink-Reachability Analysis's ICDE 2023 extended abstract (the TKDE paper is included); An Overview of Path Queries on Graphs (ICDE 2025 tutorial); Skyline Nearest Neighbor Search on Multi-Layer Graphs (ICDE workshop); Computing Significant Cliques in Large Labeled Networks (TBD, CCF C); the cohesive-subgraph book and preprint duplicates. Do not borrow a parent conference's grade for a workshop or replace the author's position with corresponding-author status.
