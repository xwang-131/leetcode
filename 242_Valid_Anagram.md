# 242. Valid Anagram 🟢

## 1. HashMap

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        count_s, count_t = {}, {}
        for i in range(len(s)):
            count_s[s[i]] = 1 + count_s.get(s[i], 0) # returns 0 as default if key not found
            count_t[t[i]] = 1 + count_t.get(t[i], 0)
        for k in count_s:
            if count_s[k] != count_t.get(k, 0):
                return False
        return True
```

```
Accepted
Time: O(s+t)
Space: O(s+t)
```

## 2. Sorting

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return sorted(s) == sorted(t)
```

```
Accepted
Time: O(nlogn) or O(n^2), depending on the built-in function
Space: O(1), sorting excluded
```
