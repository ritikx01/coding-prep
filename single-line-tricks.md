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

4. Return mod of difference b/w two int
```python3
int1, int2 = 3, 5
print(abs(int1 - int2))
```
Output: `2`

5. Change the value of a list index
```python3
x = [0, 1, 2, 3, 3]
x[4] = 4
print(x)
```
Output: `[0, 1, 2, 3, 4]
