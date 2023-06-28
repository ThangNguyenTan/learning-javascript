1. Reverse a string:

```javascript
function reverseString(str) {
  return str.split("").reverse().join("");
}

console.log(reverseString("Hello")); // Output: olleH
```

Explanation: The `reverseString` function takes a string as input and uses the `split`, `reverse`, and `join` methods to split the string into an array of characters, reverse the order of the array, and then join the characters back into a string.

2. Check if a string is a palindrome:

```javascript
function isPalindrome(str) {
  const reversed = str.split("").reverse().join("");
  return str === reversed;
}

console.log(isPalindrome("racecar")); // Output: true
```

Explanation: The `isPalindrome` function reverses the input string using the same technique as in the previous question, and then checks if the reversed string is equal to the original string.

3. Find the first non-repeated character in a string:

```javascript
function findFirstNonRepeatedChar(str) {
  const charMap = {};
  for (let char of str) {
    charMap[char] = charMap[char] + 1 || 1;
  }
  for (let char of str) {
    if (charMap[char] === 1) {
      return char;
    }
  }
  return null;
}

console.log(findFirstNonRepeatedChar("abacabad")); // Output: c
```

Explanation: The `findFirstNonRepeatedChar` function creates a character frequency map using an object. It iterates over the characters in the string, updating the count of each character in the map. Finally, it iterates over the characters again and returns the first character with a count of 1.

4. Remove duplicates from an array:

```javascript
function removeDuplicates(arr) {
  return [...new Set(arr)];
}

console.log(removeDuplicates([1, 2, 2, 3, 4, 4, 5])); // Output: [1, 2, 3, 4, 5]
```

Explanation: The `removeDuplicates` function uses a combination of the `Set` object and the spread operator to create a new array with unique values. The `Set` object automatically removes duplicate values when creating the set, and the spread operator converts the set back to an array.

5. Find the intersection of two arrays:

```javascript
function findIntersection(arr1, arr2) {
  return arr1.filter((value) => arr2.includes(value));
}

console.log(findIntersection([1, 2, 3, 4], [3, 4, 5, 6])); // Output: [3, 4]
```

Explanation: The `findIntersection` function uses the `filter` method to iterate over the elements of the first array and keeps only those elements that are also present in the second array using the `includes` method.

6. Implement a stack using an array:

```javascript
class Stack {
  constructor() {
    this.items = [];
  }

  push(item) {
    this.items.push(item);
  }

  pop() {
    if (this.isEmpty()) {
      return null;
    }
    return this.items.pop();
  }

  peek() {
    if (this.isEmpty()) {
      return null;
    }
    return this.items[this.items.length - 1];
  }

  isEmpty() {
    return this.items.length === 0;
  }

  size() {
    return this.items.length;
  }
}

const stack = new Stack();
stack.push(1);
stack.push(2);
console.log(stack.pop()); // Output: 2

console.log(stack.peek()); // Output: 1
console.log(stack.isEmpty()); // Output: false
console.log(stack.size()); // Output: 1
```

Explanation: The `Stack` class represents a stack data structure using an array `items`. The `push` method adds an item to the top of the stack by appending it to the end of the array. The `pop` method removes and returns the top item from the stack. The `peek` method returns the top item without removing it. The `isEmpty` method checks if the stack is empty by examining the length of the array. The `size` method returns the number of items in the stack.

7. Implement a queue using an array:

```javascript
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(item) {
    this.items.push(item);
  }

  dequeue() {
    if (this.isEmpty()) {
      return null;
    }
    return this.items.shift();
  }

  peek() {
    if (this.isEmpty()) {
      return null;
    }
    return this.items[0];
  }

  isEmpty() {
    return this.items.length === 0;
  }

  size() {
    return this.items.length;
  }
}

const queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
console.log(queue.dequeue()); // Output: 1
console.log(queue.peek()); // Output: 2
console.log(queue.isEmpty()); // Output: false
console.log(queue.size()); // Output: 1
```

Explanation: The `Queue` class represents a queue data structure using an array `items`. The `enqueue` method adds an item to the end of the queue by appending it to the end of the array. The `dequeue` method removes and returns the front item from the queue by shifting the first item from the array. The `peek` method returns the front item without removing it. The `isEmpty` method checks if the queue is empty by examining the length of the array. The `size` method returns the number of items in the queue.

8. Implement a linked list:

```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
  }

  append(data) {
    const newNode = new Node(data);
    if (!this.head) {
      this.head = newNode;
    } else {
      let current = this.head;
      while (current.next) {
        current = current.next;
      }
      current.next = newNode;
    }
  }

  prepend(data) {
    const newNode = new Node(data);
    newNode.next = this.head;
    this.head = newNode;
  }

  delete(data) {
    if (!this.head) {
      return;
    }
    if (this.head.data === data) {
      this.head = this.head.next;
      return;
    }
    let current = this.head;
    while (current.next) {
      if (current.next.data === data) {
        current.next = current.next.next;
        return;
      }
      current = current.next;
    }
  }

  search(data) {
    let current = this.head;
    while (current) {
      if (current.data === data) {
        return current;
      }
      current = current.next;
    }
    return null;
  }
}

const linkedList = new LinkedList();
linkedList.append(1);
linkedList.append(2);
linkedList.prepend(0);
linkedList.delete(1);
console.log(linkedList.search(2)); // Output: Node { data: 2, next: null }
```

Explanation: The `Node` class represents a node in a

linked list, with a `data` property and a `next` pointer to the next node. The `LinkedList` class has a `head` property that points to the first node in the list. The `append` method adds a new node with the given data at the end of the list. If the list is empty, the new node becomes the head. Otherwise, it traverses the list to find the last node and appends the new node there. The `prepend` method adds a new node with the given data at the beginning of the list. It updates the `next` pointer of the new node to point to the current head, and the new node becomes the new head. The `delete` method removes a node with the given data from the list. It handles cases where the node to be deleted is the head or located in the middle of the list. The `search` method traverses the list to find a node with the given data and returns the node if found, or `null` otherwise.

9. Find the middle element of a linked list:

```javascript
function findMiddleElement(linkedList) {
  let slow = linkedList.head;
  let fast = linkedList.head;
  while (fast && fast.next) {
    slow = slow.next;
    fast = fast.next.next;
  }
  return slow.data;
}

console.log(findMiddleElement(linkedList)); // Output: 2
```

Explanation: The `findMiddleElement` function uses the slow and fast pointer technique to find the middle element of a linked list. The `slow` pointer moves one node at a time, while the `fast` pointer moves two nodes at a time. When the `fast` pointer reaches the end of the list, the `slow` pointer will be at the middle element.

10. Reverse a linked list:

```javascript
function reverseLinkedList(linkedList) {
  let prev = null;
  let current = linkedList.head;
  while (current) {
    let next = current.next;
    current.next = prev;
    prev = current;
    current = next;
  }
  linkedList.head = prev;
}

reverseLinkedList(linkedList);
console.log(linkedList); // Output: LinkedList { head: Node { data: 2, next: Node { data: 0, next: null } } }
```

Explanation: The `reverseLinkedList` function reverses the linked list by iterating through the list and updating the `next` pointers of each node to reverse their direction. It uses three pointers: `prev` to keep track of the previous node, `current` to keep track of the current node, and `next` to temporarily store the next node before updating the `next` pointer of the current node.

11. Implement a binary search tree:

```javascript
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinarySearchTree {
  constructor() {
    this.root = null;
  }

  insert(value) {
    const newNode = new TreeNode(value);
    if (!this.root) {
      this.root = newNode;
    } else {
      this.insertNode(this.root, newNode);
    }
  }

  insertNode(node, newNode) {
    if (newNode.value < node.value) {
      if (!node.left) {
        node.left = newNode;
      } else {
        this.insertNode(node.left, newNode);
      }
    } else {
      if (!node.right) {
        node.right = newNode;
      } else {
        this.insertNode(node.right, newNode);
      }
    }
  }

  search(value) {
    return this.searchNode(this.root, value);
  }

  searchNode(node, value) {
    if (!node || node.value === value) {
      return node;
    }
    if (value < node.value) {
      return this.searchNode(node.left, value);
    }
    return this.searchNode(node.right, value);
  }
}

const bst = new BinarySearchTree();
bst.insert(4);
bst.insert(2);
bst.insert(6);
console.log(bst.search(2)); // Output: TreeNode { value: 2, left: null, right: null }
```

Explanation: The `TreeNode` class represents a node in a binary search tree, with a `value` property and `left` and `right` pointers to the left and right child nodes. The `BinarySearchTree` class has a `root` property that points to the root node of the tree. The `insert` method inserts a new node with the given value into the tree. If the tree is empty, the new node becomes the root. Otherwise, it calls the `insertNode` method to recursively find the correct position for the new node based on its value. The `search` method searches for a node with the given value in the tree and returns the node if found, or `null` otherwise. It calls the `searchNode` method to recursively search for the value starting from the root node.

12. Traverse a binary tree in preorder, inorder, and postorder:

```javascript
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

function preorderTraversal(root) {
  if (!root) {
    return [];
  }
  const result = [];
  function traverse(node) {
    if (!node) {
      return;
    }
    result.push(node.value);
    traverse(node.left);
    traverse(node.right);
  }
  traverse(root);
  return result;
}

function inorderTraversal(root) {
  if (!root) {
    return [];
  }
  const result = [];
  function traverse(node) {
    if (!node) {
      return;
    }
    traverse(node.left);
    result.push(node.value);
    traverse(node.right);
  }
  traverse(root);
  return result;
}

function postorderTraversal(root) {
  if (!root) {
    return [];
  }
  const result = [];
  function traverse(node) {
    if (!node) {
      return;
    }
    traverse(node.left);
    traverse(node.right);
    result.push(node.value);
  }
  traverse(root);
  return result;
}

const root = new TreeNode(1);
root.left = new TreeNode(2);
root.right = new TreeNode(3);
root.left.left = new TreeNode(4);
root.left.right = new TreeNode(5);

console.log(preorderTraversal(root)); // Output: [1, 2, 4, 5, 3]
console.log(inorderTraversal(root)); // Output: [4, 2, 5, 1, 3]
console.log(postorderTraversal(root)); // Output: [4, 5, 2, 3, 1]
```

Explanation: The `TreeNode` class represents a node in a binary tree, with a `value` property and `left` and `right` pointers to the left and right child nodes. The `preorderTraversal` function performs a preorder traversal of the tree, visiting the root node first, then the left subtree, and finally the right subtree. The `inorderTraversal` function performs an inorder traversal, visiting the left subtree first, then the root node, and finally the right subtree. The `postorderTraversal` function performs a postorder traversal, visiting the left subtree first, then the right subtree, and finally the root node. All three traversal functions use recursive depth-first

search (DFS) to traverse the tree.

13. Check if a binary tree is a binary search tree:

```javascript
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

function isBinarySearchTree(root) {
  function isValidBST(node, min, max) {
    if (!node) {
      return true;
    }
    if (node.value <= min || node.value >= max) {
      return false;
    }
    return (
      isValidBST(node.left, min, node.value) &&
      isValidBST(node.right, node.value, max)
    );
  }
  return isValidBST(root, -Infinity, Infinity);
}

const bst = new TreeNode(4);
bst.left = new TreeNode(2);
bst.right = new TreeNode(6);
bst.left.left = new TreeNode(1);
bst.left.right = new TreeNode(3);

console.log(isBinarySearchTree(bst)); // Output: true
```

Explanation: The `TreeNode` class represents a node in a binary tree, with a `value` property and `left` and `right` pointers to the left and right child nodes. The `isBinarySearchTree` function checks if the given tree is a binary search tree by recursively validating the values of each node. It uses the `isValidBST` function, which takes a node, a minimum value, and a maximum value. It checks if the current node's value is within the valid range defined by the minimum and maximum values. If the current node's value violates the BST property, it returns `false`. Otherwise, it recursively checks the left and right subtrees, updating the minimum and maximum values accordingly. The function returns `true` if all nodes pass the BST property test.

14. Find the height of a binary tree:

```javascript
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

function getHeight(root) {
  if (!root) {
    return 0;
  }
  const leftHeight = getHeight(root.left);
  const rightHeight = getHeight(root.right);
  return Math.max(leftHeight, rightHeight) + 1;
}

const root = new TreeNode(1);
root.left = new TreeNode(2);
root.right = new TreeNode(3);
root.left.left = new TreeNode(4);
root.left.right = new TreeNode(5);

console.log(getHeight(root)); // Output: 3
```

Explanation: The `TreeNode` class represents a node in a binary tree, with a `value` property and `left` and `right` pointers to the left and right child nodes. The `getHeight` function calculates the height of the binary tree recursively. The height of a tree is defined as the number of edges in the longest path from the root to a leaf node. The function uses a recursive approach by calculating the heights of the left and right subtrees and returning the maximum height plus 1.

15. Implement a hash table:

```javascript
class HashTable {
  constructor(size = 10) {
    this.size = size;
    this.table = new Array(size);
  }

  hash(key) {
    let hashValue = 0;
    for (let i = 0; i < key.length; i++) {
      hashValue += key.charCodeAt(i);
    }
    return hashValue % this.size;
  }

  set(key, value) {
    const index = this.hash(key);
    if (!this.table[index]) {
      this.table[index] = [];
    }
    for (let i = 0; i < this.table[index].length; i++) {
      if (this.table[index][i][0] === key) {
        this.table[index][i][1] = value;
        return;
      }
    }
    this.table[index].push([key, value]);
  }

  get(key) {
    const index = this.hash(key);
    if (!this.table[index]) {
      return undefined;
    }
    for (let i = 0; i < this.table[index].length; i++) {
      if (this.table[index][i][0] === key) {
        return this.table[index][i][1];
      }
    }
    return undefined;
  }

  delete(key) {
    const index = this.hash(key);
    if (!this.table[index]) {
      return;
    }
    for (let i = 0; i < this.table[index].length; i++) {
      if (this.table[index][i][0] === key) {
        this.table[index].splice(i, 1);
        return;
      }
    }
  }
}

const hashTable = new HashTable();
hashTable.set("name", "John");
hashTable.set("age", 30);
console.log(hashTable.get("name")); // Output: John
hashTable.delete("age");
console.log(hashTable.get("age")); // Output: undefined
```

Explanation: The `HashTable` class implements a basic hash table with fixed size using an array. The hash table uses a hash function to map keys to indices within the array. The `hash` method calculates the hash value for a given key by summing the ASCII values of its characters and taking the modulo of the table size. The `set` method stores a key-value pair in the hash table. If a collision occurs (multiple keys hash to the same index), the key-value pairs are stored in separate buckets within the same index. The `get` method retrieves the value associated with a given key from the hash table. It uses the hash function to find the corresponding index and searches the bucket for the key-value pair. The `delete` method removes a key-value pair from the hash table by finding the index and the matching key in the bucket and removing the pair from the array.

16. Find the most common element in an array:

```javascript
function findMostCommonElement(arr) {
  const countMap = new Map();
  let maxCount = 0;
  let mostCommonElement = null;
  for (const element of arr) {
    const count = countMap.get(element) || 0;
    countMap.set(element, count + 1);
    if (count + 1 > maxCount) {
      maxCount = count + 1;
      mostCommonElement = element;
    }
  }
  return mostCommonElement;
}

const array = [1, 2, 3, 2, 1, 2, 3, 3, 3];
console.log(findMostCommonElement(array)); // Output: 3
```

Explanation: The `findMostCommonElement` function finds the most common element in an array by using a `Map` to keep track of the count of each element. It iterates over the array and updates the count for each element in the map. It also keeps track of the current maximum count and the corresponding most common element. By the end of the iteration, the function returns the most common element.

17. Implement a graph and perform a depth-first search (DFS) and breadth-first search (BFS):

```javascript
class Graph {
  constructor() {
    this.vertices = [];
    this.adjacencyList = new Map();
  }

  addVertex(vertex) {
    this.vertices.push(vertex);
    this.adjacencyList.set(vertex, []);
  }

  addEdge(vertex1, vertex2) {
    this.adjacencyList.get(vertex1).push(vertex2);
    this.adjacencyList.get(vertex2).push(vertex1);
  }

  dfs(startVertex) {
    const visited = new Set();
    this.dfsHelper(startVertex, visited);
  }

  dfsHelper(vertex, visited) {
    visited.add(vertex);
    console.log(vertex);
    const neighbors = this.adjacencyList.get(vertex);
    for (const neighbor of neighbors) {
      if (!visited.has(neighbor)) {
        this.dfsHelper(neighbor, visited);
      }
    }
  }

  bfs(startVertex) {
    const visited = new Set();
    const queue = [startVertex];
    visited.add(startVertex);
    while (queue.length > 0) {
      const vertex = queue.shift();
      console.log(vertex);
      const neighbors = this.adjacencyList.get(vertex);
      for (const neighbor of neighbors) {
        if (!visited.has(neighbor)) {
          visited.add(neighbor);
          queue.push(neighbor);
        }
      }
    }
  }
}

const graph = new Graph();
graph.addVertex("A");
graph.addVertex("B");
graph.addVertex("C");
graph.addVertex("D");
graph.addVertex("E");
graph.addEdge("A", "B");
graph.addEdge("A", "C");
graph.addEdge("B", "D");
graph.addEdge("C", "E");
graph.dfs("A"); // Output: A B D C E
graph.bfs("A"); // Output: A B C D E
```

Explanation: The `Graph` class represents an undirected graph using an adjacency list. The graph consists of vertices and edges. The `addVertex` method adds a vertex to the graph by adding it to the `vertices` array and creating an empty array in the `adjacencyList` map to store its neighbors. The `addEdge` method adds an edge between two vertices by updating their corresponding adjacency lists. The `dfs` method performs a depth-first search starting from a given vertex. It uses a helper function, `dfsHelper`, to recursively traverse the graph, marking visited vertices using a `Set` and outputting the vertex value. The `bfs` method performs a breadth-first search starting from a given vertex. It uses a queue to store the vertices to be visited, and a `Set` to track visited vertices. It iteratively visits vertices, enqueues their neighbors, and marks them as visited. Both search methods output the visited vertices in the order they were visited.

18. Find the shortest path in a graph using Dijkstra's algorithm:

```javascript
class Graph {
  constructor() {
    this.vertices = [];
    this.adjacencyList = new Map();
  }

  addVertex(vertex) {
    this.vertices.push(vertex);
    this.adjacencyList.set(vertex, []);
  }

  addEdge(vertex1, vertex2, weight) {
    this.adjacencyList.get(vertex1).push({ node: vertex2, weight });
    this.adjacencyList.get(vertex2).push({ node: vertex1, weight });
  }

  dijkstra(startVertex) {
    const distances = new Map();
    const previous = new Map();
    const visited = new Set();
    const queue = new PriorityQueue();

    for (const vertex of this.vertices) {
      if (vertex === startVertex) {
        distances.set(vertex, 0);
        queue.enqueue(vertex, 0);
      } else {
        distances.set(vertex, Infinity);
        queue.enqueue(vertex, Infinity);
      }
      previous.set(vertex, null);
    }

    while (!queue.isEmpty()) {
      const currentVertex = queue.dequeue().value;
      visited.add(currentVertex);
      const neighbors = this.adjacencyList.get(currentVertex);
      for (const neighbor of neighbors) {
        if (!visited.has(neighbor.node)) {
          const currentDistance = distances.get(currentVertex);
          const newDistance = currentDistance + neighbor.weight;
          if (newDistance < distances.get(neighbor.node)) {
            distances.set(neighbor.node, newDistance);
            previous.set(neighbor.node, currentVertex);
            queue.enqueue(neighbor.node, newDistance);
          }
        }
      }
    }

    return { distances, previous };
  }

  getPath(previous, endVertex) {
    const path = [];
    let currentVertex = endVertex;
    while (currentVertex !== null) {
      path.unshift(currentVertex);
      currentVertex = previous.get(currentVertex);
    }
    return path;
  }
}

class PriorityQueue {
  constructor() {
    this.values = [];
  }

  enqueue(value, priority) {
    this.values.push({ value, priority });
    this.sort();
  }

  dequeue() {
    return this.values.shift();
  }

  sort() {
    this.values.sort((a, b) => a.priority - b.priority);
  }

  isEmpty() {
    return this.values.length === 0;
  }
}

const graph = new Graph();
graph.addVertex("A");
graph.addVertex("B");
graph.addVertex("C");
graph.addVertex("D");
graph.addVertex("E");
graph.addEdge("A", "B", 4);
graph.addEdge("A", "C", 2);
graph.addEdge("B", "E", 3);
graph.addEdge("C", "D", 2);
graph.addEdge("C", "E", 1);
graph.addEdge("D", "E", 3);

const { distances, previous } = graph.dijkstra("A");
console.log(distances); // Output: Map { 'A' => 0, 'B' => 4, 'C' => 2, 'D' => 4, 'E' => 3 }
console.log(graph.getPath(previous, "E")); // Output: [ 'A', 'C', 'E' ]
```

Explanation: The `Graph` class represents a weighted graph using an adjacency list. It has methods to add vertices, add edges between vertices with weights, and perform Dijkstra's algorithm to find the shortest path from a starting vertex to all other vertices. The `dijkstra` method initializes the data structures for the algorithm, including a `distances` map to store the minimum distances from the start vertex, a `previous` map to track the previous vertex in the shortest path, a `visited` set to track visited vertices, and a `PriorityQueue` to store the vertices with their respective distances. The algorithm iteratively selects the vertex with the minimum distance from the queue, updates the distances to its neighbors if a shorter path is found, and enqueues the updated vertices in the queue. The method returns the `distances` and `previous` maps.

The `getPath` method uses the `previous` map to reconstruct the shortest path from the start vertex to a given end vertex. It starts from the end vertex and iteratively follows the previous vertices until reaching the start vertex, building the path in reverse order. The method returns the shortest path as an array of vertices.

19. Implement a priority queue:

```javascript
class PriorityQueue {
  constructor() {
    this.values = [];
  }

  enqueue(value, priority) {
    this.values.push({ value, priority });
    this.sort();
  }

  dequeue() {
    return this.values.shift().value;
  }

  sort() {
    this.values.sort((a, b) => a.priority - b.priority);
  }

  isEmpty() {
    return this.values.length === 0;
  }
}

const queue = new PriorityQueue();
queue.enqueue("Task 1", 3);
queue.enqueue("Task 2", 1);
queue.enqueue("Task 3", 2);
console.log(queue.dequeue()); // Output: Task 2
console.log(queue.dequeue()); // Output: Task 3
console.log(queue.isEmpty()); // Output: false
console.log(queue.dequeue()); // Output: Task 1
console.log(queue.isEmpty()); // Output: true
```

Explanation: The `PriorityQueue` class implements a priority queue using an array. Each element in the queue is an object with a `value` and `priority`. The `enqueue` method adds an element to the queue while maintaining the priority order by sorting the array. The `dequeue` method removes and returns the element with the highest priority (lowest value of `priority`) from the front of the queue. The `sort` method uses the `Array.prototype.sort` function with a custom comparison function to sort the elements based on their priorities. The `isEmpty` method checks if the queue is empty by checking the length of the array. The example demonstrates the usage of the priority queue by enqueueing tasks with different priorities and dequeueing them in the correct order.

20. Sort an array using a sorting algorithm such as bubble sort, insertion sort, or quicksort:
    Here's an example of using the bubble sort algorithm to sort an array in JavaScript:

```javascript
function bubbleSort(arr) {
  const len = arr.length;
  for (let i = 0; i < len - 1; i++) {
    for (let j = 0; j < len - 1 - i; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
      }
    }
  }
  return arr;
}

const array = [5, 3, 8, 4, 2];
console.log(bubbleSort(array)); // Output: [2, 3, 4, 5, 8]
```

Explanation: The `bubbleSort` function implements the bubble sort algorithm to sort an array in ascending order. The algorithm iterates over the array multiple times, comparing adjacent elements and swapping them if they are in the wrong order. In each iteration, the largest element "bubbles" up to its correct position at the end of the array. The process is repeated until the entire array is sorted. The function takes an array as input and returns the sorted array. The example demonstrates the usage of the `bubbleSort` function to sort an array of numbers.
