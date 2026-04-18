# CSL7110-Assignment-4

This repository contains the implementation for Assignment 4 of the course **CSL7110: Machine Learning With Big Data**.

The assignment is divided into three parts:

1. Clustering (Farthest First & k-means++)
2. Web Search using Inverted Index
3. PageRank

---

#  Project Structure

```
Assignment_4/
│
├── datasets/
│   ├── Q1- UCI Spam clustering/
│   ├── Q2- webSearch/
│   └── Q3- PageRank/
│
├── P1/
│   └── P1_solution.ipynb
│
├── P2/
│   └── P2_solution.ipynb
│
├── P3/
│   └── P3_solution.ipynb
│
└── README.md
```

---

#  Requirements

Install the required libraries before running:

```bash
pip install numpy pandas scikit-learn matplotlib seaborn networkx
```

(Note: PageRank is implemented in pure Python, Spark was avoided due to environment constraints.)

---

#  Part 1: Clustering

### Algorithms implemented:

* Farthest First Traversal (k-center)
* k-means++

### Dataset:

UCI Spam dataset (4601 points, 58 features)

### What it does:

* Selects cluster centers using two different strategies
* Computes clustering quality using average squared distance

### Key functions:

* `readVectorsSeq()`
* `kcenter()`
* `kmeansPP()`
* `kmeansObj()`

### Output:

* Runtime comparison
* Objective function values
* Coreset experiment (k1 → k reduction)

---

#  Part 2: Web Search (Inverted Index)

### Goal:

Build a simple search engine using an inverted index.

### Features:

* Word → (page, position) mapping
* Stopword removal
* Case normalization
* Basic singular/plural handling
* Query processing

### Supported queries:

* `addPage x`
* `queryFindPagesWhichContainWord x`
* `queryFindPositionsOfWordInAPage x y`

### Dataset:

* `webpages/`
* `actions.txt`
* `answers.txt` (used for verification)

---

#  Part 3: PageRank

### Goal:

Compute PageRank scores for nodes in a graph.

### Approach:

* Adjacency list representation
* Iterative computation (40 iterations)
* Damping factor β = 0.8

### Notes:

* Duplicate edges removed
* Implemented in Python (instead of Spark)
* Small graph used for validation

### Output:

* Top 5 nodes (highest rank)
* Bottom 5 nodes (lowest rank)

---

#  Results Summary

* Clustering shows that k-means++ performs better than coreset approach
* Inverted index correctly matches all expected outputs
* PageRank values are well distributed and converge correctly

---

#  Key Learnings

* Initialization plays a major role in clustering performance
* Inverted index is essential for efficient search
* PageRank is a simple but powerful ranking algorithm

---

#  Assumptions

* Stopword list provided is considered complete
* Singular/plural handled using simple rules
* Graph has no dangling nodes
* Spark implementation skipped due to local setup issues

---

#  How to Run

1. Open each notebook inside its respective folder:

   * `P1/P1_solution.ipynb`
   * `P2/P2_solution.ipynb`
   * `P3/P3_solution.ipynb`

2. Run all cells sequentially

3. Ensure dataset paths are correct relative to notebook location

---

#  Status

* ✔ Part 1 Completed
* ✔ Part 2 Completed
* ✔ Part 3 Completed

---

#  Author

Assignment submission for academic purposes.
