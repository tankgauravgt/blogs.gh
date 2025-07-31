---
title: "0073: Set Matrix Zeroes"
---
```python
class Solution:
    def setZeroes(self, matrix):
	    
        nR = len(matrix)
        nC = len(matrix[0])
        
        hasRow0 = False
        hasCol0 = False
        
        m = matrix
        for rx in range(nR):
            if m[rx][0] == 0:
                hasCol0 = True
        
        for cx in range(nC):
            if m[0][cx] == 0:
                hasRow0 = True
        
        for rx in range(1, nR):
            for cx in range(1, nC):
                if m[rx][cx] == 0:
                    m[0][cx] = 0
                    m[rx][0] = 0
        
        for rx in range(1, nR):
            if m[rx][0] == 0:
                for cx in range(1, nC):
                    m[rx][cx] = 0
        
        for cx in range(1, nC):
            if m[0][cx] == 0:
                for rx in range(1, nR):
                    m[rx][cx] = 0
        
        if hasRow0:
            for cx in range(nC):
                m[0][cx] = 0
        if hasCol0:
            for rx in range(nR):
                m[rx][0] = 0
```