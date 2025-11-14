# HW02 — Courier Handoffs (BFS Shortest Path)

**Story intro.**  
A parcel moves between couriers. Each handoff is allowed only between certain pairs who meet in the same area. You must find the **fewest handoffs** from a start courier to a target courier.

**Technical description.**  
- **Input:** `graph` as adjacency list `dict` (undirected). Start `s`, target `t`.  
- **Output:** `bfs_path(graph, s, t)` → list of nodes for a shortest path by **number of edges**. If no path, return `None`.  
- **Constraints:**  
  - All node names are strings.  
  - If `s == t`, return `[s]`. If either missing from `graph`, return `None`.  
- **Expected complexity:** **O(V+E)** time, **O(V)** space.

## ESL scaffold with the 8 Steps
**Steps 1–5 (explicit prompts)**
1. **Read & Understand:** What does “fewest handoffs” mean in graphs?  
2. **Re-phrase:** Say: “We search in layers and stop when we see the target.”  
3. **Identify I/O:** Name inputs and the output path shape.  
4. **Break down:** What data do we need? (queue, visited, parent)  
5. **Pseudocode:** Write the loop. When do you stop? How do you rebuild the path?

**Steps 6–8 (hints)**
- **Write:** Turn pseudocode into Python using `collections.deque`.  
- **Debug:** Print `u`, `queue`, and `parent` on a tiny graph.  
- **Optimize:** State O(V+E) and why.

## Hints
- Use a `parent` dict to rebuild the path at the end.  
- Check `s == t` at the start.  
- Push neighbors only if not visited.

## Run tests locally
```bash
python -m pytest -q
```
## FAQ
Q: Directed or undirected? A: Undirected for this story.

Q: Multiple shortest paths? A: Any one shortest path is fine.

Q: Missing nodes? A: Return None.

Q: Read stdin? A: No. Implement the function.

Q: Big-O? A: Time O(V+E), space O(V).

Q: Why did I get KeyError? A: Ensure s and t exist first.

Q: My path is reversed. A: Rebuild from t back to s, then reverse.