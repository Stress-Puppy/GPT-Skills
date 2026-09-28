# 筛选后的参考目录：Lijun Chang 与 Dong Wen

## 范围与阅读状态

核验日期为 **2026-09-28**。本目录包含 **75 条发表记录：CCF A 类 64 条，B 类 11 条**，每条均由 **Lijun Chang 或 Dong Wen 担任第一或第二作者**。其中包含 skill 原有的七篇，**新增 68 条**。会议版和期刊版属于不同发表记录，不代表不同研究问题；同一发表版本的重复列表已去重。两位作者的公开列表具有选择性，更新时间也不一致，因此 75 是本轮已核验的覆盖量，不表示再无其他合格论文。

其中 **16 条已有“问题／Input／Output／最终方法”笔记**，见末列链接（本轮新增九篇笔记）。另 **59 条为已核实书目的检索参考**，收录不代表已读完其方法。陈述正式定义、最终算法、正确性或复杂度前，应打开对应全文。主题分组仅用于导航，不能用标题补全问题定义。普通单篇分析不必加载整个目录或全部笔记。

## 来源与资格核验

- 作者身份／顺序及检索来源：[Lijun Chang 论文列表](https://lijunchang.github.io/publication.html)、[Dong Wen 的 UNSW 主页](https://cgi.cse.unsw.edu.au/~dwen/)、[UNSW 发表记录第 0 页](https://research.unsw.edu.au/people/dr-dong-wen/publications?page=0)和[第 1 页](https://research.unsw.edu.au/people/dr-dong-wen/publications?page=1)。机构列表存在个别同名作者和错误字段，需匹配数据库／图方向的本人并核对具体论文。DBLP 只用于书目检索／核对，不作为算法结论的证据。
- 分级依据为 CCF 官方[数据库目录](https://www.ccf.org.cn/Academic_Evaluation/DM_CS/)、[理论目录](https://www.ccf.org.cn/Academic_Evaluation/TCS/)、[交叉综合目录](https://www.ccf.org.cn/Academic_Evaluation/Cross_Compre_Emerging/)。A 类：SIGMOD、VLDB、ICDE、KDD、WWW 会议及 TKDE、VLDB Journal；B 类：CIKM、EDBT、DASFAA 会议及 Algorithmica、World Wide Web Journal、JCST。WWW 会议与 World Wide Web 期刊必须区分。
- [CCF 第七版发布说明](https://www.ccf.org.cn/Academic_Evaluation/By_category/)规定会议论文按 full／regular paper 计入。短文、扩展摘要、tutorial、demo、workshop 不计入本目录。PVLDB／PACMMOD 研究论文按 VLDB／SIGMOD 会议归类，不虚构独立的 A 类期刊身份。
- 已核实时优先使用正式发表／卷期年份，并注明不同的会议年度或 online 年份。例如 kDC 为 PACMMOD 2023／SIGMOD 2024，C060 为 online 2023／VLDB Journal 卷期 2024。预印本及仅录用记录不额外计数。

作者列保留前两位作者的顺序（来源用缩写时保留缩写），并注明符合条件的排名。标题链接指向 DOI、全文或来源记录；“来源”链接提供作者／机构证据。A/B 条件只限定本组 reference，不限制 skill 可分析的其他论文。

## 导航

- [时序图与流图](#group-1)
- [连通性与图分解](#group-2)
- [凝聚子图与社区搜索](#group-3)
- [聚类、匹配与图相似性](#group-4)
- [路径与路网查询](#group-5)
- [大规模处理与数值摘要](#group-6)
- [数据库排序及其他图分析](#group-7)

<a id="group-1"></a>

## 时序图与流图

| 编号 | 论文 | 发表信息 | CCF | 前两位作者；符合条件的排名 | 阅读状态 |
| --- | --- | --- | --- | --- | --- |
| W005 | **[Accelerating K-Core Computation in Temporal Graphs](https://doi.org/10.48786/EDBT.2026.25)** · [来源](https://www.openproceedings.org/html/pages/2026_edbt.html) | EDBT, 2026 | B | Z. Ma; Dong Wen; Dong Wen #2 | [方法笔记](additional-graph-methods-CN.md#w005) |
| W002 | **[Maintaining Biconnected Components in Streaming Graphs](https://doi.org/10.1145/3802084)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2026 | A | Z. Lu; Dong Wen; Dong Wen #2 | 已核书目 |
| W060 | **[On Querying Historical Connectivity in Large-scale Temporal Graphs](https://doi.org/10.1007/s00778-025-00951-7)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2026 (online 2025) | A | L. Xu; Dong Wen; Dong Wen #2 | 已核书目 |
| W057 | **[On Querying Minimum Spanning Tree in Temporal Graphs](https://doi.org/10.1007/s00778-026-00989-1)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2026 | A | Y. Yu; Dong Wen; Dong Wen #2 | 已核书目 |
| W062 | **[Querying Historical K-Cores in Large Temporal Graphs](https://doi.org/10.1007/s00778-025-00903-1)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2025 | A | Y. Yu; Dong Wen; Dong Wen #2 | 已核书目 |
| W030 | **[On Compressing Historical Cliques in Temporal Graphs](https://doi.org/10.1007/978-981-97-5552-3_3)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | DASFAA, 2024 | B | K. Chen; Dong Wen; Dong Wen #2 | 已核书目 |
| W031 | **[On Querying Historical Connectivity in Temporal Graphs](https://doi.org/10.1145/3654960)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2024 | A | J. Song; Dong Wen; Dong Wen #2 | [方法笔记](temporal-graph-indexing-CN.md) |
| W033 | **[Querying Structural Diversity in Streaming Graphs](https://doi.org/10.14778/3641204.3641213)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | PVLDB / VLDB, 2024 | A | K. Chen; Dong Wen; Dong Wen #2 | 已核书目 |
| W066 | **[Span-Reachability Querying in Large Temporal Graphs](https://doi.org/10.1007/s00778-021-00715-z)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2022 | A | Dong Wen; B. Yang; Dong Wen #1 | 已核书目 |
| W046 | **[On Querying Historical K-Cores](https://doi.org/10.14778/3476249.3476260)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | PVLDB / VLDB, 2021 | A | M. Yu; Dong Wen; Dong Wen #2 | [方法笔记](temporal-graph-indexing-CN.md) |
| W049 | **[Efficiently Answering Span-Reachability Queries in Large Temporal Graphs](https://doi.org/10.1109/ICDE48307.2020.00104)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2020 | A | Dong Wen; Y. Huang; Dong Wen #1 | [方法笔记](graph-algorithm-references-CN.md) |

<a id="group-2"></a>

## 连通性与图分解

| 编号 | 论文 | 发表信息 | CCF | 前两位作者；符合条件的排名 | 阅读状态 |
| --- | --- | --- | --- | --- | --- |
| W024 | **[Minimum Spanning Tree Maintenance in Dynamic Graphs](https://doi.org/10.1145/3709704)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2025 | A | L. Xu; Dong Wen; Dong Wen #2 | 已核书目 |
| W020 | **[Preserving K-Connectivity in Dynamic Graphs](https://doi.org/10.1109/ICDE65448.2025.00019)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2025 | A | G. Zhao; Dong Wen; Dong Wen #2 | 已核书目 |
| C060 | **[A Near-Optimal Approach to Edge Connectivity-Based Hierarchical Graph Decomposition](https://doi.org/10.1007/s00778-023-00797-x)** · [来源](https://lijunchang.github.io/publication.html) | VLDBJ, 2024 (online 2023) | A | Lijun Chang; Zhiyi Wang; Lijun Chang #1 | 已核书目 |
| W025 | **[Constant-time Connectivity Querying in Dynamic Graphs](https://doi.org/10.1145/3698805)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2024 (会议 2025) | A | L. Xu; Dong Wen; Dong Wen #2 | [方法笔记](graph-algorithm-references-CN.md) |
| C009 | **[A Near-Optimal Approach to Edge Connectivity-Based Hierarchical Graph Decomposition](https://doi.org/10.14778/3514061.3514063)** · [来源](https://lijunchang.github.io/publication.html) | PVLDB / VLDB, 2022 | A | Lijun Chang; Zhiyi Wang; Lijun Chang #1 | [方法笔记](additional-graph-methods-CN.md#c009) |
| W050 | **[Fully Dynamic Depth-First Search in Directed Graphs](https://doi.org/10.14778/3364324.3364329)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | PVLDB / VLDB, 2020 | A | B. Yang; Dong Wen; Dong Wen #2 | 已核书目 |
| C022 | **[Enumerating k-Vertex Connected Components in Large Graphs](https://doi.org/10.1109/ICDE.2019.00014)** · [来源](https://lijunchang.github.io/publication.html) | ICDE, 2019 | A | Dong Wen; Lu Qin; Dong Wen #1 | 已核书目 |
| C035 | **[Computing Connected Components with Linear Communication Cost in Pregel-like Systems](https://lijunchang.github.io/publication.html)** | ICDE, 2016 | A | Xing Feng; Lijun Chang; Lijun Chang #2 | 已核书目 |
| C038 | **[Index-based Optimal Algorithms for Computing Steiner Components with Maximum Connectivity](https://lijunchang.github.io/publication.html)** | SIGMOD, 2015 | A | Lijun Chang; Xuemin Lin; Lijun Chang #1 | 已核书目 |
| C046 | **[Efficiently Computing k-Edge Connected Components via Graph Decomposition](https://lijunchang.github.io/publication.html)** | SIGMOD, 2013 | A | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | 已核书目 |

<a id="group-3"></a>

## 凝聚子图与社区搜索

| 编号 | 论文 | 发表信息 | CCF | 前两位作者；符合条件的排名 | 阅读状态 |
| --- | --- | --- | --- | --- | --- |
| W015 | **[Covering K-Cliques in Billion-Scale Graphs](https://doi.org/10.1145/3696410.3714897)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | WWW, 2025 | A | K. Chen; Dong Wen; Dong Wen #2 | 已核书目 |
| X02 | **[Estimating Biclique Counts with Accuracy Guarantees](https://doi.org/10.1145/3769791)** · [来源](https://dblp.org/rec/journals/pacmmod/GamageC25) | PACMMOD / SIGMOD, 2025 (会议 2026) | A | Rashmika Gamage; Lijun Chang; Lijun Chang #2 | 已核书目 |
| X03 | **[Identifying Maximum Defective Bicliques in Large Bipartite Graphs](https://doi.org/10.1109/ICDE65448.2025.00277)** · [来源](https://research.cuhk.edu.hk/en/publications/identifying-maximum-defective-bicliques-in-large-bipartite-graphs/) | ICDE, 2025 | A | Zhiyi Wang; Lijun Chang; Lijun Chang #2 | 已核书目 |
| X05 | **[Efficient k-Clique Count Estimation with Accuracy Guarantee](https://doi.org/10.14778/3681954.3682032)** · [来源](https://www.vldb.org/pvldb/vol17/p3707-chang.pdf) | PVLDB / VLDB, 2024 | A | Lijun Chang; Rashmika Gamage; Lijun Chang #1 | 已核书目 |
| C061 | **[Identifying Large Structural Balanced Cliques in Signed Graphs](https://doi.org/10.1109/TKDE.2023.3295803)** · [来源](https://lijunchang.github.io/publication.html) | TKDE, 2024 (online 2023) | A | Kai Yao; Lijun Chang; Lijun Chang #2 | 已核书目 |
| X04 | **[Maximum Defective Clique Computation: Improved Time Complexities and Practical Performance](https://doi.org/10.14778/3705829.3705839)** · [来源](https://www.vldb.org/pvldb/vol18/p200-chang.pdf) | PVLDB / VLDB, 2024 (会议 2025) | A | Lijun Chang; Lijun Chang #1 | 已核书目 |
| C002 | **[Maximum k-Plex Computation: Theory and Practice](https://lijunchang.github.io/Maximum-kPlex-v2/)** | PACMMOD / SIGMOD, 2024 | A | Lijun Chang; Kai Yao; Lijun Chang #1 | 已核书目 |
| W040 | **[Distributed Near-Maximum Independent Set Maintenance over Large-scale Dynamic Graphs](https://doi.org/10.1109/ICDE55515.2023.00195)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2023 | A | X. Wang; Dong Wen; Dong Wen #2 | 已核书目 |
| C003 | **[Efficient Maximum k-Defective Clique Computation with Improved Time Complexity](https://doi.org/10.1145/3617313)** · [来源](https://lijunchang.github.io/publication.html) | PACMMOD / SIGMOD, 2023 (会议 2024) | A | Lijun Chang; Lijun Chang #1 | [方法笔记](additional-graph-methods-CN.md#c003) |
| C005 | **[Verification-Free Approaches to Efficient Locally Densest Subgraph Discovery](https://lijunchang.github.io/publication.html)** | ICDE, 2023 | A | Tran Ba Trung; Lijun Chang; Lijun Chang #2 | 已核书目 |
| C066 | **[Computing K-Cores in Large Uncertain Graphs: An Index-based Optimal Approach](https://doi.org/10.1109/TKDE.2020.3023925)** · [来源](https://lijunchang.github.io/publication.html) | TKDE, 2022 | A | Dong Wen; Bohua Yang; Dong Wen #1 | 已核书目 |
| C012 | **[Computing Maximum Structural Balanced Cliques in Signed Graphs](https://lijunchang.github.io/pdf/icde22-msbc-tr.pdf)** · [来源](https://lijunchang.github.io/publication.html) | ICDE, 2022 | A | Kai Yao; Lijun Chang; Lijun Chang #2 | 已核书目 |
| C004 | **[Efficient Maximum k-Plex Computation over Large Sparse Graphs](https://doi.org/10.14778/3565816.3565817)** · [来源](https://lijunchang.github.io/publication.html) | PVLDB / VLDB, 2022 (会议 2023) | A | Lijun Chang; Mouyi Xu; Lijun Chang #1 | [方法笔记](graph-algorithm-references-CN.md) |
| C010 | **[Identifying Similar-Bicliques in Bipartite Graphs](https://lijunchang.github.io/publication.html)** | PVLDB / VLDB, 2022 | A | Kai Yao; Lijun Chang; Lijun Chang #2 | 已核书目 |
| C013 | **[Efficient Size-Bounded Community Search over Large Networks](https://doi.org/10.14778/3457390.3457407)** · [来源](https://lijunchang.github.io/publication.html) | PVLDB / VLDB, 2021 | A | Kai Yao; Lijun Chang; Lijun Chang #2 | [方法笔记](additional-graph-methods-CN.md#c013) |
| C015 | **[Deconstruct Densest Subgraphs](https://doi.org/10.1145/3366423.3380033)** · [来源](https://lijunchang.github.io/publication.html) | WWW, 2020 | A | Lijun Chang; Miao Qiao; Lijun Chang #1 | [方法笔记](additional-graph-methods-CN.md#c015) |
| C088 | **[Efficient Closest Community Search over Large Graphs](https://lijunchang.github.io/pdf/2020-closest_community-dasfaa.pdf)** · [来源](https://lijunchang.github.io/publication.html) | DASFAA, 2020 | B | Mingshen Cai; Lijun Chang; Lijun Chang #2 | [方法笔记](additional-graph-methods-CN.md#c088) |
| C069 | **[Efficient Maximum Clique Computation and Enumeration over Large Sparse Graphs](https://lijunchang.github.io/publication.html)** | VLDBJ, 2020 | A | Lijun Chang; Lijun Chang #1 | 已核书目 |
| C019 | **[Efficient Maximum Clique Computation over Large Sparse Graphs](https://lijunchang.github.io/pdf/2019-maxclique-kdd.pdf)** · [来源](https://lijunchang.github.io/publication.html) | KDD, 2019 | A | Lijun Chang; Lijun Chang #1 | [方法笔记](graph-algorithm-references-CN.md) |
| W072 | **[I/O Efficient Core Graph Decomposition: Application to Degeneracy Ordering](https://doi.org/10.1109/TKDE.2018.2833070)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | TKDE, 2019 | A | Dong Wen; L. Qin; Dong Wen #1 | 已核书目 |
| C021 | **[Index-based Optimal Algorithm for Computing K-Cores in Large Uncertain Graphs](https://doi.org/10.1109/ICDE.2019.00015)** · [来源](https://lijunchang.github.io/publication.html) | ICDE, 2019 | A | Bohua Yang; Dong Wen; Dong Wen #2 | 已核书目 |
| C024 | **[An Optimal and Progressive Approach to Online Search of Top-K Influential Communities](https://lijunchang.github.io/publication.html)** | PVLDB / VLDB, 2018 | A | Fei Bi; Lijun Chang; Lijun Chang #2 | 已核书目 |
| W055 | **[K-Connected Cores Computation in Large Dual Networks](https://doi.org/10.1007/978-3-319-91452-7_12)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | DASFAA, 2018 | B | L. Yue; Dong Wen; Dong Wen #2 | 已核书目 |
| C031 | **[Computing A Near-Maximum Independent Set in Linear Time by Reducing-Peeling](https://lijunchang.github.io/pdf/2017-mis-sigmod.pdf)** · [来源](https://lijunchang.github.io/publication.html) | SIGMOD, 2017 | A | Lijun Chang; Wei Li; Lijun Chang #1 | [方法笔记](additional-graph-methods-CN.md#c031) |
| W056 | **[I/O Efficient Core Graph Decomposition at Web Scale](https://doi.org/10.1109/ICDE.2016.7498235)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2016 | A | Dong Wen; L. Qin; Dong Wen #1 | [方法笔记](graph-algorithm-references-CN.md) |
| C083 | **[Fast Maximal Cliques Enumeration in Sparse Graphs](https://lijunchang.github.io/publication.html)** | Algorithmica, 2013 | B | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | 已核书目 |

<a id="group-4"></a>

## 聚类、匹配与图相似性

| 编号 | 论文 | 发表信息 | CCF | 前两位作者；符合条件的排名 | 阅读状态 |
| --- | --- | --- | --- | --- | --- |
| X01 | **[Graph Edit Distance Estimation: A New Heuristic and A Holistic Evaluation of Learning-based Methods](https://doi.org/10.1145/3725304)** · [来源](https://2025.sigmod.org/toc-3-3.html) | PACMMOD / SIGMOD, 2025 | A | Mouyi Xu; Lijun Chang; Lijun Chang #2 | 已核书目 |
| C063 | **[Accelerating Graph Similarity Search via Efficient GED Computation](https://lijunchang.github.io/pdf/2022-ged-tkde.pdf)** · [来源](https://lijunchang.github.io/publication.html) | TKDE, 2023 | A | Lijun Chang; Xing Feng; Lijun Chang #1 | [方法笔记](additional-graph-methods-CN.md#c063) |
| C014 | **[Speeding Up GED Verification for Graph Similarity Search](https://lijunchang.github.io/pdf/2020-ged-icde.pdf)** · [来源](https://lijunchang.github.io/publication.html) | ICDE, 2020 | A | Lijun Chang; Xing Feng; Lijun Chang #1 | 已核书目 |
| C071 | **[Efficient structural graph clustering: an index-based approach](https://doi.org/10.1007/s00778-019-00541-4)** · [来源](https://lijunchang.github.io/publication.html) | VLDBJ, 2019 | A | Dong Wen; Lu Qin; Dong Wen #1 | 已核书目 |
| C028 | **[Efficient Structural Graph Clustering: An Index-Based Approach](https://doi.org/10.14778/3157794.3157795)** · [来源](https://lijunchang.github.io/publication.html) | PVLDB / VLDB, 2017 (会议 2018) | A | Dong Wen; Lu Qin; Dong Wen #1 | 已核书目 |
| C076 | **[pSCAN: Fast and Exact Structural Graph Clustering](https://lijunchang.github.io/publication.html)** | TKDE, 2017 | A | Lijun Chang; Wei Li; Lijun Chang #1 | 已核书目 |
| C033 | **[Efficient Subgraph Matching by Postponing Cartesian Products](https://lijunchang.github.io/publication.html)** | SIGMOD, 2016 | A | Fei Bi; Lijun Chang; Lijun Chang #2 | 已核书目 |
| C090 | **[Ranking Weighted Clustering Coefficient in Large Dynamic Graphs](https://lijunchang.github.io/publication.html)** | World Wide Web Journal, 2016 | B | Xuefei Li; Lijun Chang; Lijun Chang #2 | 已核书目 |
| C034 | **[pSCAN: Fast and Exact Structural Graph Clustering](https://lijunchang.github.io/pdf/2016-pscan-icde.pdf)** · [来源](https://lijunchang.github.io/publication.html) | ICDE, 2016 | A | Lijun Chang; Wei Li; Lijun Chang #1 | [方法笔记](additional-graph-methods-CN.md#c034) |
| C092 | **[Efficient String Similarity Search: A Cross Pivotal Based Approach](https://lijunchang.github.io/publication.html)** | DASFAA, 2015 | B | Fei Bi; Lijun Chang; Lijun Chang #2 | 已核书目 |
| C039 | **[Optimal Enumeration: Efficient Top-k Tree Matching](https://www.vldb.org/pvldb/vol8/p533-chang.pdf)** · [来源](https://opus.lib.uts.edu.au/handle/10453/35410) | PVLDB / VLDB, 2015 | A | Lijun Chang; Xuemin Lin; Lijun Chang #1 | 已核书目 |

<a id="group-5"></a>

## 路径与路网查询

| 编号 | 论文 | 发表信息 | CCF | 前两位作者；符合条件的排名 | 阅读状态 |
| --- | --- | --- | --- | --- | --- |
| W004 | **[High-Throughput k Nearest Neighbors Search in Road Networks](https://doi.org/10.1145/3786656)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | PACMMOD / SIGMOD, 2026 | A | Y. Kong; Lijun Chang; Lijun Chang #2 | 已核书目 |
| W017 | **[Weight-Constrained Simple Path Enumeration in Weighted Graph](https://doi.org/10.1145/3690624.3709310)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | KDD, 2025 | A | D. Ouyang; Dong Wen; Dong Wen #2 | 已核书目 |
| W039 | **[Efficient and Effective Path Compression in Large Graphs](https://doi.org/10.1109/ICDE55515.2023.00237)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2023 | A | Y. Huang; Dong Wen; Dong Wen #2 | 已核书目 |
| C062 | **[When hierarchy meets 2-hop-labeling: efficient shortest distance and path queries on road networks](https://doi.org/10.1007/s00778-023-00789-x)** · [来源](https://lijunchang.github.io/publication.html) | VLDBJ, 2023 | A | Dian Ouyang; Dong Wen; Dong Wen #2 | 已核书目 |
| W041 | **[Efficient Shortest Path Counting on Large Road Networks](https://doi.org/10.14778/3547305.3547315)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | PVLDB / VLDB, 2022 | A | Y. Qiu; Dong Wen; Dong Wen #2 | 已核书目 |
| C065 | **[Efficient Sink-Reachability Analysis via Graph Reduction](https://lijunchang.github.io/publication.html)** | TKDE, 2022 | A | Jens Dietrich; Lijun Chang; Lijun Chang #2 | 已核书目 |
| W042 | **[GPU-accelerated Proximity Graph Approximate Nearest Neighbor Search and Construction](https://doi.org/10.1109/ICDE53745.2022.00046)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2022 | A | Y. Yu; Dong Wen; Dong Wen #2 | 已核书目 |
| C017 | **[Progressive Top-K Nearest Neighbors Search in Large Road Networks](https://doi.org/10.1145/3318464.3389746)** · [来源](https://lijunchang.github.io/publication.html) | SIGMOD, 2020 | A | Dian Ouyang; Dong Wen; Dong Wen #2 | 已核书目 |
| C042 | **[Efficiently Computing Top-K Shortest Path join](https://lijunchang.github.io/publication.html)** | EDBT, 2015 | B | Lijun Chang; Xuemin Lin; Lijun Chang #1 | 已核书目 |
| C085 | **[The Exact Distance to Destination in Undirected World](https://lijunchang.github.io/publication.html)** | VLDBJ, 2012 | A | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | 已核书目 |

<a id="group-6"></a>

## 大规模处理与数值摘要

| 编号 | 论文 | 发表信息 | CCF | 前两位作者；符合条件的排名 | 阅读状态 |
| --- | --- | --- | --- | --- | --- |
| X06 | **[Optimal Matrix Sketching over Sliding Windows](https://doi.org/10.14778/3665844.3665847)** · [来源](https://research.unsw.edu.au/people/dr-dong-wen/publications?page=0) | PVLDB / VLDB, 2024 | A | H. Yin; Dong Wen; Dong Wen #2 | 已核书目 |
| C064 | **[ScaleG: A Distributed Disk-based System for Vertex-centric Graph Processing](https://doi.org/10.1109/TKDE.2021.3101057)** · [来源](https://lijunchang.github.io/publication.html) | TKDE, 2023 | A | Xubo Wang; Dong Wen; Dong Wen #2 | 已核书目 |
| W067 | **[General Graph Generators: Experiments, Analyses, and Improvements](https://doi.org/10.1007/s00778-021-00701-5)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | VLDBJ, 2022 | A | S. Xiang; Dong Wen; Dong Wen #2 | 已核书目 |
| W047 | **[Efficient Matrix Factorization on Heterogeneous CPU-GPU Systems](https://doi.org/10.1109/ICDE51399.2021.00169)** · [来源](https://cgi.cse.unsw.edu.au/~dwen/) | ICDE, 2021 | A | Y. Yu; Dong Wen; Dong Wen #2 | 已核书目 |

<a id="group-7"></a>

## 数据库排序及其他图分析

| 编号 | 论文 | 发表信息 | CCF | 前两位作者；符合条件的排名 | 阅读状态 |
| --- | --- | --- | --- | --- | --- |
| C051 | **[Finding information nebula over large networks](https://lijunchang.github.io/publication.html)** | CIKM, 2011 | B | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | 已核书目 |
| C095 | **[Context-Sensitive Document Ranking](https://lijunchang.github.io/publication.html)** | JCST, 2010 | B | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | 已核书目 |
| C053 | **[Probabilistic Ranking over Relations](https://lijunchang.github.io/publication.html)** | EDBT, 2010 | B | Lijun Chang; Jeffrey Xu Yu; Lijun Chang #1 | 已核书目 |

## 版本关系与排除示例

阅读用户指定版本；借用后续技术时明确归属。相关发表系列包括 C019/C069（最大团）、C004/C002（k-plex）、C003/X04（缺陷团）、C009/C060（边连通层级）、C034/C076（pSCAN）、C028/C071（索引结构聚类）、C014/C063/X01（GED 方法及评估）、C021/C066（不确定图 core）、W056/W072（外存 core）、W049/W066（span reachability）、W046/W062（历史 core）、W031/W060（历史连通性）。后续论文的作者顺序须独立核验。

明确不计入的示例：Scalable Top-K Structural Diversity Search（ICDE 2017 短文）；Context-Sensitive Document Ranking（CIKM 2009 短文，JCST 2010 期刊版已收录）；ScaleG 的 ICDE 2022 扩展摘要（TKDE 版已收录）；Efficient Sink-Reachability Analysis 的 ICDE 2023 扩展摘要（TKDE 版已收录）；An Overview of Path Queries on Graphs（ICDE 2025 tutorial）；Skyline Nearest Neighbor Search on Multi-Layer Graphs（ICDE workshop）；Computing Significant Cliques in Large Labeled Networks（TBD，CCF C）；凝聚子图专著及重复预印本。不能借用母会议等级给 workshop 分级，也不能用通讯作者身份替代作者排名。
