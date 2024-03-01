

## Introduction

Hash tables are used to store key-value pairs. They use a hash function to convert keys into indices of an array, allowing quick access to the values associated with those keys.

### Components of a Hash Table

1. **Array or Bucket**: A collection of slots or buckets where data elements are stored.
2. **Hash Function**: Maps keys to indices in the array.
3. **Collision Handling**: Strategies to manage collisions when two keys hash to the same index.

## Hash Functions

**Hash functions** are at the core of hash tables. They take an input (key) and produce a fixed-size string of characters, the hash value.

```python
# Example of a simple hash function in Python
def simple_hash(key, size):
    return len(key) % size
```

## Handling Collisions

### 1. Chaining

**Chaining** involves each bucket in the hash table storing a linked list of elements that hash to the same index.

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

### 2. Open Addressing

**Open addressing** involves finding alternative slots in the hash table when a collision occurs, using techniques like linear probing or quadratic probing.

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

## Applications of Hash Tables

1. **Databases**: Hashing allows rapid data retrieval in database systems.
2. **Cryptography**: Hash functions secure sensitive information.
3. **Caching**: Efficiently store and retrieve previously computed results.

Hash tables are versatile and widely used, providing an essential tool for optimizing data storage and retrieval operations in various computer science applications.