# DSA Graphs - Set 1

📋 Topics Included: 3

1. Graph Representation (Adjacency List)
2. Breadth First Search (BFS)
3. Depth First Search (DFS)

---

# 1. Graph Representation (Adjacency List)

## Description

A graph can be represented using an adjacency list, where each vertex stores a list of its neighboring vertices.

Example Graph:

```text
0 ---- 1
|      |
|      |
2 ---- 3
```

Adjacency List Representation:

```text
0 -> 1, 2
1 -> 0, 3
2 -> 0, 3
3 -> 1, 2
```

## C++ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n = 4;

    vector<vector<int>> adj(n);

    adj[0].push_back(1);
    adj[1].push_back(0);

    adj[0].push_back(2);
    adj[2].push_back(0);

    adj[1].push_back(3);
    adj[3].push_back(1);

    adj[2].push_back(3);
    adj[3].push_back(2);

    for (int i = 0; i < n; i++) {
        cout << i << " -> ";

        for (int neighbor : adj[i])
            cout << neighbor << " ";

        cout << endl;
    }

    return 0;
}
```

### Time Complexity

O(V + E)

### Space Complexity

O(V + E)

---

# 2. Breadth First Search (BFS)

## Description

Breadth First Search (BFS) is a graph traversal algorithm that visits vertices level by level.

BFS uses a **queue** to keep track of the vertices to visit.

Example:

```text
0 ---- 1
|      |
|      |
2 ---- 3
```

Starting from vertex `0`, one possible BFS traversal is:

```text
0 1 2 3
```

## C++ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

void bfs(int start, vector<vector<int>>& adj) {
    int n = adj.size();

    vector<bool> visited(n, false);
    queue<int> q;

    visited[start] = true;
    q.push(start);

    while (!q.empty()) {
        int node = q.front();
        q.pop();

        cout << node << " ";

        for (int neighbor : adj[node]) {
            if (!visited[neighbor]) {
                visited[neighbor] = true;
                q.push(neighbor);
            }
        }
    }
}

int main() {
    int n = 4;

    vector<vector<int>> adj(n);

    adj[0].push_back(1);
    adj[1].push_back(0);

    adj[0].push_back(2);
    adj[2].push_back(0);

    adj[1].push_back(3);
    adj[3].push_back(1);

    adj[2].push_back(3);
    adj[3].push_back(2);

    bfs(0, adj);

    return 0;
}
```

### Time Complexity

O(V + E)

### Space Complexity

O(V)

---

# 3. Depth First Search (DFS)

## Description

Depth First Search (DFS) is a graph traversal algorithm that explores as far as possible along one path before backtracking.

DFS can be implemented using **recursion** or a **stack**.

Example:

```text
0 ---- 1
|      |
|      |
2 ---- 3
```

Starting from vertex `0`, one possible DFS traversal is:

```text
0 1 3 2
```

## C++ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

void dfs(int node, vector<vector<int>>& adj, vector<bool>& visited) {
    visited[node] = true;

    cout << node << " ";

    for (int neighbor : adj[node]) {
        if (!visited[neighbor]) {
            dfs(neighbor, adj, visited);
        }
    }
}

int main() {
    int n = 4;

    vector<vector<int>> adj(n);

    adj[0].push_back(1);
    adj[1].push_back(0);

    adj[0].push_back(2);
    adj[2].push_back(0);

    adj[1].push_back(3);
    adj[3].push_back(1);

    adj[2].push_back(3);
    adj[3].push_back(2);

    vector<bool> visited(n, false);

    dfs(0, adj, visited);

    return 0;
}
```

### Time Complexity

O(V + E)

### Space Complexity

O(V)
