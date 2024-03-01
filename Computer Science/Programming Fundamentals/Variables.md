








**Magic Numbers:**
A magic number in programming refers to a literal value embedded directly in code without any explanation. This can be problematic because it makes the code less readable and harder to maintain. For example, the number 7 appearing in the code might not be clear what it represents. Instead, it's better to define a descriptive constant to improve clarity and maintainability.

instead of this
Python

```python
if age > 7:
    print("You can vote")
```

Use this:
Python

```python
VOTING_AGE = 7

if age > VOTING_AGE:
    print("You can vote")
```

