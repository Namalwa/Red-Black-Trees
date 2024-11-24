# Red-Black Trees
## Red-Black Tree Implementation

### Properties of Red-Black Trees

A **Red-Black Tree** is a type of balanced binary search tree that use a set of rules to maintain balance, ensuring logarithmic time complexity for operations like insertion, deletion, and searching, regardless of the initial shape of the tree. Red Black Trees are self-balancing, using a simple color-coding scheme to adjust the tree after each modification.

The key properties of a Red-Black Tree include:

- **Node Color**: Each node is either red or black.
- **Root Property**: The root node is always black.
- **Leaf Property**: All leaves (NIL nodes) are black.
- **Red Node Property**: Red nodes cannot have red children (no two consecutive red nodes).
- **Black Height Property**: Every path from a node to its descendant NIL nodes must contain the same number of black nodes.

This project provides a Red-Black Tree implementation with basic operations such as insertion, deletion, and searching.

**Red-Black Tree Example**

![red-black tree example](</assets/redtree.png>)

The right is the Correct Red-Black Tree in above image which ensures that every path from the root to a leaf node has the same number of black nodes. In this case,​ there is one (excluding the root node).

The left is the Incorrect Red Black Tree which does not follow the red-black properties as two red nodes are adjacent to each other. Another problem is that one of the paths to a leaf node has zero black nodes, whereas the other two contain a black node.

## Features

### 1. Efficient Insertion

In a Red-Black Tree, inserting a new element is done in a manner similar to a standard Binary Search Tree (BST), but with additional balancing steps to maintain the Red-Black Tree properties.

- **Standard BST Insertion**: The element is inserted like in a regular binary search tree, by finding the appropriate leaf node where the new element should go.
  
- **Balancing the Tree**: After insertion, the tree may violate one or more of the Red-Black Tree properties. To restore balance, we use specific tree rotations and color changes. The balancing process involves:
  - **Recoloring**: Changing the colors of nodes to maintain the Red-Black properties.
  - **Rotations**: Performing left or right rotations to balance the tree and ensure that it remains balanced after the insertion.

This balancing process ensures that the tree maintains a **logarithmic height**, resulting in **O(log n)** time complexity for insertions.

### 2. Deletion and Rebalancing

Deleting a node from a Red-Black Tree is more complex than insertion due to the need to maintain the Red-Black properties while removing the node.

- **Find the Node**: First, we locate the node to be deleted, similar to regular BST deletion.
  
- **Handle Node Removal**: After deleting the node, we must ensure that the tree remains balanced. If the deleted node was black, it can affect the "black height" property of the tree, causing imbalance. 

- **Rebalancing**: To rebalance the tree, we perform a series of **color changes** and **rotations**:
  - **Color Fixing**: Changing the colors of nearby nodes to ensure that no Red-Black properties are violated.
  - **Rotations**: Left or right rotations are used to shift nodes in such a way that the tree retains its balance.

The key challenge during deletion is ensuring that the tree’s properties are maintained while removing a node and rebalancing. This operation also takes **O(log n)** time complexity due to the logarithmic height of the tree.

### 3. Search Operation

Searching for an element in a Red-Black Tree is quite efficient due to its balanced nature. Since the tree is balanced according to the Red-Black properties, the search time is logarithmic, i.e., **O(log n)**.

- **Standard Binary Search**: Searching in a Red-Black Tree is done by starting at the root and following left or right children based on the value being searched for.
  
- **Logarithmic Search**: Due to the Red-Black properties, the tree’s height is guaranteed to remain balanced, with a height of at most **2 * log(n)**. As a result, the search operation always takes **O(log n)** time.

### 4. In-order Traversal

In-order traversal of a Red-Black Tree returns the elements in sorted order. Since the tree is a binary search tree, an in-order traversal guarantees that the nodes are visited from smallest to largest.

- **Traversal Process**: In-order traversal works by recursively visiting the left child, the current node, and then the right child. This traversal ensures that all nodes are visited in ascending order of their values.
  
- **Use Case**: In-order traversal is useful when you need to process or print the elements in sorted order, making it an essential feature for tasks like displaying data in a sorted list.

This operation has a time complexity of **O(n)** because it needs to visit all nodes in the tree, but since the tree is balanced, the tree size does not affect the efficiency of traversal as much as in unbalanced trees.

### 5. Automatic Balancing

The primary advantage of a Red-Black Tree is its ability to **automatically balance itself** during insertion and deletion operations. This self-balancing feature is what differentiates Red-Black Trees from regular binary search trees, which can become unbalanced and degrade performance.

- **Why Balancing is Needed**: In an unbalanced BST, the height of the tree could become linear (i.e., O(n)), leading to inefficient operations (like searching and inserting). Red-Black Trees ensure that the height remains balanced, maintaining **O(log n)** performance for operations like searching, insertion, and deletion.

- **How Balancing Happens**: After each insertion or deletion, the tree performs necessary **color changes** and **rotations** to restore its balance. These operations do not require rebalancing the entire tree, only the affected portions, ensuring efficiency.

This automatic balancing guarantees that the Red-Black Tree maintains optimal performance without requiring external intervention. After an insertion or deletion, you don’t need to manually intervene to ensure the tree remains balanced.

### 6. Logarithmic Time Complexity

The most significant feature of the Red-Black Tree is its **logarithmic time complexity** for key operations like insertion, deletion, and searching.

- **Insertions and Deletions**: Both of these operations involve finding a place for the new element and performing necessary rotations and recoloring to maintain the Red-Black properties. Since the height of the tree is limited to **2 * log(n)**, these operations take **O(log n)** time.

- **Search**: Searching for an element also takes **O(log n)** because the tree remains balanced, and the maximum path length from root to leaf is logarithmic.

The logarithmic time complexity makes Red-Black Trees ideal for applications where large sets of ordered data need to be maintained with fast insertions, deletions, and lookups.

## How to Use

### Installation

To use this implementation, simply clone the repository and include the Red-Black Tree implementation in your project.

```bash
git clone https://github.com/your-username/red-black-tree.git
```

### Advantages of Red-Black Trees:

**Balanced:** Red-Black Trees are self-balancing, meaning they automatically maintain a balance between the heights of the left and right subtrees. This ensures that search, insertion, and deletion operations take O(log n) time in the worst case.

**Efficient search, insertion, and deletion:** Due to their balanced structure, Red-Black Trees offer efficient operations. Search, insertion, and deletion all take O(log n) time in the worst case.

**Simple to implement:** The rules for maintaining the Red-Black Tree properties are relatively simple and straightforward to implement.

**Widely used:** Red-Black Trees are a popular choice for implementing various data structures, such as maps, sets, and priority queues.

### Disadvantages of Red-Black Trees:

**More complex than other balanced trees:** Compared to simpler balanced trees like AVL trees, Red-Black Trees have more complex insertion and deletion rules.

**Constant overhead:** Maintaining the Red-Black Tree properties adds a small overhead to every insertion and deletion operation.

**Not optimal for all use cases:** While efficient for most operations, Red-Black Trees might not be the best choice for applications where frequent insertions and deletions are required, as the constant overhead can become significant.

### Applications of Red-Black Trees:

**1.Implementing maps and sets:** Red-Black Trees are often used to implement maps and sets, where efficient search, insertion, and deletion are crucial.

**2.Priority queues:** Red-Black Trees can be used to implement priority queues, where elements are ordered based on their priority.

**3.File systems:** Red-Black Trees are used in some file systems to manage file and directory structures.

**4.In-memory databases:** Red-Black Trees are sometimes used in in-memory databases to store and retrieve data efficiently.

**4.Graphics and game development:** Red-Black Trees can be used in graphics and game development for tasks like collision detection and pathfinding.