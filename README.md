# SC2001: Dijkstra's Algorithm

## Dijksta's: 
An algorithm that finds the shortest path from source to goal node. 

Key points: 
- Only works for non-negative weights 
- Works for both undirected and directed (convert directed to undirected by adding two directions) 

## Pseudocode with comments

```java
Dijkstra (Graph G, Node source) {
	for each vertex v {
		d[v] = infinity; 
		pi[v] = null pointer; 
		S[v] = 0; 
	}
}

// the distance from source to itself is always 0 
d[source] = 0; 

put all vertices in priority queue, Q, in d[v]'s increasing order; 

// the one with the lowest weight gets highest priority 

while not Empty(Q) {
	u = ExtractCheapest(Q); 
	S[u] = 1; // this adds vertex u to the solution set (meaning, it forms the tree) 
	for each vertex v adjacent to u {
			// if v is not part of Solution, then the value is larger than 
			// d[u] + w[u,v] < d[v] checks for if it is the first node. and if there exists a path that is shorter than the current "estimated distance" of vertex v 
			// this will always be true if it's the first iteration meaning, u = 0; 
			if (S[v] != 1 and d[u] + w[u,v] < d[v]) {
				
				remove v from Q; 
				// update the estimated distance to a shorter one 
				d[v] = d[u] + w[u,v];
				// update its predecessor
				pi[v] = u; 
				
		}
	}
}
```
## Reference
- https://www.youtube.com/watch?v=XB4MIexjvY0&t=821s
- Computer Algorithms - Baase Van Gelder
