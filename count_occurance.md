For counting occurance only, Method 2 also works but if we want to perform any other operation
like sorting or to get sum of some elements, list is not recommended, indeed we can use dictionaries
which are slower than lists in general, but much faster when performing an operation like search etc.
Method 1:  
```python3
a = [1, 2, 3, 4, 4]
occurrence = {}
for i in a:
    if i not in occurrence:
        occurrence[i] = 0
    occurrence[i] += 1
print(occurrence)
```
We can also use `Counter()` from builtin library collections. `from collections import Counter`.
One more advantage of this method is that we don't need to use `ord()` function for counting letters
like in the method 2.

Method 2:  
When counting occurance of letters or numbers in very large strings or very large numbers,
say, the string is a paragraph of words or the number has 100 digits, we can use counting sort
algorithm.  
  
numbers = 02345678922  
  
We initialize a list with 10 zeroes, each representing the time the index number occurred 
in the given large number.  
Eg: For above 'numbers', we will initially have a list [0, 0, 0, 0, 0, 0, 0, 0, 0, 0].
We know the following:  
|Number	|Occurance|
|-------|---------|
|0	|1	  |
|1	|0	  |
|2	|3	  |
|3	|1	  |
|4	|1	  |
|5	|1	  |
|6	|1	  |
|7	|1	  |
|8	|1	  |
|9	|1	  |

So our final list would be, [1, 0, 3, 1, 1, 1, 1, 1, 1, 1]
with each index representing the number of times it is present in the large number.
```python3
def countingSort(string):
    res = [0] * 26              # Create list
    for i in string:
        res[ord(i)-97] += 1     # ord(i)
    return res


s = "ritik"
result = countingSort(s)
print(result)
```
To index value of an alphabet is calculated by subtracting 97 from it's ascii value.

