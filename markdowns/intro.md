# Welcome!

This short playground will give you some fundamentals about Dijkstra's algorithm.

# Prerequisites
* Graph Theory Basics: graphs, vertices and edges. You can learn all of it in this Playground: [Graph Theory Basics](https://tech.io/playgrounds/5470/graph-theory-basics).

# Weighted graphs

In some applications, it's useful to model data as a graph with weighted edges. These graphs are called "weighted graphs". What are "weighted edges", you wonder? Consider this graph:

![Graph example](graph.png "")

Let's imagine that each node is a City, and each edge is an existing road between two cities. This means that you can drive from A to B directly. However, you can't drive from A to D directly, as there's no road between those cities; instead, for example, you need to go from A to B and then from B to D.

Now, not every road is equal. Some of them are longer, some aren't in good shape (so you need to go slowly), some have more traffic... In short: you need more time for traversing some roads than other. We may represent that time with weights that we assign to the roads (edges of the graph). In the example, let's assume that each number represent the amount of time in hours that it takes you to take a road. This would mean that going from A to B takes 3 hours if you use the road that connects them directly.

As you will discover, you can represent a lot of different things (time, distance, money...) with the weights in the edges of a graph.

# Paths

Suppose that I ask you how much time would it take you to go from C to B. You may say that it would take you 7 hours, by taking the road that connects them directly. However, you may also say that you can complete the trip in only 4 hours if you go from C to A and then from A to B. There are other routes you can take.

Formally, a path is _a sequence of edges which connect a sequence of distinct vertices_. If there are no multiple edges in your graph (i.e. parallel edges that connect the same pair of nodes, as if you had two different roads directly connecting the same two cities), you can describe a path simply as the list of nodes it connects. For example, the two paths we mentioned in our example are C, B and C, A, B.

# Shortest paths

As we said before, it takes 7 hours to traverse path C, B, and only 4 hours to traverse path C, A, B. Those times are the _weights_ of those paths. As such, we say that the weight of a path is the sum of the weights of the edges it contains.

As you can see, path C, A, B is shorter than path C, B. In fact, it is the shortest path between C and B (try to find a shorter one!). Of course, in lots of applications, it would be really useful to be able to calculate in advance what the shortest path between two nodes is. What's the shortest route I can take to go home? What's the cheapest way I can fly from Bucaramanga to Hawaii? How can I efficiently route this data packet from node 1 to node 2 in this network? That kind of questions can be solved with shortest path algorithms or variants.

So... How can we obtain the shortest path in a graph? There are several options. Dijkstra's algorithm is one of them! Keep reading to know how!

?[Exercise: What is the weight of the shortest path between C and E?]
-[ ] 8
-[ ] 9
-[x] 5
-[ ] 7
