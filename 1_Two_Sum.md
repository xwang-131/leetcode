# 1. Two Sum 🟢

## 1. Brute Force

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums) - 1):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]
        return [-1, -1]
```

```
Accepted
Time: O(n^2)
```

## 2. HashMap

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hashmap = {} # create a hashmap, {k: num, v: index}
        for i, n in enumerate(nums):
            diff = target - n
            if diff in hashmap:
                return [hashmap[diff], i]
            hashmap[n] = i
        return [-1, -1]
```

```
Accepted
Time: O(n)
Space: O(n)
```
