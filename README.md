# Custom Data Structures in Java

This project is a custom implementation of common data structures in Java **without using the Java Collections Framework** (except for `Iterator`). The goal is to understand how these data structures work under the hood.

## 📦 Included Data Structures

### Physical Data Structures
These implement the shared interface `MyList<T>`:

- **MyArrayList<T>**  
  A resizable array-based list (similar to Java's `ArrayList`).
  ```
  MyList<Integer> arrList = new MyArrayList<>();
  arrList.add(10);
  arrList.add(20);
  arrList.add(1, 15);   // [10, 15, 20]
  arrList.remove(0);    // [15, 20]
  arrList.addLast(25);  // [15, 20, 25]
  arrList.sort();       // [15, 20, 25] (already sorted)
  System.out.println("MyArrayList contents:");
  for (Integer i : arrList) {
    System.out.println(i);
  }
  ```

- **MyLinkedList<T>**  
  A doubly linked list (similar to Java's `LinkedList`).
  ```
  MyList<String> linkedList = new MyLinkedList<>();
  linkedList.add("apple");
  linkedList.add("banana");
  linkedList.addFirst("zeroth");
  
  System.out.println("MyLinkedList contents:");
  for (String s : linkedList) {
    System.out.println(s);
  }
  ```

### Logical Data Structures
Built on top of physical data structures:

- **MyStack<T>**  
  LIFO (Last-In, First-Out) stack implemented using `MyArrayList`.
  ```
  MyStack<Integer> stack = new MyStack<>();
  stack.push(100);
  stack.push(200);
  System.out.println("Stack pop: " + stack.pop()); // 200
  ```

- **MyQueue<T>**  
  FIFO (First-In, First-Out) queue implemented using `MyLinkedList`.
  ```
  MyQueue<String> queue = new MyQueue<>();
  queue.enqueue("front");
  queue.enqueue("back");
  System.out.println("Queue dequeue: " + queue.dequeue()); // front
  ```

- **MyMinHeap<T extends Comparable<T>>**  
  Binary min-heap implemented using `MyArrayList`.
  ```
  MyMinHeap<Integer> minHeap = new MyMinHeap<>();
  minHeap.add(50);
  minHeap.add(20);
  minHeap.add(30);
  minHeap.add(10);
  System.out.println("MinHeap remove (should be 10): " + minHeap.remove());
  System.out.println("MinHeap remove (should be 20): " + minHeap.remove());
  ```

---

## 🚀 Getting Started

### Prerequisites
- JDK 8 or higher
- Any IDE (e.g. IntelliJ IDEA, Eclipse) or terminal with `javac`

### Running the Project
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/custom-data-structures.git
   cd custom-data-structures
