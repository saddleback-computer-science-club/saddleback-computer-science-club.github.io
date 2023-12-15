---
title: 'Breadth First Search'
date: 2023-12-15T13:37:36-08:00
draft: false

author: 'Matthew Reese'
---

## Definition

Breadth first search is a searching algorithm designed to find the shortest possible path from one node to another in a graph. Iteration is depth-based in relation to the specified root node.

The previous paragraph had a lot of terms, many of which you may have never heard in relation to computer science. Let's unpack them all in the context of this algorithm.

graph
: A data structure holding a collection of nodes and their connections

node
: A singular data point on a graph, having a value and connections

root node
: The starting node of the algorithm (or in other contexts, the topmost node of a tree)

depth-based iteration
: The algorithm begins at the specified root node, *then* obtains a list of nodes at  the next level down (lower depth). Those will then be iterated through, and the process repeats until all connected nodes have been checked.

### Examples

Ex

## External Resources

- [University of Wisconsin](https://pages.cs.wisc.edu/~vernon/cs367/notes/13.GRAPH.html#bfs): Great resource. Note that their definition of BFS is slightly different than the one on this page, though still perfectly applicable to everything here.
- [Wikipedia page](https://en.wikipedia.org/wiki/Breadth-first_search): Note that information in the first paragraph is slightly inaccurate. The page claims *"Breadth-first search (BFS) is an algorithm for searching a tree data structure."* BFS may be used for graphs as well (a tree is a type of undirected graph for which there are no cyclic paths).
