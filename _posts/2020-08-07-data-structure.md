# Data Structure

## Linked List

연결 리스트는 데이터 요소의 선형 콜렉션으로, 각 요소는 다음을 가리킨다.

## Double Linked List

이중 연결 리스트는 데이터 요소의 선형 콜렉션으로, 각 요소는 이전과 다음을 가리킨다.

## Queue

First-In-First-Out (FIFO) data structure.

## Priority Queue

우선 순위 큐는 크 또는 스택과 같은 추상 데이터 유형이지만, 추가로 각 요소에는 연관된 우선 순위가 있다.
## Stack

Last-In-Last-Out (LIFO) data structure

## Hash Table

### Collision resolution

* separate chainig
* open addressing

테이블이 높은 load factor가 예상되거나, 데이터가 크거나, 데이터의 길이가 가변일 때 chaining이 좋다.

## Disjoint Set

Disjoint-set data structure is a data structure that tracks a set of elements partitioned into a number of disjoint subsets.

## Tree

트리는 값과 다른 노드에 대한 참조 목록으로 이루어진 노드의 콜렉션이며, 참조는 중복되지 않고, root에 대한 참조는 없는 제약을 가진다.

* Height
  * The number of edges on the longest path between a node and a descendant leaf.
* Level
  * 1 + the number of edges between a node and the root, i.e. (Depth + 1)
* binary tree
  * 각 노드는 최대 두 개의 자식을 가지는 트리
* full binary tree
  * 모든 노드가 0 혹은 2개의 자식을 가지는 트리
* balanced binary tree
  * 모든 노드의 왼쪽과 오른쪽 서브 트리 높이의 차이가 1이하인 트리.

### Binary Search Tree

### AVL Tree

self-balancing binary search tree (with Rotation operation)

### Red-Black Tree

A red–black tree is a kind of self-balancing binary search tree in computer science

### Segment Tree

A segment tree also known as a statistic tree is a tree data structure used for storing information about intervals, or segments.
A segment tree is a binary tree. The root of the tree represents the whole array.
The two children of the root represent the first and second halves of the array.
Similarly, the children of each node corresponds to the two halves of the array corresponding to the node.

### Fenwick Tree / Binary Indexed Tree

A data structure that can efficiently update elements and calculate prefix sums in a table of numbers.

## Heap

heap 조건을 만족하는 특수 트리.

* min heap
* max heap

## Graph
A graph is an abstract data type that is meant to implement the undirected graph and directed graph concepts from mathematics,
specifically the field of graph theory
