# Ex-3-Implement-Depth-First-Search-Traversal-of-a-Graph

Name:Vasanth kumar V

Register Number:2305002027

### Aim:
To Implement Depth First Search Traversal of a Graph using Python 3.

### Theory:

Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. 
The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). 
Use a Boolean visited array to avoid processing a node more than once. 
A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. 
The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking. 

### Algorithm:

Step 1: Construct a Graph with Nodes and Edges

Step 2: Depth First Search Uses Stack and Recursion

Step 3:Insert a START node to the STACK

Step 4:Find its Successors Or neighbors and Check whether the node is visited or not

Step 5:If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.


### Program:
```
from collections import defaultdict

def dfs(graph, start, visited, path):
    path.append(start)
    visited[start] = True
    for neighbour in graph[start]:
        if not visited[neighbour]:
            dfs(graph, neighbour, visited, path)
    return path

graph = defaultdict(list)
edges = input("Enter all edges (u v pairs, space-separated): ").split()

for i in range(0, len(edges), 2):
    u, v = edges[i], edges[i + 1]
    graph[u].append(v)
    graph[v].append(u)

print("Graph:", dict(graph))

start = 'A'
visited = defaultdict(bool)
path = []
print("DFS Traversal Path:", dfs(graph, start, visited, path))

```

### Sample Input:
A B
A C
B D
B E
C E
D E

### Sample Output:

Enter all edges (u v pairs, space-separated): A B A C B D B E C E D E

Graph: {'A': ['B', 'C'], 'B': ['A', 'D', 'E'], 'C': ['A', 'E'], 'D': ['B', 'E'], 'E': ['B', 'C', 'D']}
DFS Traversal Path: ['A', 'B', 'D', 'E', 'C']

**Result:
Thus the  Implementation Depth First Search Traversal of a Graph using Python is successfully verified.
