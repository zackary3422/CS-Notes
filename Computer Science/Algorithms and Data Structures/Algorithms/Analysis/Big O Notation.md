## Big O Notation

#### **What is Big O Notation?**

Big O Notation is a mathematical notation used to describe the **efficiency of an algorithm**. It allows us to express the upper bound (worst case) of an algorithm's time complexity as the input size approaches infinity. In other words, it tells us how the running time of an algorithm **scales with increasing input size**.

#### **Why is it important?**

Big O Notation is important for several reasons:

- **Helps us compare algorithms:** We can use Big O Notation to compare the efficiency of different algorithms for solving the same problem. This helps us choose the most efficient algorithm for a particular application.
- **Predicts algorithm behavior:** Big O Notation helps us predict how an algorithm will perform for large inputs. This is important for optimizing programs and ensuring that they run within acceptable time constraints.
- **Provides a common language:** Big O Notation is a standard way to discuss the efficiency of algorithms. This makes it easy for programmers to communicate and understand each other's work.

##### **Basic Concepts:**

- **Constant time (O(1))**: The running time of the algorithm does not depend on the input size. It remains constant regardless of how many elements are in the input.


```python
def find_max(array):
  max_value = array[0]
  for i in range(1, len(array)):
    if array[i] > max_value:
      max_value = array[i]
  return max_value
```

The above function iterates through the entire array once, regardless of its size. Therefore, its time complexity is O(1).

- **Logarithmic time (O(log n))**: The running time of the algorithm grows logarithmically with the input size. This means that the running time doubles for every power of 2 increase in the input size.


```Python
def binary_search(array, target):
  low = 0
  high = len(array) - 1
  while low <= high:
    mid = (low + high) // 2
    if array[mid] == target:
      return mid
    elif array[mid] < target:
      low = mid + 1
    else:
      high = mid - 1
  return None
```

The binary search function iterates through the array by dividing it in half in each iteration. This results in a logarithmic time complexity of O(log n).

- **Linear time (O(n))**: The running time of the algorithm grows linearly with the input size. This means that the running time increases by a constant factor for each additional element in the input.


```python
def find_sum(array):
  sum = 0
  for i in range(len(array)):
    sum += array[i]
  return sum
```

The find_sum function iterates through the entire array and adds each element to the sum. Therefore, its time complexity is O(n).

- **Quadratic time (O(n^2))**: The running time of the algorithm grows quadratically with the input size. This means that the running time increases by the square of the number of elements in the input.

```python
def bubble_sort(array):
  for i in range(len(array)-1):
    for j in range(len(array)-1-i):
      if array[j] > array[j+1]:
        array[j], array[j+1] = array[j+1], array[j]
```

The bubble sort function performs nested loops that iterate through the entire array multiple times. This results in a quadratic time complexity of O(n^2).

##### **Other Common Notations:**

- **Polynomial time (O(n^k))**: The running time of the algorithm grows polynomially with the input size. This means that the running time increases by some power of n for each additional element in the input.
- **Exponential time (O(a^n))**: The running time of the algorithm grows exponentially with the input size. This means that the running time increases by a constant factor raised to the power of n for each additional element in the input. 
- Using the omega symbol is for showing the least number of steps a algorithm needs to take.



## Big O Notation Time Complexity Reference Table

|Algorithm|Time Complexity|Description|
|---|---|---|
|Constant time (O(1))|Independent of input size|Running time remains constant.|
|Logarithmic time (O(log n))|Increases logarithmically with input size|Running time doubles with every power of 2 increase in input size.|
|Linear time (O(n))|Increases linearly with input size|Running time increases by a constant factor for each additional element.|
|Quadratic time (O(n^2))|Increases quadratically with input size|Running time increases by the square of the number of elements.|
|Polynomial time (O(n^k))|Increases polynomially with input size|Running time increases by some power of n for each additional element.|
|Exponential time (O(a^n))|Increases exponentially with input size|Running time increases by a constant factor raised to the power of n for each additional element.|