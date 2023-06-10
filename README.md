# Iterative-Deepening-Depth-First-Search--IDDFS-

Iterative Deepening Depth-First Search (IDDFS) is a graph traversal algorithm that combines the depth-first search (DFS) strategy with a iterative deepening approach. It aims to find a target node in a graph while limiting the search depth.

Here's an explanation of the algorithm based on the provided code:

1. The code defines a `Graph` class that represents a directed graph using an adjacency list representation. The class has methods to add edges to the graph and perform the IDDFS algorithm.

2. The `DLS` (Depth-Limited Search) method is a recursive function that performs a depth-limited search from a given source vertex (`src`) up to a maximum depth (`maxDepth`). It returns `True` if the target vertex (`target`) is found within the depth limit, and `False` otherwise.

3. In the `DLS` method, the base cases are checked:
   - If the source vertex is the target vertex, it means the target is found, so the method returns `True`.
   - If the maximum depth limit is reached or exceeded, it means the target is not found within the depth limit, so the method returns `False`.

4. If the base cases are not met, the method recursively calls itself for each adjacent vertex of the source vertex.
   - If the recursive call returns `True`, it means the target vertex is found, so the method returns `True`.
   - If the recursive call returns `False`, the loop continues to check the next adjacent vertex.

5. The `IDDFS` method (Iterative Deepening Depth-First Search) performs the main IDDFS algorithm. It repeatedly calls the `DLS` method with increasing depth limits from 0 to the maximum depth.

6. In the `IDDFS` method, a loop runs from 0 to `maxDepth` (exclusive).
   - For each depth limit `i`, the `DLS` method is called with the current depth limit. If it returns `True`, it means the target vertex is found within the depth limit, and the method returns `True`.
   - If the loop completes without finding the target vertex within the maximum depth, the method returns `False`.

7. The code creates a graph object `g` with 7 vertices and adds edges to it.

8. The target vertex is set to 3, the maximum depth is set to 3, and the source vertex is set to 0.

9. The `IDDFS` method is called with the source, target, and maximum depth as parameters. If it returns `True`, it means the target is reachable from the source within the maximum depth, so the corresponding message is printed.
   - In the provided example, since there is a path from vertex 0 to vertex 3 within a depth of 3, the message "Target is reachable from the source within max depth" is printed.

10. If the `IDDFS` method returns `False`, it means the target is not reachable from the source within the maximum depth, so the corresponding message is printed.
