---
title: "0054: Spiral Matrix"
---
```python
class Solution:
    def spiralOrder(self, matrix):
	    
        nR = len(matrix)
        nC = len(matrix[0])
        
        initR = 0
        initC = 0
        stopR = nR - 1
        stopC = nC - 1
        
        out = []
        count = 0
        while count < nR * nC:
            
            if count < nR * nC:
                for cx in range(initC, stopC + 1, +1):
                    out.append(matrix[initR][cx])
                    count = count + 1
                initR = initR + 1
            if count < nR * nC:
                for rx in range(initR, stopR + 1, +1):
                    out.append(matrix[rx][stopC])
                    count = count + 1
                stopC = stopC - 1
            if count < nR * nC:
                for cx in range(stopC, initC - 1, -1):
                    out.append(matrix[stopR][cx])
                    count = count + 1
                stopR = stopR - 1
            if count < nR * nC:
                for rx in range(stopR, initR - 1, -1):
                    out.append(matrix[rx][initC])
                    count = count + 1
                initC = initC + 1
        
        return out
```