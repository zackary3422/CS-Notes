

**Summary:**
Uniform Cost Search is a graph traversal algorithm used to find the shortest path from a given start node to a target node in a weighted graph. Unlike algorithms like Breadth-First Search, UCS considers the cost of reaching each node and always selects the lowest-cost path. UCS is best suited for scenarios where finding the lowest-cost path is crucial, such as route planning in transportation systems or navigation in maps.

**Algorithm:**

1. Initialize an empty priority queue and add the start node with cost 0.
2. While the priority queue is not empty, do the following:
   - Dequeue the node with the lowest cost from the priority queue.
   - If the dequeued node is the target node, return the path to it.
   - Otherwise, expand the dequeued node by considering its neighbors.
   - For each neighbor, calculate the cost of reaching it and add it to the priority queue if it's not already visited or if the new cost is lower than the previously calculated cost.
3. Repeat until the target node is reached or the priority queue becomes empty.

**Code (Java):**

```java
import java.util.*;

class Node implements Comparable<Node> {
    int id;
    int cost;

    Node(int id, int cost) {
        this.id = id;
        this.cost = cost;
    }

    public int compareTo(Node other) {
        return this.cost - other.cost;
    }
}

public class UniformCostSearch {
    static final int INF = Integer.MAX_VALUE;

    static void ucs(List<List<Node>> graph, int start, int target) {
        int n = graph.size();
        int[] parent = new int[n];
        int[] dist = new int[n];
        Arrays.fill(parent, -1);
        Arrays.fill(dist, INF);

        PriorityQueue<Node> pq = new PriorityQueue<>();
        pq.add(new Node(start, 0));
        dist[start] = 0;

        while (!pq.isEmpty()) {
            Node curr = pq.poll();
            int u = curr.id;
            int cost = curr.cost;

            if (u == target)
                break;

            if (cost > dist[u])
                continue;

            for (Node neighbor : graph.get(u)) {
                int v = neighbor.id;
                int weight = neighbor.cost;
                int newCost = dist[u] + weight;

                if (newCost < dist[v]) {
                    dist[v] = newCost;
                    parent[v] = u;
                    pq.add(new Node(v, newCost));
                }
            }
        }

        if (dist[target] == INF) {
            System.out.println("No path exists.");
            return;
        }

        System.out.println("Shortest path cost: " + dist[target]);
        System.out.print("Path: ");
        printPath(parent, target);
    }

    static void printPath(int[] parent, int target) {
        List<Integer> path = new ArrayList<>();
        while (target != -1) {
            path.add(target);
            target = parent[target];
        }
        Collections.reverse(path);
        System.out.println(path);
    }

    public static void main(String[] args) {
        int n = 5;
        List<List<Node>> graph = new ArrayList<>();
        for (int i = 0; i < n; i++)
            graph.add(new ArrayList<>());

        // Example graph
        graph.get(0).add(new Node(1, 4));
        graph.get(0).add(new Node(2, 3));
        graph.get(1).add(new Node(2, 5));
        graph.get(1).add(new Node(3, 2));
        graph.get(2).add(new Node(3, 6));
        graph.get(3).add(new Node(4, 1));

        int start = 0;
        int target = 4;

        System.out.println("Uniform Cost Search:");
        ucs(graph, start, target);
    }
}
```

**Complexity:**
- **Time Complexity:** O((V + E)logV), where V is the number of vertices and E is the number of edges.
- **Space Complexity:** O(V), where V is the number of vertices.

**Advantages:**
1. Finds the lowest-cost path efficiently.
2. Suitable for problems with weighted graphs where finding the shortest path is crucial.
3. Guarantees optimality when all edge costs are non-negative.

**Disadvantages:**
1. Inefficient for graphs with high branching factors or large edge costs.
2. Not suitable for graphs with negative edge costs unless modified.

**Applications:**
1. Route planning and navigation systems.
2. Transportation systems for finding optimal routes.
3. Network routing algorithms.
4. Any scenario where finding the lowest-cost path is essential.