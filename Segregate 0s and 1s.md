## 01. Segregate 0s and 1s

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/segregate-0s-and-1s5106/1)

### Problem Description

**Task:** Given an array arr[] consisting of only 0's and 1's. Modify the array in-place to segregate 0s onto the left side and 1s onto the right side of the array. Examples :Input: arr[] = [0, 1, 0, 1, 0, 0, 1, 1, 1, 0]

#### Examples

##### Example 1

- **Output:**
```text
[1, 1]
```
- **Explanation:** There are no 0s in the given array, so the modified array is [1, 1]

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-05 22:30:10
- **Status:** Correct
- **Marks:** 2

```python
class Solution:
    def segregate0and1(self, arr):
        # code here
        i = 0
        j = len(arr) - 1
        while i < j:
            if arr[i] == 0:
                i+=1
                
            elif arr[j] == 1:
                j-=1
                
            elif arr[i] == 1 and arr[j] == 0:
                arr[i], arr[j] = arr[j], arr[i]
                i += 1
                j -=1
                
        return arr
```

*Generated on: 10/5/2026, 10:30:26 PM*