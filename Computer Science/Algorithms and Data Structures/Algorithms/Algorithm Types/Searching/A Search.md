

**Summary:**
The A* search algorithm is a popular heuristic search algorithm used for pathfinding and graph traversal. It efficiently finds the shortest path between two points on a graph while taking into account both the cost of reaching a node and the estimated cost to reach the destination from that node. A* is best suited for applications where finding the shortest path is crucial, such as route planning, navigation systems, and video games.

**Algorithm:**

1. Initialize an open list with the starting node and a closed list as empty.
2. While the open list is not empty, do the following:
   - Select the node with the lowest f value (f = g + h, where g is the cost from the start node to the current node, and h is the heuristic estimate of the cost from the current node to the goal).
   - Remove the selected node from the open list and add it to the closed list.
   - For each neighboring node of the selected node:
     - If it is not in the closed list and is not blocked, calculate its f value and add it to the open list.
3. Continue until the goal node is reached or the open list becomes empty.

**Code (Java):**

```java
import java.util.*;

class Node {
    int x, y; // coordinates
    int g; // cost from start
    int h; // heuristic cost
    int f; // f = g + h

    Node(int x, int y, int g, int h) {
        this.x = x;
        this.y = y;
        this.g = g;
        this.h = h;
        this.f = g + h;
    }
}

public class AStarSearch {
    static final int ROW = 9, COL = 10;

    static boolean isValid(int row, int col) {
        return (row >= 0) && (row < ROW) && (col >= 0) && (col < COL);
    }

    static boolean isUnblocked(int grid[][], int row, int col) {
        return (grid[row][col] == 1);
    }

    static boolean isDestination(int row, int col, Node dest) {
        return (row == dest.x) && (col == dest.y);
    }

    static int calculateHValue(int row, int col, Node dest) {
        return Math.abs(row - dest.x) + Math.abs(col - dest.y);
    }

    static void tracePath(Node[][] path, Node dest) {
        System.out.println("Path is:");

        int row = dest.x;
        int col = dest.y;

        Stack<Node> stack = new Stack<>();

        while (!(path[row][col].x == row && path[row][col].y == col)) {
            stack.push(path[row][col]);
            int temp_row = path[row][col].x;
            int temp_col = path[row][col].y;
            row = temp_row;
            col = temp_col;
        }

        stack.push(path[row][col]);

        while (!stack.isEmpty()) {
            Node curr = stack.pop();
            System.out.print("-> (" + curr.x + "," + curr.y + ") ");
        }
    }

    static void aStarSearch(int[][] grid, Node src, Node dest) {
        if (!isUnblocked(grid, src.x, src.y) || !isUnblocked(grid, dest.x, dest.y)) {
            System.out.println("Source or destination is blocked");
            return;
        }

        boolean[][] closedList = new boolean[ROW][COL];
        Node[][] path = new Node[ROW][COL];

        for (int i = 0; i < ROW; ++i)
            for (int j = 0; j < COL; ++j)
                closedList[i][j] = false;

        PriorityQueue<Node> openList = new PriorityQueue<>(Comparator.comparingInt(a -> a.f));

        openList.add(src);

        while (!openList.isEmpty()) {
            Node currentNode = openList.poll();
            closedList[currentNode.x][currentNode.y] = true;

            if (isDestination(currentNode.x, currentNode.y, dest)) {
                System.out.println("Destination found!");
                tracePath(path, dest);
                return;
            }

            int[] rowNum = {-1, 0, 0, 1};
            int[] colNum = {0, -1, 1, 0};

            for (int i = 0; i < 4; ++i) {
                int row = currentNode.x + rowNum[i];
                int col = currentNode.y + colNum[i];

                if (isValid(row, col) && isUnblocked(grid, row, col) && !closedList[row][col]) {
                    int gNew = currentNode.g + 1;
                    int hNew = calculateHValue(row, col, dest);
                    int fNew = gNew + hNew;

                    if (path[row][col] == null || fNew < path[row][col].f) {
                        openList.add(new Node(row, col, gNew, hNew));
                        path[row][col] = currentNode;
                    }
                }
            }
        }

        System.out.println("Failed to find the destination!");
    }

    public static void main(String[] args) {
        int[][] grid = {
                {1, 1, 1, 1, 1, 0, 0, 1, 1, 1},
                {0, 1, 1, 1, 1, 1, 0, 1, 0, 1},
                {0, 0, 1, 0, 1, 1, 1, 0, 0, 1},
                {1, 0, 1, 1, 1, 0, 1, 1, 0, 1},
                {1, 1, 1, 1, 0, 0, 0, 1, 1, 1},
                {1, 1, 0, 0, 0, 1, 1, 1, 1, 0},
                {1, 0, 1, 1, 1, 1, 1, 1, 0, 0},
                {1, 1, 1, 1, 1, 0, 0, 1, 1, 1},
                {0, 1, 0, 0, 1, 1, 1, 0, 0, 1},
        };

        Node src = new Node(0, 0, 0, 0);
        Node dest = new Node(8, 9, 0, 0);

        aStarSearch(grid, src, dest);
    }
}
```

**Complexity:**
- **Time Complexity:** O(V^2), where V is the number of vertices.
- **Space Complexity:** O(V), where V is the number of vertices.

**Advantages:**
1. Finds the shortest path efficiently.
2. Uses heuristic information to guide the search.
3. Suitable for problems where finding the shortest path is crucial.

**Disadvantages:**
1. Requires an admissible heuristic function.
2. May not find the optimal solution in some cases