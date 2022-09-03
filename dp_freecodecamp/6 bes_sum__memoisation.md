```python3
def bestSum(total, grid, memo={}):
    if total == 0:
        return []
    if total < 0:
        return None
    if total in memo:
        return memo[total][:]
    shortest_combination = None

    for i in grid:
        remainderResult = bestSum(total - i, grid)
        if remainderResult is not None:
            remainderResult.append(i)
            combination = remainderResult
            if shortest_combination is None or len(combination) < len(shortest_combination):
                shortest_combination = combination
    memo[total] = shortest_combination[:]
    return shortest_combination
    
print(bestSum(100, [1, 4, 25]))
```
