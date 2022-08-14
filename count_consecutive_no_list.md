# Count consecutive occurance of numbers, characters in a list.
If `a = [1, 3, 3, 7]` the output would be `[1, 2, 1]`  
If `a  = [a, p, p l, e]` the output would be `[1, 2, 1, 1]`
If `a = []` the output would be `[0]`
```python3
s = "apple"
k = 0
g = []

for i in range(len(s)+1):
    if i == len(s) or s[i] != s[k]:
        g.append(i-k)
        k = i

print(g)
```
Explanation:- We have two variables i and k. Value of i goes to length of
string +1. This is because we are not iterating over the string as usual.
The result would be appended into list g. We take each character(k) and compare 
it with the next character(i). 

Case1: Both are different- We append difference of i and k to list g.
Case2: Both are same (character at index i and k) - The value of k remains same
but the value of i increases unless Case1 is met. THis results in counting same 
character.

Edge Case: All the characters are same: If all the characters are same, The case 1
won't be met. Hence we add another `OR` condition that triggers when the value of 
i is 1 more than the highest index of string (1 more than length of string). When this 
`OR` condition is triggered, the difference is appended to the list g, effectively 
counting all the characters.

k will remain same as start, 0, and i will be equal to length of string hence the 
difference will be length of string(No. of characters).
