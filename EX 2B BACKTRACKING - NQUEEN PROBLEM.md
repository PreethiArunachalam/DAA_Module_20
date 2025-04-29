# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE: 08/03/2025
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.

## Algorithm
1. Input:Read integer N, which specifies the size of the board (NxN) and the number of queens.
2. Initialize an empty board of size NxN with all cells set to 0 (representing an empty space).
3. Start placing queens column by column, starting from the first column (col = 0).
4. For each row in the current column:
Check if it's safe to place a queen by:
Ensuring no other queen is placed in the same row to the left of the current column.
Ensuring no other queen is placed in the upper diagonal (to the left).
Ensuring no other queen is placed in the lower diagonal (to the left).
5. If it's safe:
Place the queen in the current cell (set board[row][col] = 1).
Recursively attempt to place the next queen in the next column (col + 1).
6. Backtrack if placing the queen leads to an invalid configuration:
If no valid placement is possible in the next column, remove the queen (set board[row][col] = 0) and try placing it in the next row.
7. Repeat the process until all queens are placed (i.e., all columns are filled).
8. If all queens are placed successfully, print the board as the solution.
9. If placing queens is not possible (i.e., no valid configuration), print "Solution does not exist."

## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: Preethi A A
Register Number: 212222110035 
*/
```
```
global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if(col>=N):
        return True
    for i in range(N):
        if isSafe(board,i,col):
            board[i][col]=1
            if(solveNQUtil(board,col+1)):
                return True
            board[i][col]=0
    return False
      
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()
```
## Output:

![image](https://github.com/user-attachments/assets/e3bbfb82-6baa-4b59-9dea-1bedc8a1ead0)

## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
