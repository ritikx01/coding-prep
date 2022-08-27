## Sometimes python behaves in an unitended way. Here are some examples.
1. Copied list changes value after assignment  
```python3
l = [1, 2, 3, 4]
b = l
l.append(5)
print(b)
```
Output: `[1, 2, 3, 4, 5]`  
We haven't touched `b` so the expected value should be `[1, 2, 3, 4]`. This happens because  
`b=l` does not copy the list but the reference to itself.  
Consider another example:  
```python3
a = {}
b = []

for i in range(5):
    b.append(i)
    a[i] = b

print(a)
```
Output: `{0: [0, 1, 2, 3, 4], 1: [0, 1, 2, 3, 4], 2: [0, 1, 2, 3, 4], 3: [0, 1, 2, 3, 4], 4: [0, 1, 2, 3, 4]}`  
Expected Output: `{0: [0], 1: [0, 1], 2: [0, 1, 2], 3: [0, 1, 2, 3], 4: [0, 1, 2, 3, 4]}`  
This too happened because `a[i]=b` just copies the reference to `b` in `a[i]` so if b changes at a later stage of code
all the previous reference of b will also change.  
The workaround to this is to copy list by these methods:  
```python3
a[i] = list(b)
a[i] = b[:]		# List slicing is the fastest method
```
A good thread can b found over: https://stackoverflow.com/questions/2612802/how-do-i-clone-a-list-so-that-it-doesnt-change-unexpectedly-after-assignment.  
  
2. Mutable default argument  
```
def func1(a=[]):
    a.append(5)
    print(a)

func1()
func1()
func1()
```
Expected Output: 
```
[5]
[5]
[5]
```
Output:
```
[5]
[5, 5]
[5, 5, 5]
```
This happens because the function `func1` keeps using same in each call. Default parameter values are always evaluated when, and only when, the “def” 
statement they belong to is executed.  
**Note: This happens only with mutable data types.**  
The workaround is to use a placeholder value like 'None'.  
```python3
def func1(a=None):
    if a is None:
        a = []
    a.append(5)
    print(a)

func1()
func1()
func1()
```
Now the statement `a = []` will be evaluated every time the function is called.  
  
3. Passing value to a function
Python uses "Pass by Object Reference" system. This means for immutable data types, passing is like pass-by-value and for mutable data types, it
is like pass-by-reference.
```python3
a = [1, 2, 3, 4]

def func1(arr):
    arr.append(5)

func1(a)
print(a)
```
We haven't modified 'a' so,  
Expected output:`[1, 2, 3, 4]`  
Output: `[1, 2, 3, 4, 5]`  


