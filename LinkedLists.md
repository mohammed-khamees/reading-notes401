# Linked Lists

**What is a linked list?**

A linked list is an ordered collection of data elements. A data element can be represented as a node in a linked list. Each node consists of two parts:

- data
- pointer to the next node.

Unlike arrays, data elements are not stored at contiguous locations. The data elements or nodes are linked using pointers, hence called a linked list.

### A linked list has the following properties:

1. Successive nodes are connected by pointers.
2. The last node points to null.
3. A head pointer is maintained which points to the first node of the list.
4. A linked list can grow and shrink in size during execution of the program.
5. It can be made just as long as required.
6. It allocates memory as the list grows. Unlike arrays, which have a fixed size. Therefore, the upper limit on the number of elements must be known in advance. Generally, the allocated memory is equal to the upper limit irrespective of the usage. This is one the key advantages of using a linked list over an array.

**Types of Linked lists**

- Singly linked list
- doubly linked list
- circular linked list

  A singly linked list is collection of nodes wherein each node has 2 parts: data and a pointer to the next node. The list terminates with a node pointing at null.

  ![Singly](https://miro.medium.com/max/700/1*Ftrp2Eg3-AuDpWa5Pe1fUQ.png)

  ```
  class LinkedListNode {
    constructor(data) {
        this.data = data;
        this.next = null;
    }
  }

  ```

  ```
  // create the first node
  const head = new LinkedListNode(12);
  // add a second node
  head.next = new LinkedListNode(99);
  // add a third node
  head.next.next = new LinkedListNode(37);

  ```

**Other resources**

[link](https://humanwhocodes.com/blog/2019/01/computer-science-in-javascript-linked-list/) //
[link](https://medium.com/swlh/singly-linked-list-in-javascript-a0e58d045561)
