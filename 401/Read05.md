# Linked Lists

A Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.

There are two types of Linked List - Singly and Doubly. We will be implementing a Singly Linked List in this implementation.

## Linear data structures

If we really want to understand the basics of linked lists, it’s important that we talk about what type of data structure they are.

One characteristic of linked lists is that they are linear data structures, which means that there is a sequence and an order to how they are constructed and traversed.

## Terminology:

1. Linked List - A data structure that contains nodes that links/points to the next node in the list.
2. Singly - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.
3. Doubly - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.
4. Node - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.
5. Next - Each node contains a property called Next. This property contains the reference to the next node.
6. Head - The Head is a reference of type Node to the first node in a linked list.
7. Current - The Current is a reference of type Node to the node that is currently being looked at. When traversing, you create a new Current variable at the Head to guarantee you are starting from the beginning of the linked list.

![linked](https://miro.medium.com/max/875/1*Xokk6XOjWyIGCBujkJsCzQ.jpeg)

## Memory management

The biggest differentiator between arrays and linked lists is the way that they use memory in our machines. Those of us who work with dynamically typed languages like Ruby, JavaScript, or Python don’t have to think about how much memory an array uses when we write our code on a day to day basis because there are several layers of abstraction that end up with us not having to worry about memory allocation at all.

![memory](https://miro.medium.com/max/875/1*G43FVT5xJ1n1QDKVNZUxXQ.jpeg)

## Parts of a linked list

A linked list can be small or huge, but no matter the size, the parts that make it up are actually fairly simple. A linked list is made up of a series of nodes, which are the elements of the list.

![parts](https://miro.medium.com/max/875/1*K0_eV07tJtKQSVGKfP18bw.jpeg)

## Lists for all shapes and sizes

Even though the parts of a linked list don’t change, the way that we structure our linked lists can be quite different. Like most things in software, depending on the problem that we’re trying to solve, one type of linked lists might be a better tool for the job than another.

Singly linked lists are the simplest type of linked list, based solely on the fact that they only go in one direction. There is a single track that we can traverse the list in; we start at the head node, and traverse from the root until the last node, which will end at an empty null value.

![lists](https://miro.medium.com/max/875/1*AeMDLFUjR0w0J4n8CP4H6g.jpeg)

## Growing a linked list

We already know what linked lists are made of, and how their non-contiguous memory allocation makes them uniquely different from their seemingly more popular cousin, the array.

So how do they work, exactly? Well, just like with an array, we can add elements and remove elements from a linked list. But unlike arrays, we don’t need to allocate memory in advance or copy and re-create our linked list, since we won’t “run out of space” the way we might with a pre-allocated array.

For simplicity’s sake, we’ll work with a singly linked list in these examples. We’ll start with the simplest place we can insert an element into a linked list: at the very beginning. This is fairly easy to do, since we don’t need to go through our entire list; instead we just start at the beginning.

1. First, we find the head node of the linked list.
2. Next, we’ll make our new node, and set its pointer to the current first node of the list.
3. Lastly, we rearrange our head node’s pointer to point at our new node.

![growing-list](https://miro.medium.com/max/875/1*Jy5tjwrMdtpGl2ceq4f94A.jpeg)

## To list or not to list?

No human is perfect, and neither is a linked list. Here’s the thing: sometimes, a linked list can be really awesome — for example, when you want to insert or remove something at the beginning of the list. But, as we’ve learned, they can sometimes be…less than ideal (imagine having a million nodes and just wanting to delete the last one!)

Even if you don’t have to work with them every day, it’s useful to know just enough about data structures like linked lists so that you can both recognize them when you see them, and know when to reach for them when the time is right.

![to-list](https://miro.medium.com/max/875/1*cUehR5S18XSoVLaPNfNzlA.jpeg)