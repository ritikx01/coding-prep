```python3
def fib(n):
    table = [0] * (n + 2)
    table[1] = 1
    for i in range(n):
        table[i + 1] += table[i]
        table[i + 2] += table[i]
    return table[n]


print(fib(4))  # Result: 3
print(fib(5))  # Result: 5
print(fib(8))  # Result: 21
print(fib(50))  # Result: 12586269025
print(fib(0))  # Result: 0
```
