## 01. Triplets with Smaller Sum

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/count-triplets-with-sum-smaller-than-x5549/1)

### Problem Description

**Task:** Given an array arr[] of distinct integers and an integer sum, count the number of unique triplets of elements whose sum is strictly less than sum. A triplet is identified only by the three elements it contains, so different permutations of the same three elements are counted as one triplet.

#### Examples

##### Example 1

- **Input:**
```text
sum = 2, arr[] = [-2, 0, 1, 3]
```
- **Output:**
```text
2
```
- **Explanation:** Triplets with sum less than 2 are (-2, 0, 1) and (-2, 0, 3).

##### Example 2

- **Input:**
```text
sum = 12, arr[] = [5, 1, 3, 4, 7]
```
- **Output:**
```text
4
```
- **Explanation:** Triplets with sum less than 12 are (1, 3, 4), (5, 1, 3), (1, 3, 7) and (5, 1, 4).

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n^2)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Python)

- **Submitted:** 2026-10-11 11:46:15
- **Status:** Correct
- **Marks:** 4

```python
class Solution:
    def countTriplets(self, sum, arr):
        #code here
        arr.sort()
        n = len(arr)
        result = 0

        for i in range(n - 2):
            left = i + 1
            right = n - 1

            while left < right:
                s = arr[i] + arr[left] + arr[right]

                if s < sum:
                    result += right - left
                    left += 1

                else:
                    right -= 1

        return result
```

*Generated on: 10/11/2026, 11:47:21 AM*