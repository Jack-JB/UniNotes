# Pseudocode & Program Analysis

## Recursion

Recursion can be used to define a function, e.g., for the geometric series

> $f q (0) = 1 and f q (k) = q k + f q (k – 1).$

```python
def geometricSeries(q,k):
  if k > 0:
    # Function recursively returns the function call 
    return Q**k + geometricSeries(q, k-1)
  else:
    return 1
```

