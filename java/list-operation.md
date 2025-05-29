## 🔹 Problem: **Segmented Reverse List Operations**

### 🧠 **Problem Statement**

You are given a list of integers `nums` and an integer `k`.

1. **Break the list into segments** of size `k`.

    * The last segment may contain fewer than `k` elements if the list size is not a multiple of `k`.
2. **Reverse each segment** individually.
3. Return the resulting list after all such operations.

Then, apply an **optional operation** on each segment:

* `"sum"` → return a list of the segment sums
* `"max"` → return a list of segment max values
* `"none"` → just return the transformed (reversed) list

---

### 🧪 **Examples**

```python
Input:
  nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]
  k = 3
  operation = "sum"

Process:
  Segments: [1,2,3], [4,5,6], [7,8,9]
  Reversed: [3,2,1], [6,5,4], [9,8,7]
  Sums:     [6,15,24]

Output: [6, 15, 24]
```

```python
Input:
  nums = [10, 20, 30, 40, 50]
  k = 2
  operation = "max"

Output: [20, 40, 50] 
```

```python
Input:
  nums = [5, 4, 3, 2, 1]
  k = 2
  operation = "none"

Output: [4, 5, 2, 3, 1]
```

---

### ⚙️ Constraints
* `1 <= nums.length <= 10^5`
* `1 <= k <= nums.length`
* `operation` is one of `"sum"`, `"max"`, `"none"`
---