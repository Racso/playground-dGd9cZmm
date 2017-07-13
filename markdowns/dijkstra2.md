# Calculating paths,  too

Let's run the algorithm again in our graph:

![Graph example](graph.png "")

 This time, however, let's keep track of the actual shortest paths. They all begin empty, except for the path of the initial node, which simply contains it:

```python
path to A = empty
path to B = empty
path to C = C
path to D = empty
path to E = empty
```

The new thing is that we will update those paths _every time we modify the minimum distance of a node_.

Let's check the neighbours of our current node. Let's begin with B. We add 0 + 7 = 7. As that value is less than infinity, we change the minimum distance of B with it _and replace the current path to B_ with the path to the current node (`path to C`, which is `C`), plus `B`. This means that `path to B = C, B`.

We repeat the procedure with neighbours A and D. After that, our graph and paths are as follows:

![Graph example](graph_cok.png "")

```python
path to A = C, A
path to B = C, B
path to C = C
path to D = C, D
path to E = empty
```

Our current node is now set to A. We check its only non-visited neighbour, B. As we replace the minimum distance of B from 7 to 4, we also replace its current path with the path of the current node A (`C, A`), plus B: `path to B = C, A, B`).


![Graph example](graph_a1.png "")

```python
path to A = C, A
path to B = C, A, B
path to C = C
path to D = C, D
path to E = empty
```

We mark A as visited and select our next current node: D. We check two neighbours: B and E.

When checking B, we don't replace its minimum distance (as the existing 4 is less than the calculated 7), so we don't replace its current path, either. Remember: we only replace a path when we modify the minimum distance of a node.

We then check neighbour E, update its minimum distance (9, which is less than infinity) and path (`path to E = C, D, E`, which is the `path to D` plus E), and are left with this:

![Graph example](graph_b.png "")

```python
path to A = C, A
path to B = C, A, B
path to C = C
path to D = C, D
path to E = C, D, E
```

Let's fast-forward a bit: we continue applying the algorithm until we're done. After we finish, our graph and paths will be the following:

![Graph example](graph_final.png "")

```python
path to A = C, A
path to B = C, A, B
path to C = C
path to D = C, D
path to E = C, A, B, E
```

Congratulations! Those are the minimum paths between C and every other node!