# Interview task: Checking the balance of brackets

You are given a string containing various parentheses such as parentheses "()", square "[]" and curly "{}". Your task is to write a function that will determine whether a sequence of parentheses in a string is balanced.

## Examples:

- `"()"` - considered balanced.
- `"{[()]}"` is also considered balanced.
- `"{[()]}"` - considered unbalanced due to the sequence `"(]"`.
- `"(()"` is also considered unbalanced due to the missing closing parenthesis.
   
Your function should return `True` if the parentheses are balanced and `False` if they are unbalanced.

## Note:

The input string may contain other characters, but we only consider parentheses to check the balance.

![](https://media.giphy.com/media/hYrsNV7n0HYi0Xx9QR/giphy.gif)

# Solution

```python
def isValid(s):
    stack = []
    brackets = {'(': ')', '[': ']', '{': '}'}

    for char in s:
        if char in brackets.keys():
            stack.append(char)
        elif char in brackets.values():
            if not stack or brackets[stack.pop()] != char:
                return False

    return not stack


print(isValid('   ()[]{}  '))
print(isValid('   ((()))  '))
print(isValid('   )()     '))
print(isValid('   ([{)]}  '))
```
