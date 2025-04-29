# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE: 11/03/25
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.

## Algorithm
1. Input:Read the size of the array size and the elements of the array a[].
2. Read the target sum to check if a subset with the sum equal to target exists.
3. Define the recursive function SubsetSum(a, i, sum, target, n):
4. Base case 1: If i == n, check if the current sum is equal to the target:
 If sum == target, return True (a valid subset has been found).
 Otherwise, return False.
5. Base case 2: If the subset sum has not been found yet, recursively try two possibilities:
 Include the current element a[i] in the sum: SubsetSum(a, i+1, sum + a[i], target, n).
 Exclude the current element a[i] from the sum: SubsetSum(a, i+1, sum, target, n).
6. Call the recursive function SubsetSum starting from index 0 with an initial sum of 0.
7. If a valid subset is found, print all the elements in the array and "True, subset found."
8. If no valid subset is found, print all the elements in the array and "False, subset not found."

## Program:
```
/*
Program to implement Subset sum problem.
Developed by: Preethi A A
Register Number: 212222110035
*/
```
```
def SubsetSum(a,i,sum,target,n):
    if(i==n):
        return sum==target
    if SubsetSum(a,i+1,sum+a[i],target,n):
        return True
    if SubsetSum(a,i+1,sum,target,n):
        return True
        
    return False

a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)
if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")

```
## Output:

![image](https://github.com/user-attachments/assets/cc3e4abb-d434-4fb2-9e48-f2e5a3ac7c5a)

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
