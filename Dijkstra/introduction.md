## Dijkstra's Algorithm

Dijkstra's Algorithm is used to find the shortest path from a starting point to all other points in a graph. It applies to directed or undirected graphs but requires that edge weights be non-negative.

### General Steps to Solve the Problem:

1. **Graph Representation**:
   - Convert the edges into a directed or undirected `graph`. Graphs are typically represented using adjacency lists or adjacency matrices.

2. **Initialization**:
   - Create a list `result` to record the shortest path to each node. Initialize all nodes with `infinity` (`inf`), except for the starting node which is set to 0.

3. **Priority Queue**:
   - Use a min-heap (commonly the `heapq` module) to manage nodes and their shortest distances to improve algorithm efficiency.

4. **Starting Point Processing**:
   - Initialize the distance of the starting node to 0 and insert it into the priority queue, which will sort nodes based on distance.

5. **Algorithm Iteration**:
   - While the priority queue is not empty, repeat the following steps:

   1. Pop the node with the smallest distance from the priority queue. If this node is the target, return `result[node]`.
   
   2. Iterate through `graph[node]` to get each adjacent node `neighbor` and the edge weight from `node` to `neighbor`.
   
   3. Calculate the new distance from the start node to `neighbor`. If this new distance is smaller than `result[neighbor]`, update `result[neighbor]` and insert the new shortest distance and `neighbor` into the priority queue.

### Notes

- Dijkstra's Algorithm is only applicable to graphs with non-negative edge weights.
- If the graph contains negative edge weights, use the Bellman-Ford Algorithm.
