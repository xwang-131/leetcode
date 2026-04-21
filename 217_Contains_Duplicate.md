# 217. Contains Duplicate #Easy

## 1. Brute Force

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        n = len(nums)
        for i in range(n - 1):
            for j in range(i + 1, n):
                if nums[i] == nums[j]:
                    return True
        return False
```

```
TLE
Time: O(n^2)
Space: O(1)
```

## 2. Sorting

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
        n = len(nums)
        for i in range(n - 1):
            if nums[i] == nums[i + 1]:
                return True
        return False
```

```
Accepted
Time: O(nlogn)
Space: O(1)
```

## 3. HashSet

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        values = set()
        for num in nums:
            if num in values:
                return True
            values.add(num)
        return False
```

```
Accepted
Time: O(n)
Space: O(n)
```
