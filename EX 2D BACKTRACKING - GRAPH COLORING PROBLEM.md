# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 15/03/25
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm
1. Initialize the graph and number of vertices v.
2. Define isSafe() to check if a color can be assigned to a vertex without conflict.
3. Use backtracking in graphColouringUtil() to assign colors from 1 to m to each vertex.
4. If all vertices are colored without conflict, return the color assignment.
5. If not possible, return that no solution exists.

## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: Preethi A A
Register Number: 212222110035 
*/
```
```
class Graph:
    def __init__(self,vertices):
        self.v=vertices
        self.graph=[[0 for column in range(vertices)] for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.v):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
    def graphColouringUtil(self,m,colour,v):
        if v==self.v:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColouringUtil(m,colour,v+1):
                    return True
                colour[v]=0
        return False
    def graphColouring(self,m):
        colour=[0]*self.v
        if not self.graphColouringUtil(m,colour,0):
            return False
        return colour
g=Graph(4)
g.graph=[[0,1,1,1],[1,0,1,0],[1,1,0,1],[1,0,1,0]]
m=3
result=g.graphColouring(m)
if result:
    print("Solution exist and Following are the assigned colours:")
    for c in result:
        print(c,end=" ")
else:
    print("f")
```
## Output:

![image](https://github.com/user-attachments/assets/0c093ebc-3eca-4928-9702-24d589051778)

## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
