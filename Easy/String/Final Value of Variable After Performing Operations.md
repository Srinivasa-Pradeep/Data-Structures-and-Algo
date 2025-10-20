## [Final Value of Variable After Performing Operations](https://leetcode.com/problems/final-value-of-variable-after-performing-operations/description/) - Notes

### 🧾 Problem Statement

There is a programming language with only **four operations** and **one variable** `X`:

* `++X` and `X++` → **increment** the value of `X` by 1
* `--X` and `X--` → **decrement** the value of `X` by 1

Initially, `X = 0`.

Given an array of strings `operations` containing a list of these operations, return the **final value** of `X` after performing all of them.

---

### 🧠 Example 1

**Input:**
`operations = ["--X","X++","X++"]`
**Output:**
`1`
**Explanation:**

```
X = 0
--X → X = -1
X++ → X = 0
X++ → X = 1
```

---

### 🧠 Example 2

**Input:**
`operations = ["++X","++X","X++"]`
**Output:**
`3`
**Explanation:**

```
X = 0
++X → X = 1
++X → X = 2
X++ → X = 3
```

---

### 🧠 Example 3

**Input:**
`operations = ["X++","++X","--X","X--"]`
**Output:**
`0`
**Explanation:**

```
X = 0
X++ → X = 1
++X → X = 2
--X → X = 1
X-- → X = 0
```

---

### 🧩 Code

```python
class Solution:
    def finalValueAfterOperations(self, operations: List[str]) -> int:
        X = 0
        for op in operations:
            if '+' in op:
                X += 1
            else:
                X -= 1
        return X
```

---

### 💡 Intuition

Every operation either **adds or subtracts 1**.
The position of `++` or `--` (before or after `X`) doesn’t matter — both modify `X` the same way.

---

### ⚙️ Algorithm

1. Initialize `X = 0`.
2. Loop through each operation:

   * If `'+'` in operation → `X += 1`
   * Else → `X -= 1`
3. Return `X`.

---

### ⏱️ Complexity

* **Time:** `O(n)`
* **Space:** `O(1)`

---

want me to add a one-line **mnemonic** for remembering the pattern (`++ = +1`, `-- = -1`) like how you like keeping in your notes, da?
