# Java--CustomLinkedList

This repository contains a java package for a linked list, a linear data structure used to store the elements (nodes) in contiguous locations. The package contains classes and interfaces for singly and doubly linked lists. A linked list has pointers that are used to link the elements, and each element in the linked list consists of two parts, namely the data part and the address part. The data part is the value or object to be stored in an element, and the address part consists of a pointer to the next element in the list. In the case of a doubly linked list each element has an additional part, a pointer to link an element to the previous element in the list. Each element in the list is called a node.

## Syntax
The syntax to define an instance of this custom linked list is:

&emsp;*SLinkedList<data_type> list_name = new SlinkedList<>();   // for a single linked list*  
&emsp;*DLinkedList<data_type> list_name = new DlinkedList<>();   // for a double linked list*
   
The syntax to define an instance of Iterator for a list is as follows:

&emsp;*IIterator<data_type> iterator_name = list_name.iterator();   // for a single linked list*  
&emsp;*IIterator<data_type> iterator_name = list_name.iterator(IteratorDirection.direction);   // for a double linked list*
  
&emsp;A Doubly Linked list can be iterated either forwards or backwards. Direction needs to be specified when initiating the iterator:

   - IteratorDirection.FORWARD  
   - IteratorDirection.BACKWARDS

## Nodes

A linked list consists of nodes each of which stores a particular object item of the same data type that was defined when the list was initiated.
   
## Methods (Linked List)

|Method|Description|SLinkedList|DLinkedList|
|------|-----------|:---------:|:---------:|
|isEmpty()|Returns a boolean, true if list is empty, false if not.|Yes|Yes|
|size()|Return number of elements/nodes in list.|Yes|Yes|
|add(Object o)|Add node to end of list and assign object to it.|Yes|Yes|
|add(Object o, int index)|Add node to list at specified index. Assign object to it.|Yes|Yes|
|remove(int index)|Remove node from list at specified index|Yes|Yes|
|peek()|Returns the object stored in the first node of the list.|Yes|Yes|
|peekTail()|Returns the object stored in the last node of the list.|Yes|Yes|
|poll()|Returns the object stored in the first node of list and removes the node from list.|Yes|Yes|
|pollTail()|Returns the object stored in the last node of the list and removes the node from the list|No|Yes|
|indexOf(Object o)|Return the index of element/node that contains the specified object.|Yes|Yes|
|contains(Object o)|Returns true if list contains the specified object.|Yes|Yes|
|iterator()|Return a ListIterator object for a particular list. Used to iterate through that list|Yes|Yes|

## Methods (Iterator)

|Method|Description|SlinkedList|DLinkedList|
|------|-----------|:---------:|:---------:|
|hasNext()|Returns true if there is another node after the current node, or if we have not yet started to iterate through the list but at least one element/node exists.|Yes|Yes|
|hasPrev()|Returns true if there is another node before the current node, or if we have not yet started to iterate backwards through the list but at least one element/node exits.|No|Yes|
|next()|Iterate to the next or first element/node in the list. Must be called for each iteration.|Yes|Yes|
|prev()|Iterate to the previous or last element/node in the list. Must be called for each iteration.|No|Yes|
|get()|Returns the object stored in the current element/node.|Yes|Yes|
|remove()|Remove the current element/node from the list.|Yes|Yes|
|addBefore(Object o)|Add a new element/node to the list immediately before the current node. Will store the object argument in the new node.|Yes|Yes|
|addAfter(Object o)|Add a new element/node to the list immediately after the current node. Will store the object argument in the new node.|Yes|Yes|
|set(Object o)|Stores the argument object in the current element/node.|Yes|Yes|

## Examples

   Define a list and add elements to that list:  
   
      import com.cqueltech.linkedlist.SLinkedList;
      ...
      // Create a new list.
      SLinkedList<String> list = new SLinkedist<>();
      // Add elements to the list.
      list.add("Hello");
      list.add("World!");
      ...
   
   Define a list and add elements to the list that contain class objects:
   
      import com.cqueltech.linkedlist.SLinkedList;
      ...
      // Create a new list.
      SlinkedList<Dog> list = new SLinkedList<>();
      // Add elements to the list.
      list.add(new Dog("Poodle"));
      list.add(new Dog("Dalmation");
      ...

   Define a doubly linked list, add elements to that list and iterate through it:
   
      import com.cqueltech.linkedlist.DLinkedList;
      import com.cqueltech.linkedlist.IIterator;
      import com.cqueltech.linkedlist.IIterator.IteratorDirection;
      ...
      // Create a new list.
      DLinkedList<String> list = new DLinkedList<>();
      // Add elements to the list.
      list.add("Hello");
      list.add("World");
      list.add("Example!");
      // Define iterator to iterate forwards through the list.
      IIterator<String> iter1 = list.iterator(IteratorDirection.FORWARDS);
      // Iterate through the list.
      while (iter1.hasNext()) {
        // Get the next or first node in the list.
        iter1.next();
        // Current node processing logic goes here...
        System.out.println(iter1.get());
      }
      ...
   
      Output:
      -------
      Hello
      World
      Example!
      
   Iterate through a doubly linked list backwards:
   
      import com.cqueltech.linkedlist.DLinkedList;
      import com.cqueltech.linkedlist.IIterator;
      import com.cqueltech.linkedlist.IIterator.IteratorDirection;
      ...
      // Define iterator to iterate backwards through the list.
      IIterator<String> iter2 = list.iterator(IteratorDirection.BACKWARDS);
      // Iterate through the list.
      while (iter2.hasPrev()) {
        // Get the previous or last node in the list.
        iter2.prev();
        // Current node processing logic goes here...
        System.out.println(iter2.get());
      }
      ...
      
      Output:
      -------
      Example!
      World
      Hello
