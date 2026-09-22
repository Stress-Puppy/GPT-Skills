# Representative papers: temporal graph indexing

Read this reference for historical graph queries, temporal graph indexes, or examples of how to explain a final optimized algorithm. The Chinese counterpart is [temporal-graph-indexing-CN.md](temporal-graph-indexing-CN.md). These are analytical notes, not additional universal requirements or substitutes for reading a new paper.

## Sources and scope

- **[K21]** Michael Yu et al., *On Querying Historical K-Cores*, PVLDB 14(11), 2033–2045, 2021. DOI: `10.14778/3476249.3476260`. Read from the supplied `historical-kcore.pdf`, 13 pages. PDF page 1 is printed page 2033. This is the conference paper: its conclusion lists dynamic PHC index maintenance as future work. Do not attribute algorithms from a later journal extension to this file.
- **[C24]** Jingyi Song et al., *On Querying Historical Connectivity in Temporal Graphs*, Proc. ACM Manag. Data 2(3), Article 157, 2024. DOI: `10.1145/3654960`. Read from the supplied `sigmod_24_camera_ready.pdf`, 25 pages. PDF page N is printed page 157:N. This paper's final historical method is POEC-Index; its final sliding-window method uses OEC-Forest.

All page references below use **PDF page order**. Notes paraphrase the supplied texts. Reusable lessons are our analytical synthesis; algorithm names and stated results belong to the cited papers.

## Terms and distinctions

| English term | Chinese term | Meaning in these papers and reading implication |
| --- | --- | --- |
| temporal edge / edge occurrence | 时间边／边的出现记录 | A triple `(u,v,t)`; repeated contacts between the same endpoints are separate temporal records. |
| projected graph / snapshot | 投影图／快照 | For a closed window `[s,e]`, include endpoint pairs with at least one occurrence in the window and merge repetitions into a simple undirected graph. This is not an intersection requiring every edge to exist at every instant. |
| historical query | 历史查询 | A query on an arbitrary historical window, rather than only the current window. |
| sliding-window query | 滑动窗口查询 | A query on the most recent window as new edges arrive. Check the paper's discrete or continuous endpoint convention. |
| core number | 核数 | The largest `k` for which a vertex belongs to a k-core; distinct from its ordinary degree. |
| core time (CT) | core time／核时间 | In [K21], the earliest end time that makes a vertex belong to a k-core, with the start time and k fixed. It is not a persistence duration. |
| start-/end-anchored query | 固定起点／终点的查询 | Fix one window boundary to reveal a simpler query family; check which boundary is fixed. |
| connectivity-equivalent forest | 连通性等价森林 | In [C24], a forest preserving the connected components for every start-time threshold at a fixed end time. Equivalence concerns query answers, not all original edges or paths. |
| maximum spanning forest (MSF) | 最大生成森林 | Uses edge times as weights in [C24]. “Maximum” is essential; the final ordered forest need not itself be a spanning forest. |
| lowest common ancestor (LCA) | 最近公共祖先 | The meeting point used to explain ordered upward search, not necessarily the root. |
| temporal wedge transformation (TW) | 时间楔变换 | [C24]'s local two-edge transformation preserving end-anchored connectivity; a paper-specific operation. |

Sources: [K21] §2, Definitions 2.2/2.4 (p.3), Definition 4.2 (p.4); [C24] Definitions 2.1–2.3 (p.5), 4.1/4.3 (pp.8–9), 4.11 (p.10), 5.1/5.4 (pp.13/15).

## [K21]: PHC-Index with PHC-Construct*

### Problem, input, and output

Given an undirected temporal graph, a window `[s,e]`, and an integer `k`, return **all vertices belonging to k-cores of the projected graph** (Problem 1, p.3). The paper defines an individual k-core as a maximal connected induced subgraph with minimum internal degree at least k (Definition 2.2); the returned union can contain several components. Do not turn maximality into a maximum-size optimization or return only one arbitrary component.

Index construction takes the temporal graph. Online querying takes `[s,e]` and `k` with the index available. The containment subproblem additionally takes a vertex `u` and returns a Boolean (Problem 2, p.4); this subproblem is not the full vertex-set output. Core decomposition and finding the core containing a specified vertex are separately described extensions (§4.3, p.6).

### Explain the final pipeline

The opening intuition can be one sentence: repeatedly peeling each window's snapshot, or materializing all windows, duplicates considerable work. The main explanation should then cover **PHC-Index, PHC-Query, and the optimized PHC-Construct***, rather than treating PHC-Construct as the final algorithm.

1. **Encode a threshold.** For each `(u,k,s)`, `CT_s(u,k)` is the earliest valid end time. Window containment makes membership monotone: at a fixed start, increasing the end cannot reduce the core number. Thus membership for `[s,e]` is determined by `CT_s(u,k) <= e` (§4.1, p.4).
2. **Store only changes.** As the start increases, the core time cannot decrease. PHC stores ordered `(start, core-time)` records only when the core-time value changes; one record represents a run of starts with the same threshold (§4.2, p.5). These are change records, not a list of every valid query window, and should not automatically be called inclusion-minimal feasible windows. The paper handles k=1 directly via incident-edge existence and uses an out-of-range time for an impossible threshold.
3. **Construct by local validity repair.** PHC-Construct* initializes core times at the first start, then advances the start. CT-neighbor tables track distinct supporting neighbors and counts of repeated edge occurrences. Removing an occurrence reduces its count; a neighbor is lost only when its support disappears. A `(u,k)` pair enters the work queue when fewer than k supporting neighbors remain. LocalCT recomputes its threshold from distinct neighbors' earliest contribution times `max(edge time, neighbor CT)`, taking the k-th smallest contribution and using chronological early termination. Repair affected neighbors until the queue is exhausted, and record changed core times. This dependency propagation is essential: the local formula alone is not an independent, one-pass algorithm (§5.2, Algorithms 5–7, pp.8–9).
4. **Recover the answer.** For each candidate vertex, binary-search the last stored start not greater than the query start, and compare its core-time value with the query end. Collect all vertices passing this membership check (§4.3, Lemmas 4.11/4.13, pp.5–6).

The useful reasoning chain is **window monotonicity → threshold representation → compression of unchanged thresholds → support certificates → local repair when a certificate fails**. Explain what work is avoided and why checking fewer states remains sufficient.

### Cost and attribution checks

Keep the number of temporal occurrences `m` separate from the number of distinct projected edges `m*` (§2). Lemma 4.13 bounds one containment query by `O(log |PHC(u,k)|)`; this is not the cost of returning every qualifying vertex. Theorem 4.14 states `O(n log t_bar)` for the full query. Theorem 5.14 states `O(|PHC| D_max)` for PHC-Construct*, where `|PHC|` is the index size and `D_max` is the maximum degree. Preserve that factor instead of repeating an unqualified “linear construction” claim. Average stored-record counts observed to be small are empirical, not constants guaranteed for every graph.

## [C24]: POEC-Index with OEC-Forest

### Problem, input, and output

Preprocessing/maintenance receives an undirected temporal edge stream. A historical query receives two vertices `(u,v)` and an arbitrary window `[s,e]`; it returns a **Boolean** stating whether a path connects them in that window's projected graph (Definition 2.2, p.5). Path timestamps need not be increasing. The task does not require returning the path, the forest, or every connected component.

Sliding-window queries restrict the query to the most recent duration; they are a separate workload using a smaller maintained state. Do not interchange a historical index spanning many end times with a single current forest.

### Explain the final pipeline

A short motivation may mention that an MSF preserves connectivity thresholds but repeated searches toward roots and rerooting create avoidable work. The detailed explanation belongs to **OEC-Forest, POEC-Query, and POEC-Update** in §5 (pp.13–17).

1. **Preserve exactly the required equivalence.** Fix end time `e`. For every start `s`, keeping forest edges whose labels are at least `s` must yield the same connected components as the original window snapshot. This is stronger than preserving connectivity only at the current full window. OEC-Forest adds a fixed total vertex order, with `parent(v) ≺ v` for non-root vertices (Definitions 4.3/5.1).
2. **Store ordered histories of changed labels.** A historical label records `(parent, forest-edge time, end time at which this state is recorded)`. Consecutive identical states can be omitted. The edge time and the historical end time serve different purposes. POEC-Index retains these histories; the latest forest is recovered from the latest labels (§§4.1/5.1, Tables 2–3). Do not interpret “unchanged parent” as sufficient for dropping a changed edge-time label: Table 3 contains the same parent with different edge times.
3. **Query using the order.** Resolve each visited vertex's label for `e`, then repeatedly move the larger endpoint under `≺` to its parent while its edge label meets the start threshold. Equality gives a positive result; an obstructing root or too-old edge gives a negative result. The order lets the search meet at the LCA without visiting unnecessary ancestors above it (Algorithm 4, p.14). Use the explicit order relation rather than ambiguous descriptions such as “higher rank.”
4. **Update through TW transformations.** Combine an incoming connection with the chosen endpoint's parent edge. If its time is at least the parent-edge time, keep the newer connection as the parent edge and propagate the displaced older connection upward; otherwise propagate the incoming connection upward. Repeated local transformations reduce a cycle or join two trees while preserving threshold connectivity and the parent-order constraint. Changed states are appended to historical labels (Definition 5.4, Lemmas 5.5/5.7, Algorithm 5, pp.15–17). Reusing the earlier MSF reroot procedure would violate the final structure's order constraint.
5. **Specialize only when discussing sliding windows.** Maintain the latest OEC-Forest without historical label lists. Threshold checks make explicit expiration deletion/replacement searches unnecessary, and the update can stop when its propagated time is older than the needed window. This specialization has `O(n)` state (§6, pp.16–17).

OEC-Forest may contain transformed edges absent from the original graph. A forest path is a connectivity witness in the representation, not automatically a path that can be returned as original input edges. The useful reasoning chain is **query equivalence → compressed representation → order invariant → smaller search/changed region → equivalence-preserving local update**.

### Cost and source-consistency checks

Attach costs to historical query, single-edge update, or current-window query separately. Theorem 5.9 gives `O(dist(u,v))` for POEC-Update, with `O(n)` worst case; §6 gives `O(dist(u,v))` for a sliding-window query. These bounds do not justify calling historical queries constant-time label access.

The supplied camera-ready text needs care: Theorem 5.3 prints `O(dist(u,v) · t_bar)`, while §4.1 describes binary search of historical labels and Theorem 4.9 includes a logarithmic label-search factor. Do not silently replace the printed theorem with a derived bound; identify any derivation separately. Likewise Definition 2.3 uses `[t_max - theta + 1, t_max]`, while §6 writes a threshold `t_e - theta`. If endpoints affect an example or implementation, explicitly state the chosen interpretation and the discrepancy.

## Reusable analysis habits

- Begin with the exact graph semantics and answer predicate; the word “temporal” does not specify either.
- Separate the user's output, a decision primitive used to obtain it, and the maintained index.
- Follow the final algorithm's actual representation and update operations. An earlier algorithm can remain an initialization subroutine without becoming the focus of the explanation.
- For every pruning or compression idea, identify the redundant states, the retained certificate, and the recovery rule. For every incremental operation, identify what changes, what remains valid, and how dependencies propagate.
- Ask what a representation preserves: vertex membership, connected components, edge identities, or paths. Do not infer stronger preservation than the proved query equivalence.
- Transfer these questions to other database/graph papers; re-establish monotonicity, ordering, temporal semantics, and update assumptions from each new source.
