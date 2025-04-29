# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 05/03/25
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.

## Algorithm
1. Start and initialize a solution matrix sol of size N×N with all zeros.
2. Start from cell (0, 0); if it's safe (value is 1), mark it as part of the path in sol.
3. Try to move right (x, y+1); if the path leads to the destination, return True.
4. If moving right doesn't work, try moving down (x+1, y); if successful, return True.
5. If neither move is valid, backtrack by unmarking (set sol[x][y] to 0), and return False.

## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: Preethi A A 
Register Number: 212222110035
*/
```
```
N = 4
 

def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 

def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
 

def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     

def solveMazeUtil(maze, x, y, sol):
    if (x==N-1 and y==N-1):
        sol[x][y]=1
        return True
    elif (isSafe(maze,x,y)==True):
        sol[x][y]=1
        if(solveMazeUtil(maze,x+1,y,sol)==True):
            return True
        if(solveMazeUtil(maze,x,y+1,sol)==True):
            return True
        sol[x][y]=0
        return False
    return False
    
# Driver program to test above function
if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```
## Output:

![image](https://github.com/user-attachments/assets/fe90185b-eb92-44a0-8d51-b4b874ced5ae)

## Result:
The Rat in/ a Maze program executed successfully, and a valid path from the start to the destination was found and display.
