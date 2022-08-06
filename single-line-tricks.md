1. Convert a list to dictionary, items as keys and no of occurance as values.
```python3
x = ['ABC','GOOGLE','BCD','GOOGLY', 'A','A', 'LOOGLE', 'GOOGLY', 'GOOGLY']
d = {item:x.count(item) for item in x}
print(d)
```
`{'ABC': 1, 'GOOGLE': 1, 'BCD': 1, 'GOOGLY': 3, 'A': 2, 'LOOGLE': 1}`

2. Find the key with maximum value in dictionaries.
```python3
d = {'ABC': 1, 'GOOGLE': 1, 'BCD': 1, 'GOOGLY': 3, 'A': 2, 'LOOGLE': 1}
x = max(d, key=d.get)
print(x)
```
`GOOGLY`

3. Bit flipping
```python3
num = 1011010
print(''.join(['0' if i is '1' else '1'  for i in num]))
```
Output: `0100101`
