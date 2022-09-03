Question: Given a word and an array of words, find out if we can construct the words using the words from array. 
The words from array can be used as many times as needed.
```python3
def can_construct(target, words, memo={}):
    if len(target) == 0:
        return []
    if target in memo:
        return memo[target]
    for word in words:
        if target.find(word) == 0:
            new = target[len(word):]
            value = can_construct(new, words)
            if value is not False:
                value.append(word)
                memo[target] = value[:]
    memo[target] = False
    return False


print(can_construct('eee', ['e', 'ee', 'eee', 'eeee', 'eeeee']))
```
