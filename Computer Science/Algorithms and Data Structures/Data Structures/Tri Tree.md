

## Introduction

Tri-trees, also known as Ternary Search Trees (TSTs), are specialized data structures that combine characteristics of tries, binary search trees, and hash tables. They excel in scenarios where efficient searching, insertion, and deletion of strings with low memory overhead are required.

## Structure

A Tri-tree node contains:

- **Key Character**: Represents a character in the string.
- **Value**: Data associated with the key (optional).
- **Three Child Pointers**: Pointers to nodes representing characters less than, equal to, and greater than the current key character.

### Node Structure (Pseudo-code)

```pseudo
class TriNode:
    character
    value
    left_node
    equal_node
    right_node
```

## Operations

### Insertion

- Start from the root node.
- For each character in the string:
  - If the node does not exist for the character, create one.
  - Traverse to the next node based on character comparison.
- At the end of the string, mark the last node as a leaf node and store associated data.

### Search

- Begin at the root.
- For each character in the search string:
  - Traverse to the next node based on character comparison.
- If the string is found completely, retrieve the associated data. If not, it's not present in the tree.

### Deletion

- Search for the node containing the string to delete.
- If found, mark the node as a non-leaf node or remove it.
- Adjust the tree structure if necessary.

## Use Cases

Tri-trees are advantageous in scenarios such as:

- **Dictionary Implementation**: Efficient storage and retrieval of words.
- **Auto-completion Systems**: Quickly suggest words based on partial input.
- **Spell Checkers**: Fast checking of word existence and correction.

## Advantages

- **Efficient Searching**: Suitable for prefix-based searches.
- **Low Memory Overhead**: Saves memory compared to traditional tries for certain applications.
- **Ordered Storage**: Maintains lexicographical order, facilitating range searches.

## Disadvantages

- **Complexity**: More intricate than basic data structures, requiring careful implementation.
- **Memory Usage**: In certain cases, may use more memory compared to hash tables for similar operations.

### Example Code (Python)

```python
class TriNode:
    def __init__(self):
        self.character = ''
        self.value = None
        self.left_node = None
        self.equal_node = None
        self.right_node = None

# Function to insert a string into a Tri-tree
def insert(root, key, value):
    if not root:
        root = TriNode()

    if not key:
        root.value = value
        return root

    char = key[0]

    if char < root.character:
        root.left_node = insert(root.left_node, key, value)
    elif char == root.character:
        root.equal_node = insert(root.equal_node, key[1:], value)
    else:
        root.right_node = insert(root.right_node, key, value)

    return root
```

![[Pasted image 20240106154510.png]]