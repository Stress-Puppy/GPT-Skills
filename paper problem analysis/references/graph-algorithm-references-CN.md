# 图算法参考：Lijun Chang 与 Dong Wen

分析凝聚子图搜索、半外存图处理、时间可达性或全动态图连通性时，按需阅读对应示例。本文补充已有的[历史图索引示例](temporal-graph-indexing-CN.md)。[英文版](graph-algorithm-references-EN.md)包含相同内容，无需同时加载两版。

## 筛选条件与证据

核验日期：2026-09-28。每篇论文均满足：**Lijun Chang 或 Dong Wen 中至少一人为第一或第二作者**，且属于 **CCF A/B 类会议，包含 B 类**。本次新增的五篇均通过 A 类会议入选。这是本组 reference 的筛选条件，不限制 skill 可以分析的论文。

[CCF 官方“数据库／数据挖掘／内容检索”目录](https://www.ccf.org.cn/Academic_Evaluation/DM_CS/)将 SIGKDD、ICDE、VLDB、SIGMOD 列为 A 类会议。下表中的 PVLDB、PACMMOD 论文按对应的 VLDB、SIGMOD 研究论文轨道归类；不据此宣称这两种出版物单独属于 CCF A 类期刊。作者顺序以链接论文首页为准，区分正式发表年份与会议年度。

| 编号 | 论文与发表信息 | 满足条件的作者 | 会议分级依据 |
| --- | --- | --- | --- |
| C19 | **Efficient Maximum Clique Computation over Large Sparse Graphs**。KDD 2019，529–538 页。[DOI](https://doi.org/10.1145/3292500.3330986) | Lijun Chang，唯一作者，即第一作者 | SIGKDD，CCF A |
| C22 | **Efficient Maximum k-Plex Computation over Large Sparse Graphs**。PVLDB 16(2)，127–139 页，2022 年发表；对应 VLDB 2023。[DOI](https://doi.org/10.14778/3565816.3565817) | Lijun Chang 第一作者；其后为 Mouyi Xu、Darren Strash | VLDB，CCF A |
| W16 | **I/O Efficient Core Graph Decomposition at Web Scale**。ICDE 2016，133–144 页。[DOI](https://doi.org/10.1109/ICDE.2016.7498235) | Dong Wen 第一作者；Lu Qin 第二作者 | ICDE，CCF A |
| W20 | **Efficiently Answering Span-Reachability Queries in Large Temporal Graphs**。ICDE 2020，1153–1164 页。[DOI](https://doi.org/10.1109/ICDE48307.2020.00104) | Dong Wen 第一作者；Yilun Huang 第二作者 | ICDE，CCF A |
| W24 | **Constant-time Connectivity Querying in Dynamic Graphs**。PACMMOD 2(6)，Article 230，2024 年 12 月发表；对应 SIGMOD 2025。[DOI](https://doi.org/10.1145/3698805) | Lantian Xu 第一作者；Dong Wen 第二作者 | SIGMOD，CCF A |

补充发表记录：[KDD 2019 接收列表](https://www.kdd.org/kdd2019/accepted-papers)、[Lijun Chang 论文列表](https://lijunchang.github.io/publication.html)、[UTS 的 W16 记录](https://opus.lib.uts.edu.au/handle/10453/131193)、[SIGMOD 2025 对应的 PACMMOD 2(6) 目录](https://2025.sigmod.org/toc-2-6.html)。

## C19 — 精确最大团：MC-BRB

**阅读来源：**[作者 PDF](https://lijunchang.github.io/pdf/2019-maxclique-kdd.pdf)，§2–4、Algorithms 1–3。需要页码时使用该文件的 10 页 PDF 页序。

- **问题／Input／Output：**无向图 `G` → 一个顶点数最多的团。Maximum 指基数最大；maximal 只表示不能继续加入顶点。
- **最终技术：** **MC-BRB**，局部搜索使用 **KCF-BRB**。逆 degeneracy order 将搜索分到规模受限的前向邻居 ego-network；core／着色上界排除无法改进当前解的区域，再以邻接矩阵支持局部的分支、归约与定界。
- **适用边界：** **MC-EGO** 提供启发式当前解，不是最终精确求解器。当前解给出的下界与剪枝上界作用不同。

**可迁移的阅读问题：**哪种分解使大规模实例变成可处理的局部实例？凭什么证明丢弃区域不能改进当前解？输出是一个最优解，还是枚举全部解？

## C22 — 带明确规模条件的最大 k-plex：kPlexS

**阅读来源：**[作者 PDF，含附录](https://lijunchang.github.io/pdf/2022-Maximum-kPlex.pdf)，§2 的问题定义、§3–5、Algorithm 1 与 CTCP／BBMatrix 部分。[正式发表 PDF](https://www.vldb.org/pvldb/vol16/p127-chang.pdf)对应上述 PVLDB 版本。

- **问题／Input／Output：**无向 `G`、整数 `k ≥ 2` → 若存在规模至少为 `2k−1` 的 k-plex，返回其中最大的；否则允许返回任意 k-plex。可行条件为 `degree_S(v) ≥ |S|−k`，即最多缺少与其他 `k−1` 个顶点的连接。
- **最终技术：** **kPlexS** 组合反复执行的 **core-truss co-pruning（CTCP）**、至多两跳的局部子问题与 **BBMatrix**。顶点／边归约相互触发；矩阵搜索结合顶点及顶点对信息，并增量维护。
- **适用边界：**返回规模为 `2k−2` 的解时也能保证最大；更小的返回解不一定最大。若需要不受规模限制的小规模最优解，正文要求另用精确求解器。归约过程的多项式界不等于完整精确搜索的界。

**可迁移的阅读问题：**结构性质对所有可行解成立，还是只对超过某个规模的解成立？“不存在足够大的解”是否已经确定了较小规模的最优值？区分搜索空间归约与完整算法的代价。

## W16 — 边无法全部放入内存时的 core number：SemiCore*

**阅读来源：**[UTS 接收稿](https://opus.lib.uts.edu.au/rest/bitstreams/65874dc3-1e78-447b-bdef-afd45844bf51/retrieve)，§IV.C、Lemma 4.2、Algorithm 5，PDF 第 7–8 页。该文件在论文前有一页封面。

- **问题／Input／Output：**顶点状态在 RAM、边在磁盘的无向图 → 每个顶点的 core number。属于半外存 core 分解，不是查询一个固定 k 的 core。
- **最终技术：** **SemiCore*** 从度数上界出发，根据邻居估计逐步降低估计值。维护达到顶点当前估计阈值的邻居数 `cnt(v)`；初始化后，`cnt(v) < core(v)` 才触发重算，阈值被跨越时更新受影响的计数与扫描范围。
- **适用边界：**`O(n)` 指 RAM 用量，`n` 为顶点数；不代表磁盘空间或总 CPU 代价。计数需要首轮初始化。“Optimal node computation”不能扩写成全局最优 I/O。

**可迁移的阅读问题：**什么驻留内存，什么必须从磁盘读取？哪个判据证明必须重新计算？内存、I/O、CPU 的界是否对应同一种操作？

## W20 — 窗口投影图中的可达性：TILL

**阅读来源：**[ICDE 官方 PDF](https://conferences.computer.org/icde/2020/pdfs/ICDE2020-5acyuqhpJ6L9P042wmjY1p/290300b153/290300b153.pdf)，§II、§IV–V；**TILL-Construct***（Algorithm 3）和 **Span-Reach**（Algorithm 4）。对应 PDF 第 3、5–8 页。

- **问题／Input／Output：**有向时序图 `G`、顶点 `u,v`、区间 `I` → 在 `I` 的投影图中是否可达的布尔值。路径边的时间戳不必按遍历顺序递增。
- **最终技术：** **TILL-Construct*** 构建入／出标签 `(hub,start,end)`，优先处理较短 span；已经可由处理过的 hub 表示的区间及探索被剪去。**Span-Reach** 匹配共同 hub 及包含于 `I` 的区间，通过有序标签分组与二分搜索加速。
- **适用边界：**另一个 θ-reachability 问题中的查询参数 `θ` 限制见证子区间；建索引参数 `ϑ` 限制覆盖范围。截断后的索引不能自动保证任意跨度查询的完备性。

**可迁移的阅读问题：**区间约束的是边是否出现、遍历的时间顺序，还是持续时长？省略索引记录依赖什么判据，答案又如何恢复？是否混淆了构建参数与查询参数？

## W24 — 全动态图连通性：DND-Trees

**阅读来源：**[共同作者 PDF](https://ronghuali.github.io/PaperFiles/Constant-time%20Connectivity%20Querying%20in%20Dynamic%20Graphs.pdf)，§6，尤其 PDF 第 13 页 Theorem 6.2 与删除处理部分。目标版本是上表的 2024 PACMMOD 文章；替换为扩展版前必须重新核对作者顺序及结论。

- **问题／Input／Output：**无向图、任意边插入／删除、顶点对查询 → 维护连通性并返回查询布尔值。
- **最终技术：** **DND-Trees** 将维护生成树的 **ID-Tree** 与带孩子链表的压缩 **DS-Tree** 配合。查询比较 DS 根；删除导致分裂时，隔离较小连通分量的顶点并在 DS 中重新合并，ID 提供结构信息与替代边搜索。
- **适用边界：**技术重点是 DND-Trees，不能停在中间方案 ID-Tree。Theorem 6.2 给出查询**均摊 `O(α(n))`**，`α` 是反 Ackermann 函数，不能改写为严格最坏 `O(1)`。DS 的父子连接不一定对应原图边。

**可迁移的阅读问题：**哪种结构负责回答查询，哪种负责维护更新？树边没有替代边时怎么办？合成连接保持的是连通分量归属、原图路径，还是两者？

## 使用方式

用示例帮助准确使用术语、提出阅读问题；当前论文的定义与保证仍以其自身正文为准。技术解释以最终算法为中心，baseline 只作简短动机。遇到新版本或新增 reference，重新核对作者顺序、发表 venue、输入输出约定、最终变体及原文位置。保留已有历史 core 与历史连通性笔记，不将其重复计为本次新增。
