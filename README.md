# Optimal Balanced Multiway Number Partitioning
> 📌 ***Datasets → small to large (N) → uniform random values (10k–1B) → optimal partitions → K ≤ 10,000*** 🚀

**Author**: [mllmso](https://orcid.org/0009-0005-3698-7366)

## Overview
- Benchmark datasets for the **Balanced Multiway Number Partitioning** problem—at scale.
- All solutions **achieve the theoretical optimum**—with subset sums & sizes equal or differing by at most 1.
- Large-scale **verified optimal partitions**—where optimality is generally not guaranteed *(see 📜 [SOTA_BMNP_25](SOTA_BMNP_25.md))*.
- **Important**: Computed on **non-adversarial instances** with an **original algorithm**—not included in the repository.

## 1. Problem

💬 **Balanced Multiway Number Partitioning (BMNP)**

The goal is to partition a multiset of `N` positive integers into `K` *disjoint* subsets such that:

- the maximum subset sum *(makespan)* is **minimized**, and
- subset sizes *(cardinality)* **differ by at most 1**.
 
The problem is **NP-hard**—no polynomial-time algorithm can solve all instances optimally, unless P = NP.

**BMNP** has practical applications in *data sharding, balanced task assignment, and balanced clustering*.

## 2. Datasets

📊 **Instances**
- **Total**: `35`
- **Sizes**: Small `(N = 100)` to large `(N = 100,000)`
- **Partitions**: Low `(K ≤ 10)` to high `(K = 10,000)` 

🎲 **Distributions**
- **Uniform**: True random, fully traceable, and unique positive integers from [RANDOM.ORG](https://random.org)  
- **Ranges**: Medium `[1-10,000]` to large `[1-1,000,000,000]`

🔗 **Constraints**  
- **Number of subsets**: `K`
- **Subset sum**: either `floor(target)` or `ceil(target)`, where `target = sum(multiset) / K`
- **Subset size**: either `floor(limit)` or `ceil(limit)`, where `limit = size(multiset) / K`
- **Objective**: All subset sums & sizes equal or differing by at most 1 🟩

📄 **File formats**
- **`.json`**: Structured object with `multiset`, `constraints`, and `partition` keys

🔍 **Validate partition**  
- Use the portable pseudocode in `validate_partition_BMNP.txt`

## 3. State of the Art

📈 **mllmso—largest instances**

- **Medium values**

| # | N         | K        | Limit    | Range           | Filename                             | Optimal |  
|---|-----------|----------|----------|-----------------|--------------------------------------|:-------:|
| 1 | `100`     | `10`     | `10`     | `[1-1,000,000]` | `k-10-limit-10-target-5632681`       | 100% 🟩 | 
| 2 | `1,000`   | `100`    | `10`     | `[1-1,000,000]` | `k-100-limit-10-target-4965012`      | 100% 🟩 | 
| 3 | `10,000`  | `1,000`  | `10`     | `[1-1,000,000]` | `k-1000-limit-10-target-5016830`     | 100% 🟩 | 
| 4 | `100,000` | `10,000` | `10`     | `[1-1,000,000]` | `k-10000-limit-10-target-4998926`    | 100% 🟩 |  

- **Large values**

| #  | N       | K      | Limit  | Range               | Filename                           | Optimal  |  
|----|---------|--------|--------|---------------------|------------------------------------|:--------:|
| 5  | `100`   | `4`    | `25`   | `[1-1,000,000,000]` | `K-4-limit-25-target-12490060607`  | 100% 🟩  | 
| 6  | `500`   | `10`   | `50`   | `[1-1,000,000,000]` | `k-10-limit-50-target-25596179235` | 100% 🟩  | 
| 7  | `1,000` &nbsp; | `12` | `84` | `[1-1,000,000,000]` | `k-12-limit-84-target-42280611559` | 100% 🟩  | 

[+Full list](validate_partition_BMNP-expected_output.html)

> According to 📜 [SOTA_BMNP_25](SOTA_BMNP_25.md):  
> - In theory, instances **#1–#4** are classified as "Easy" and **#5–#7** as "Hard".  
> - In practice, **no known method guarantees optimality** on instances **#2–#7**.

## 4. License

[![License](https://img.shields.io/badge/License-CC%20BY%204.0-blue.svg)](https://creativecommons.org/licenses/by/4.0/)

**Author**: [mllmso](https://orcid.org/0009-0005-3698-7366)

- ✅ Free to **share, use, and adapt**  
- 💼 **Commercial use allowed**  
- ℹ️ **Attribution required** — credit the author  

Review the ⚖️ [Full Legal Code](https://creativecommons.org/licenses/by/4.0/legalcode.en)
