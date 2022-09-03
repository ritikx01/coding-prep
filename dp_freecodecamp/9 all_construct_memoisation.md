```python3
def all_construct(target, words, memo={}):
    if target == '':
        return [[]]
    if target in memo:
        return memo[target]
    result = []
    
    for word in words:
        if target.find(word) == 0:
            suffix = target[len(word):]
            suffix_ways = all_construct(suffix, words)
            targetways = [[word, *b] for b in suffix_ways if len(suffix_ways)]
            result.extend(targetways)
            memo[target] = result

    return result

print(all_construct('purple', ['purp', 'p', 'ur', 'le', 'purpl']))
print(all_construct('abcdef', ['ab', 'abc', 'cd', 'def', 'abcd']))
print(all_construct('skateboard', ['bo', 'rd', 'ate', 't', 'ska', 'sk', 'boar']))
print(all_construct('enterapotentpot', ['a', 'p', 'ent', 'enter', 'ot', 'o', 't']))
print(all_construct('eee', ['e', 'ee']))

print(all_construct('eeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeeef', ['e', 'ee', 'eee', 'eeee', 'eeeee']))
```
