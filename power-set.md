# Power Set

## Cracking the Coding Interview (CTCI) 8.4

<br />

## Question

You are given a set. Write a method that returns all subsets of a set.

```
Input - [1,2,3]
Output - [[],[1],[2],[3],[1,2],[1,3],[2,3],[1,2,3]]
```

 />

<details>
  <summary>Solution</summary>


When adding an element to a set, we can find all new subsets by copying all of the old subsets, and adding the new element to each. We can get all subsets by making recursive calls to smaller sets. 

```python
import copy
def get_subsets(a_set, index=None):
    if index is None:
        index = len(a_set) - 1
    if index == -1:
        return [[]]
    old_subsets = get_subsets(a_set, index - 1)
    new_subsets = []
    item = a_set[index]
    for val in old_subsets:
        new_subsets.append(val)
        entry = copy.deepcopy(val)
        entry.append(item)
        new_subsets.append(entry)
    return new_subsets
```

The time complexity is $$O(n2^n)$$ and the space complexity is $$O(n2^n)$$.

</details>
