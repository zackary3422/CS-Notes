
**Summary:**
Depth-First Search is a versatile graph traversal algorithm used to explore and search through graphs or trees. It systematically explores as far as possible along each branch before backtracking. It's particularly useful for solving problems like finding connected components, detecting cycles, and solving puzzles like mazes or Sudoku.

**Algorithm:**

1. Choose a starting vertex or node.
2. Mark the chosen vertex as visited.
3. Explore an adjacent unvisited vertex.
4. If all adjacent vertices are visited, backtrack to the previous vertex.
5. Repeat steps 3-4 until all vertices are visited.

**Code (Java):**

```java
import java.util.*;

class Graph {
    private int V; // No. of vertices
    private LinkedList<Integer> adj[]; // Adjacency Lists

    // Constructor
    Graph(int v) {
        V = v;
        adj = new LinkedList[v];
        for (int i=0; i<v; ++i)
            adj[i] = new LinkedList();
    }

    // Function to add an edge into the graph
    void addEdge(int v,int w) {
        adj[v].add(w);
    }

    // A function used by DFS
    void DFSUtil(int v, boolean visited[]) {
        // Mark the current node as visited and print it
        visited[v] = true;
        System.out.print(v+" ");

        // Recur for all the vertices adjacent to this vertex
        Iterator<Integer> i = adj[v].listIterator();
        while (i.hasNext()) {
            int n = i.next();
            if (!visited[n])
                DFSUtil(n, visited);
        }
    }

    // The function to do DFS traversal. It uses recursive DFSUtil()
    void DFS(int v) {
        // Mark all the vertices as not visited(set as false by default in java)
        boolean visited[] = new boolean[V];

        // Call the recursive helper function to print DFS traversal
        DFSUtil(v, visited);
    }

    public static void main(String args[]) {
        Graph g = new Graph(4);

        g.addEdge(0, 1);
        g.addEdge(0, 2);
        g.addEdge(1, 2);
        g.addEdge(2, 0);
        g.addEdge(2, 3);
        g.addEdge(3, 3);

        System.out.println("Depth First Traversal starting from vertex 2:");

        g.DFS(2);
    }
}
```

**Complexity:**
- **Time Complexity:** O(V + E), where V is the number of vertices and E is the number of edges.
- **Space Complexity:** O(V), where V is the number of vertices.

**Advantages:**
1. Simplicity: Easy to implement and understand.
2. Versatility: Can be used for a wide range of graph problems.
3. Memory Efficiency: Requires memory proportional to the depth of the recursion stack.

**Disadvantages:**
1. May get stuck in infinite loops if cycles are not properly handled.
2. Not suitable for finding the shortest path.
3. Inefficient for large graphs with deep levels of recursion.

**Applications:**
1. Maze solving algorithms.
2. Topological sorting.
3. Solving puzzles like Sudoku or finding paths in a maze.