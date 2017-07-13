# Enhancements

Here's Dijkstra's Algorithm again:
1. Mark your selected initial node with a current distance of 0 and the rest with infinity.
2. Set the non-visited node with the smallest current distance as the current node `C`.
3. For each neighbour `N` of your current node `C`: add the current distance of `C` with the weight of the edge connecting `C`-`N`. If it's smaller than the current distance of `N`, set it as the new current distance of `N`.
4. Mark the current node `C` as visited.
5. If there are non-visited nodes, go to step 2.

Let's see some small enhancements we may apply to the algorithm:
* If you only need the path between two specific nodes, you can stop the algorithm as soon as you mark your second node as visited.
* Sometimes, there are several minimum paths between two nodes (different paths with the same weights). If you wish, you can keep track of all those variants: in step 3, if there is a tie between the calculated value and the current distance, save both the old current path and the new one. This complicates the tracking, but it may be useful to you.
* If you finish the algorithm because there are not univisted nodes left but there are nodes which minimum distance is still infinity, those nodes don't have any valid path to the original node.

# Ending

That's it! If you have any questions or proposals on how to improve this tutorial, please get in touch!