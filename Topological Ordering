# Topological Ordering

A **topological ordering** is an ordering of the vertices of a directed graph such that:

> **Every directed edge points forward.**

For every edge `u → v`, `u` appears before `v`.

Example:

```text
A → B
A → C
B → D
C → D
```

One valid ordering:

```text
A, B, C, D
```

A graph can have **multiple valid topological orderings**.

---

## DAGs

A **DAG (Directed Acyclic Graph)** is a directed graph with **no directed cycles**.

A directed graph has a topological ordering **if and only if it is a DAG**.

```text
Topological ordering exists
        ⇕
Graph is a DAG
        ⇕
Graph has no directed cycle
```

A cycle such as:

```text
A → B → C → A
```

makes a topological ordering impossible.

---

## Applications

Used when objects have **precedence/dependency constraints**:

* Course prerequisites
* Task scheduling
* Project planning
* Build systems
* Dependency resolution

---

# Computing a Topological Ordering

Two common approaches:

1. **Sink-vertex algorithm**
2. **DFS-based algorithm**

---

## Sink-Vertex Algorithm

A **sink** is a vertex with **no outgoing edges**.

**Key fact:**

> Every DAG has at least one sink.

### Algorithm

1. Find a sink.
2. Assign it the highest available label.
3. Remove it and its incoming edges.
4. Repeat until all vertices are removed.
5. The labels give the topological ordering.

---

## DFS-Based Algorithm

Use **DFS** and assign vertices a label when they finish.

```text
DFS(v):

    mark v as explored

    for each outgoing edge v → w:
        if w is unexplored:
            DFS(w)

    assign current label to v
    decrease label
```

Start with:

```text
label = |V|
```

Run DFS from every unvisited vertex.

The vertices in **decreasing order of finishing time** form a topological ordering.

### Why?

For an edge `u → v`, DFS finishes `v` before `u` when `v` is explored through `u`.

Therefore:

```text
finish(v) < finish(u)
```

So decreasing finishing times places `u` before `v`.

---

## NB

* Topological ordering only exists for **DAGs**.
* A directed cycle means **no topological ordering exists**.
* DFS can detect cycles using the set of vertices currently being explored.


