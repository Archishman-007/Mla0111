## BFS
Start with an empty queue and visited set
Insert the start node into the queue
Mark the start node as visited
While queue is not empty:
Remove front node
If it is goal → stop
Else add all unvisited neighbors to queue
Mark them as visited
End
## DFS
Start with an empty stack and visited set
Push start node onto stack
While stack is not empty:
Pop top node
If not visited:
Mark as visited
Process node
Push all unvisited neighbors onto stack
End
## Water jug problem
Represent state as (x, y)
Initialize queue with (0, 0)
Mark as visited
While queue is not empty:
Remove current state
If goal achieved → stop
Generate all possible states:
Fill jug1
Fill jug2
Empty jug1
Empty jug2
Pour jug1 → jug2
Pour jug2 → jug1
Add unvisited states to queue
End
## UCS
nitialize priority queue with (cost=0, start node)
Create a visited set
While queue is not empty:
Remove node with lowest cost
If it is goal → return solution
If not visited:
Mark visited
Add all neighbors with updated cost
End
## A*Search 
Initialize priority queue with:

f(n) = g(n) + h(n)
Insert start node with f(n)
While queue is not empty:
Remove node with lowest f(n)
If goal reached → stop
Else:
Expand neighbors
Compute:
g(n) = path cost
h(n) = heuristic
f(n) = g(n) + h(n)
Add to queue
End
## GBFS
nitialize priority queue with heuristic value h(n)
Insert start node
While queue is not empty:
Remove node with lowest h(n)
If goal reached → stop
Else:
Add neighbors to queue
End
