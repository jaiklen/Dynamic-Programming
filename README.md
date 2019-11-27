# Dynamic-Programming
Given a set of non-negative integers, and a value sum, determine if there is a subset of the given set with sum equal to given sum.
            
        
    def dynamic(ar,n): # decrease tab space
    arr = [[False for i in range(n+1)] for j in range (len(ar)+1)]

    for l in range(len(ar)+1):
        arr[l][0] = True
    for k in range(1,n+1):
        arr[0][k] = False

    for i in range(1,len(ar)+1):
        for j in range(1,n+1):
            if(j< ar[i-1]):
                arr[i][j] = arr[i-1][j]
            if(j>= ar[i-1]):
                arr[i][j] = arr[i-1][j] or arr[i-1][j-ar[i-1]]

        
    return arr[len(ar)][n]
    # decrease tabs space of below lines from 
    ar = [3, 34, 4, 12, 5, 2] 
    n = 9
    print(dynamic(ar,n))
