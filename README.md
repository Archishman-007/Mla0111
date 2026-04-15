## BFS
BFS(Graph, start, goal):
    create empty queue Q
    create empty set Visited
    enqueue start into Q
    add start to Visited
    while Q is not empty:
        node = dequeue from Q
        if node == goal:
            return SUCCESS
        for each neighbor of node:
            if neighbor not in Visited:
                add neighbor to Visited
                enqueue neighbor into Q
    return FAILURE
    
## DFS
SDFS(Graph, start, goal):
    create empty stack S
    create empty set Visited
    push start into S
    while S is not empty:
        node = pop from S
        if node == goal:
            return SUCCESS
        if node not in Visited:
            add node to Visited
            for each neighbor of node:
                push neighbor into S
    return FAILURE
    
## Water jug problem
WaterJug(x, y, z):
    create queue Q
    create set Visited
    enqueue (0, 0) into Q
    while Q is not empty:
        (a, b) = dequeue
        if (a == z) or (b == z):
            return SUCCESS
        if (a, b) not in Visited:
            add (a, b) to Visited
            enqueue (x, b)        
            enqueue (a, y)        
            enqueue (0, b)       
            enqueue (a, 0)        
            enqueue pour(a → b)
            enqueue pour(b → a)
    return FAILURE
    
## UCS
UCS(Graph, start, goal):
    create priority queue PQ
    insert (0, start) into PQ   // cost, node
    create empty set Visited
    while PQ is not empty:
        (cost, node) = remove node with smallest cost
        if node == goal:
            return cost
        if node not in Visited:
            add node to Visited
            for each neighbor of node:
                new_cost = cost + edge_cost
                insert (new_cost, neighbor) into PQ
    return FAILURE
    
## A*Search 
A*(Graph, start, goal):
    create priority queue PQ
    insert (f(start), start) into PQ
    g(start) = 0
    while PQ is not empty:
        node = remove node with lowest f(n)
        if node == goal:
            return SUCCESS
        for each neighbor of node:
            g_new = g(node) + cost(node, neighbor)
            f_new = g_new + h(neighbor)
            insert (f_new, neighbor) into PQ
            
## GBFS
GBFS(Graph, start, goal):
    create priority queue PQ
    insert (h(start), start) into PQ
    create empty set Visited
    while PQ is not empty:
        node = remove node with lowest h(n)
        if node == goal:
            return SUCCESS
        add node to Visited
        for each neighbor of node:
            if neighbor not in Visited:
                insert (h(neighbor), neighbor) into PQ
    return FAILURE
