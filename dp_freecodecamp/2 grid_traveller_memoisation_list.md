```python3
def gridTraveller(m, n, memo={}):
    key = '{},{}'.format(m, n)
    key1 = '{},{}'.format(n, m)
    if m == 1 and n == 1:
        return 1
    if key in memo or key1 in memo:
        try:
            return memo[key]
        except:
            return memo[key1]
    if m < 0 or n < 0:
        return 0
    memo[key] = gridTraveller(m - 1, n) + gridTraveller(m, n - 1)
    return memo[key]


print(gridTraveller(300, 300))
```
