
## Introduction to Hashing

Hashing is a fundamental concept used in data structures and algorithms, providing an efficient way to store and retrieve data. It involves mapping data of arbitrary size to fixed-size values, known as hash codes or hashes, through a hash function. This process allows for rapid data retrieval by reducing search times from linear to nearly constant time complexity. The number of steps only depends on the look up not the actual data set size.

### Hash Function

A **hash function** takes an input (or key) and produces a fixed-size string of characters, typically a hash code or hash value. It should satisfy the following properties:

- **Deterministic**: For a given input, the hash function always generates the same hash value.
- **Efficient**: It should compute the hash value quickly.
- **Uniform Distribution**: Hash values should be evenly distributed across the hash table to minimize collisions.

```python
# Example of a simple hash function in Python
def simple_hash(key, size):
    return len(key) % size
```

## Hash Tables

**Hash tables** are the primary data structure that employs hashing. They utilize an array-like structure where data elements are stored in association with their hash codes.

### Components of a Hash Table

1. **Array or Bucket**: A collection of slots or buckets where data elements are stored.
2. **Hash Function**: Maps keys to indices in the array.
3. **Collision Handling**: Mechanisms to manage situations when two keys hash to the same index.

### Handling Collisions

#### 1. **Chaining**

- **Chaining** involves each bucket in the hash table storing a linked list of elements that hash to the same index.

```python
# Example: Chaining implementation in Python
class HashTable:
    def __init__(self, size):
        self.size = size
        self.table = [[] for _ in range(size)]

    def hash(self, key):
        return len(key) % self.size

    def insert(self, key, value):
        index = self.hash(key)
        self.table[index].append((key, value))

    def search(self, key):
        index = self.hash(key)
        for k, v in self.table[index]:
            if k == key:
                return v
        return None
```

#### 2. **Open Addressing**

- **Open addressing** involves finding alternative slots in the hash table when a collision occurs, using techniques like linear probing or quadratic probing.

```python
# Example: Open Addressing (Linear Probing) implementation in Python
class HashTable:
    def __init__(self, size):
        self.size = size
        self.table = [None] * size

    def hash(self, key):
        return len(key) % self.size

    def insert(self, key, value):
        index = self.hash(key)
        while self.table[index] is not None:
            index = (index + 1) % self.size
        self.table[index] = (key, value)

    def search(self, key):
        index = self.hash(key)
        while self.table[index] is not None:
            k, v = self.table[index]
            if k == key:
                return v
            index = (index + 1) % self.size
        return None
```

## Applications of Hashing

1. **Databases**: Hashing enables rapid data retrieval in database systems.
2. **Cryptography**: Hash functions are used to secure sensitive information.
3. **Caching**: Efficiently store and retrieve previously computed results.

Hashing plays a crucial role in various fields, providing an essential tool for optimizing data storage and retrieval operations in computer science.