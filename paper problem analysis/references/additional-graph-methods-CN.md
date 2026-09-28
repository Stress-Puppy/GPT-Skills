# 补充图算法方法笔记

按需读取对应章节。编号对应[筛选后的参考目录](chang-wen-catalog-CN.md)；[英文版](additional-graph-methods-EN.md)内容相同。以下九篇笔记于 2026-09-28 对照链接全文核验；页码采用 PDF 页序。它们补充已有的五篇[图算法示例](graph-algorithm-references-CN.md)和两篇[历史索引示例](temporal-graph-indexing-CN.md)。

<a id="c003"></a>

## C003 — 最大缺陷团：kDC

来源：[作者稿](https://lijunchang.github.io/pdf/2024-Maximum-kDC.pdf)，§2–3，尤其 §3.1.3 和 Algorithm 2，PDF 第 5–8 页。首页注明 PACMMOD 1(3)，Article 209，**2023 年发表**，对应 SIGMOD 2024。

- **输入输出：**无向图 `G`、缺边预算 `k` → 一个顶点数最多、距离完全图至多缺少 `k` 条边的顶点集。
- **最终方法：** **kDC** 先找较大的可行解，用其规模归约顶点／边，再结合上界与实际优化归约规则进行分支搜索。Non-fully-adjacent-first 规则优先对已经与部分解中某个顶点不相邻的顶点分支。
- **边界：**预算约束整个诱导子图，与 k-plex 的逐顶点缺邻居限制不同。Algorithm 1 的 **kDC-t** 只包含理论核心，解释时要包含 Algorithm 2 的实际优化。后续 **kDC-Two** 是另一篇论文，目录编号 X04。

<a id="c009"></a>

## C009 — 全部边连通度层级：ECo-DC-AA

来源：[PVLDB 2022 对应的作者技术报告](https://lijunchang.github.io/pdf/2022-ecd-tr.pdf)，§4–5、Algorithms 3–4、§5.2，PDF 第 5–9 页。

- **输入输出：**无向图 `G` → 表示所有 k 值下 k-edge-connected components 的层级树。
- **最终方法：** **ECo-DC-AA** 将连通度层级上的分治与邻接数组实现结合。在分割层级计算分量，收缩分量得到较低层级子问题，在分量内部递归较高层级，再用边连通度信息生成层级树；数组和紧凑辅助状态控制构建内存。
- **边界：**全部 k 的层级结构不同于固定 k 的答案。输出树大小与构建工作空间不同。技术分析要同时讲 §4 的递归与 §5.2 的实现，不能把最终内存界套给链表 baseline。C060 是后续期刊版。

<a id="c013"></a>

## C013 — 精确的规模受限社区搜索：SC-BRB

来源：[作者 PDF](https://lijunchang.github.io/pdf/scs-tr.pdf)，§2、§4–5；PDF 第 8 页 Algorithm 4 和 §4.4。

- **输入输出：**无向 `G`、查询顶点 `q`、规模范围 `[ℓ,h]` → 包含 `q`、满足 `ℓ ≤ |S| ≤ h` 的连通社区，并最大化最小度。
- **最终方法：** **SC-BRB** 结合度数／距离归约、逐步增强的上界与基于支配关系的分支。选分支时优先改善部分解中低度顶点的连接，同时保持连通性；**SC-Heu** 用来初始化可行当前解。
- **边界：**规模范围是约束，不是优化目标；最小度不是平均度密度。SC-Heu 虽在后文出现，却没有取代精确求解器。“最大化社区规模”将是另一个任务。

<a id="c015"></a>

## C015 — 表示全部最密子图：ds-Index

来源：[作者 PDF](https://lijunchang.github.io/pdf/dds.pdf)，§2–3、Definition 3、Theorems 1–4、§3.4，PDF 第 2–5 页。

- **输入输出：**在本文连通无向图设置下，表示所有最大化 `|E(S)|/|S|` 的子图，并支持枚举全部或仅极小最密子图。
- **最终方法：**先用密度下界和 core 归约安全缩图，再通过参数化流计算得到临界残量图，将其强连通分量收缩成 DAG。**ds-Index** 保存相关分量、DAG 与诱导图；对子孙关系封闭的分量集合恢复最密子图，汇分量对应极小最密子图。
- **边界：**`O(L)` 枚举延迟不是枚举所有答案的总时间；`L` 为极大最密子图的顶点数与边数之和。全局最密、局部最密以及一般的“稠密”不能混用。

<a id="c031"></a>

## C031 — 大规模独立集：LinearTime 与 NearLinear

来源：[作者 PDF](https://lijunchang.github.io/pdf/2017-mis-sigmod.pdf)，§4–5、Algorithms 4–5，PDF 第 7–9 页。

- **输入输出：**无向 `G` → 较大的独立顶点集，并扩展到极大；算法不保证最大独立集，也没有正式近似比保证。
- **最终方法：** **LinearTime** 将低度及度二路径归约与高度顶点剥离结合，再重建答案；**NearLinear** 额外维护三角形信息以执行支配归约。两种最终变体在运行时间和实际解质量间取舍，应按场景说明。
- **边界：**某条安全归约可保持最优解，但整个算法中的非精确剥离仍可能失去最优性。不要停在 baseline BDOne／BDTwo，也不能把“near-maximum”当成已证明的近似比。

<a id="c034"></a>

## C034 — 精确结构聚类：pSCAN

来源：[作者 PDF](https://lijunchang.github.io/pdf/2016-pscan-icde.pdf)，§II、§IV–VI；PDF 第 6 页 Algorithm 3。

- **输入输出：**无向 `G`、结构相似度阈值 `ε`、核心阈值 `μ` → SCAN 语义下的簇及 hub／outlier 识别。
- **最终方法：** **pSCAN** 维护相似邻居数的上下界，无需算完每一对相似度就可确定 core／non-core 状态；并查集合并核心簇，随后分配非核心顶点。度数界和提前终止加速剩余相似性检查。
- **边界：**这里的 core vertex 由结构相似性及 `μ` 定义，不是 k-core number。区分精确聚类语义与省略不必要检查的优化；TKDE 版 C076 是另一发表版本。

<a id="c063"></a>

## C063 — 图编辑距离验证：AStar-BMao

来源：[作者稿](https://lijunchang.github.io/pdf/2022-ged-tkde.pdf)，§2、§5（含 §5.3），PDF 第 3–4、7–10 页。目录采用 TKDE 2023 的卷期年份。

- **输入输出：**带标签无向图 `q,g`、阈值 `τ` → 图编辑距离是否不超过 `τ`，用于验证数据库相似性搜索的候选图；精确距离计算是另一个支持的操作。
- **最终方法：** **AStar-BMao** 用优化的 anchor-aware branch-match 下界搜索部分顶点映射；适度放松下界使不同子映射的计算更便宜，并结合提前终止及可行上界维护进一步减少工作。
- **边界：**最紧下界不一定对应最快算法，需区分 BMa 与计算更便宜的 BMao。内部下界不是最终 GED；图对验证也不等于整个数据库过滤流程。

<a id="c088"></a>

## C088 — 最近社区搜索：CCS

来源：[作者 PDF](https://lijunchang.github.io/pdf/2020-closest_community-dasfaa.pdf)，§2、§4.3；PDF 第 11 页 Algorithm 6。

- **输入输出：**无向 `G`、查询集合 `Q` → 包含 `Q` 的连通社区，先最大化最小度，再最小化最大查询距离，并满足文中的极大性要求。查询距离取在 `G` 中到 `Q` 内各顶点距离的最大值。
- **最终方法：** **CCS** 从索引得到最优可行 core 层级，按查询距离顺序、以几何规模增长的方式扩张工作子图，再对其中满足要求的连通 core 调用 **LinearOrder-S2**，直到获得答案。
- **边界：**技术重点是最终的扩张策略，不能只讲最初全局缩图／剥离 baseline。到 `Q` 的最大距离不同于到最近查询顶点的距离，也要保留优化目标的先后顺序。

<a id="w005"></a>

## W005 — 不同时间 core 的枚举：CoreTime + Enum

来源：[EDBT 2026 正式 PDF](https://www.openproceedings.org/2026/conf/edbt/paper-175.pdf)，问题定义、§4–5、Algorithms 2、4–5，PDF 第 3–9 页。

- **输入输出：**时序图、`k`、查询范围 `[Ts,Te]` → 其中各子窗口对应的不同 temporal k-core 边集，而不是单个固定窗口的答案。
- **最终方法：** **CoreTime** 从顶点 core time 导出边的 core-window skyline；**Enum** 推进开始时间，以按结束时间排序的链表维护活跃最小窗口；**AS-Output** 利用 tightest interval 条件输出不同结果。EnumBase 只是 baseline。
- **边界：**区分重复边出现记录、顶点集合与时间边集。论文给出整体 `O(|VCT|·deg_avg + |R|)`，`|R|` 是总输出大小；其枚举 `O(|R|)` 的陈述以已有 skyline 为前提。不能省略预处理，也不能把输出大小仅当作答案个数。
