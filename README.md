Floyd–Warshall Algorithm (C++)

📌 Overview

This repository contains a C++ implementation of the Floyd–Warshall Algorithm, a dynamic programming algorithm used to find the shortest paths between all pairs of vertices in a weighted graph.

The algorithm works with both directed and undirected graphs and supports negative edge weights, provided the graph does not contain a negative weight cycle.

---

🚀 Features

- Finds the shortest path between every pair of vertices.
- Supports positive and negative edge weights.
- Detects the shortest distances in a weighted graph.
- Simple and easy-to-understand C++ implementation.
- Time-efficient for dense graphs.

---

📚 Theory

The Floyd–Warshall Algorithm is based on Dynamic Programming.

Instead of finding the shortest path from one source, it computes the shortest paths between every pair of vertices.

Initially, the adjacency matrix stores the direct distances between vertices. The algorithm then repeatedly checks whether using an intermediate vertex can produce a shorter path.

Dynamic Programming Relation

dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])

Where:

- "dist[i][j]" = Current shortest distance from vertex "i" to vertex "j"
- "k" = Intermediate vertex

The algorithm performs this update for every possible intermediate vertex.

---

🧠 Algorithm Steps

1. Initialize the distance matrix using the graph.
2. Set the distance from every vertex to itself as "0".
3. For every vertex "k":
   - Consider it as an intermediate vertex.
   - Update all pairs "(i, j)" using:
     dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j]);
4. After all iterations, the matrix contains the shortest distances between every pair of vertices.

---

⏱️ Time Complexity

Operation| Complexity
Time Complexity| O(V³)
Space Complexity| O(V²)

Where V is the number of vertices.

---

✅ Advantages

- Computes shortest paths between all pairs of vertices.
- Easy to implement.
- Handles negative edge weights.
- Suitable for dense graphs.

---

❌ Limitations

- Cannot correctly solve graphs containing negative weight cycles.
- High time complexity ("O(V³)") makes it inefficient for very large graphs.

---

📖 Applications

- Network routing
- Road map navigation
- Airline route optimization
- Social network analysis
- Graph analysis
- Distance matrix computation

---

💻 Sample C++ Logic

for (int k = 0; k < V; k++) {
    for (int i = 0; i < V; i++) {
        for (int j = 0; j < V; j++) {
            if (dist[i][k] + dist[k][j] < dist[i][j]) {
                dist[i][j] = dist[i][k] + dist[k][j];
            }
        }
    }
}

---

📥 Input

- Number of vertices
- Weighted adjacency matrix
- Use a large value (such as "INF") where no direct edge exists.

---

📤 Output

- Shortest distance matrix containing the minimum distance between every pair of vertices.

---

📌 Example

Input Matrix

0   5   INF 10
INF 0   3   INF
INF INF 0   1
INF INF INF 0

Output Matrix

0 5 8 9
INF 0 3 4
INF INF 0 1
INF INF INF 0

---

📂 Repository Structure

├── FloydWarshall.cpp
├── README.md
└── LICENSE

---

🛠️ Requirements

- C++11 or later
- Any C++ compiler (GCC, Clang, MSVC)

Compile using:

g++ FloydWarshall.cpp -o FloydWarshall
./FloydWarshall

---

👨‍💻 Author

Developed as a Data Structures and Algorithms (DSA) learning project in C++.

---

⭐ If you found this project helpful, consider giving it a star!
