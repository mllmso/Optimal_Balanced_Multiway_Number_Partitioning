## 📜 State of the Art in Balanced Multiway Number Partitioning — 2025  

*Practical Feasibility Snapshot*

**Author**: [mllmso](https://orcid.org/0009-0005-3698-7366)

> **Disclaimer**  
> This snapshot is based on established benchmarks, peer-reviewed literature, and industrial practice as of late 2025.  
> It synthesizes a consensus validated across multiple AI reasoning systems and critically challenged by the author.  
> **No liability** is assumed for algorithmic choices, performance outcomes, or system decisions based on this summary.  
> **Always validate on your own instances**—real-world results depend on data, hardware, and implementation details.

---

### Scope and Rationale  
This snapshot includes **only operationally relevant, state-of-the-art approaches** for balanced *(cardinality-constrained)* multiway number partitioning, where each subset must contain either floor(N/K) or ceil(N/K) items.

### Selection Criteria  
Methods were selected based on:  
* **Operational relevance**: demonstrated use in real-world systems *(e.g., data sharding, balanced task assignment, and balanced clustering)*  
* **Empirical dominance**: consistent top performance in public benchmarks or solver studies  
* **Algorithmic distinctiveness**: each entry represents a unique strategy class *(not a minor variant)*  
* **Decision utility**: enables rapid elimination of non-viable approaches for practitioners  

**Excluded**: unconstrained methods—technically valid, yet unable to guarantee balanced subset sizes.

---

### Notation  
* **N**: Total number of items  
* **K**: Number of subsets  
* **S**: Subset sizes are either floor(N/K) or ceil(N/K)

---

### Instance Classes  
Classified by weight dispersion **relative to instance scale (N)**:

* **Easy**: Tightly clustered weights *(e.g., uniform, Gaussian)*  
* **Moderate**: Moderately spread weights *(e.g., log-normal, power-law)*  
* **Hard**: Highly dispersed weights *(e.g., large-range uniform, mix of small and large values)*

---

### Legend  
- ✅ = Provably optimal *(optimality verified)*  
- ☑️ = High-quality heuristic *(no optimality guarantee)*  
- ⚠️ = Possible but unreliable *(slow or highly instance-dependent)*  
- ❌ = Generally infeasible *(under stated limits and typical hardware)*

---

### Feasibility Table (2025)

| Method                                | Typical max scale     | K       | Easy | Mod. | Hard | Best suited for…                     |
| ------------------------------------- | --------------------- | ------- | ---- | ---- | ---- | ------------------------------------ |
| **Exact methods**                     |                       |         |      |      |      |                                      |
| CIW (cardinality-aware)               | N ≤ 70 \*             | 2–5     | ✅   | ⚠️   | ❌   | Small balanced instances             |
| CP-SAT / MIP hybrids                  | N ≤ 100 \*\*          | 2–6     | ✅   | ⚠️   | ❌   | Flexible modeling, symmetry breaking |
| **Heuristics**                        |                       |         |      |      |      |                                      |
| Balanced KK + Local Search            | N ≤ 1,000             | 2–10    | ☑️   | ☑️   | ⚠️   | Best general-purpose heuristic       |
| Greedy Balanced (LPT-style)           | N ≤ 10,000            | ≤20     | ☑️   | ☑️   | ☑️   | Large-N baseline                     |
| Metaheuristics (Tabu / SA / GA)       | N ≤ 5,000             | ≤10     | ☑️   | ⚠️   | ❌   | Offline, quality-focused runs        |
| Distributed Balanced Greedy           | N ≥ 100,000           | ≤50     | ☑️   | ☑️   | ☑️   | Large-scale equal-shard systems      |
| Streaming Balanced Greedy             | N ≥ 10,000,000        | ≤100    | ☑️   | ☑️   | ☑️   | One-pass fixed-size buckets          |

---

### Notes  
- \* Exact methods become impractical once **S > 15–20** due to combinatorial explosion in feasible assignments.  
- \*\* CP-SAT and MIP hybrids scale slightly with simple cases but degrade under adversarial inputs or tight constraints.

---

### Decision Guidelines  
Start here to pick a method:  
* **N ≤ 50, K ≤ 5, S ≤ 20?** → Try exact (CP-SAT or CIW).  
* **N ≤ 1,000, K ≤ 10?** → Balanced KK + local search.  
* **N > 1,000?** → Prefer greedy or distributed balanced variants; exact methods only for reduced subproblems.  
* **Exact balanced partitioning beyond N ≈ 100 is rarely practical in 2025 except for very favorable instances or heavy compute budgets.**

---

### Overall Assessment (2025)
* No theoretical breakthrough has altered the fundamental NP-hard complexity.
* Cardinality constraints significantly restrict viable algorithms compared to the unconstrained case.
* Heuristics dominate production workloads; exact methods are limited to small or critical instances.
* **Ongoing work** explores constraint-aware heuristics, yet results remain highly instance-specific.

---

### Validity Statement  
This snapshot covers the **major practically relevant method classes** for balanced multiway partitioning in 2025.  

*(Last reviewed: Dec 2025)*