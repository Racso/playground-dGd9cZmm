# El algoritmo de Dijkstra

El algoritmo de Dijkstra te permite calcular la ruta más corta entre un nodo (tú eliges cuál) y **todos los demás nodos en el grafo**. Encontrarás una descripción del algoritmo al final de esta página, pero ¡vamos a estudiarlo con un ejemplo explicado! Calcularemos la distancia más corta entre el nodo C y los demás nodos del grafo:

![Grafo de ejemplo](graph.png "")

Durante la ejecución del algoritmo, iremos marcando cada nodo con su _distancia mínima_ al nodo C (nuestro nodo elegido). Para el nodo C, esta distancia es 0. Para el resto de nodos, como todavía no conocemos esa distancia mínima, empieza siendo infinita (∞):

![Grafo de ejemplo](graph_c.png "")

También tendremos un _nodo actual_. Inicialmente, el nodo actual será C (nuestro nodo elegido). En la imagen, marcaremos el nodo actual con un punto rojo.

Ahora, revisaremos los vecinos de nuestro nodo actual (A, B y D) en cualquier orden. Empecemos con B. Sumamos la mínima distancia del nodo actual (en este caso, 0) con el peso de la arista que conecta al nodo actual con B (en este caso, 7), y obtenemos 0 + 7 = 7. Comparamos ese valor con la mínima distancia de B (infinito); el valor más pequeño es el que queda como la distancia mínima de B (en este caso, 7 es menos que infinito):

![Graph example](graph_c1.png "")

Bien. Ahora revisaremos al vecino A. Sumamos 0 (la distancia mínima de C, nuestro nodo actual) con 1 (el peso de la arista que conecta nuestro nodo actual con A) para obtener 1. Comparamos ese 1 con la mínima distancia de A (infinito) y dejamos el menor valor:

![Graph example](graph_c2.png "")

OK. Repetimos el procedimiento para D:

![Graph example](graph_c3.png "")

Genial. Hemos revisado todos los vecinos de C. Por ello, lo marcamos como _visitado_. Representemos a los nodos visitados con una marca de verificación verde:

![Graph example](graph_cok.png "")

We now need to pick a new _current node_. That node must be the unvisited node with the smallest minimum distance (so, the node with the smallest number and no check mark). That's A. Let's mark it with the red dot:

![Graph example](graph_a.png "")

And now we repeat the algorithm. We check the neighbours of our current node, ignoring the visited nodes. This means we only check B.

For B, we add 1 (the minimum distance of A, our current node) with 3 (the weight of the edge connecting A and B) to obtain 4. We compare that 4 with the minimum distance of B (7) and leave the smallest value: 4.

![Graph example](graph_a1.png "")

Afterwards, we mark A as visited and pick a new current node: D, which is the non-visited node with the smallest current distance.

![Graph example](graph_d.png "")

We repeat the algorithm again. This time, we check B and E.

For B, we obtain 2 + 5 = 7. We compare that value with B's minimum distance (4) and leave the smallest value (4). For E, we obtain 2 + 7 = 9, compare it with the minimum distance of E (infinity) and leave the smallest one (9).

We mark D as visited and set our current node to B.

![Graph example](graph_b.png "")

Almost there. We only need to check E. 4 + 1 = 5, which is less than E's minimum distance (9), so we leave the 5. Then, we mark B as visited and set E as the current node.

![Graph example](graph_e.png "")

E doesn't have any non-visited neighbours, so we don't need to check anything. We mark it as visited.

![Graph example](graph_final.png "")

As there are not univisited nodes, we're done! The minimum distance of each node now actually represents the minimum distance from that node to node C (the node we picked as our initial node)!

Here's a description of the algorithm:
1. Mark your selected initial node with a current distance of 0 and the rest with infinity.
2. Set the non-visited node with the smallest current distance as the current node `C`.
3. For each neighbour `N` of your current node `C`: add the current distance of `C` with the weight of the edge connecting `C`-`N`. If it's smaller than the current distance of `N`, set it as the new current distance of `N`.
4. Mark the current node `C` as visited.
5. If there are non-visited nodes, go to step 2.

# Exercise
The shown Python function is used during step 2 in the algorithm. It selects the node that should be set as current node. Fix it so it picks the correct node.

@[The shown function should select a new current node for Dijkstra's Algorithm. Fix it so it does it correctly.]({"stubs": ["nodes.py"], "command": "python3 test_nodes.py"})

# Next step
To obtain the paths that correspond to those minimum values, we simply need to keep track of the nodes every time we change the minimum distance of a node. Keep reading to check it out!
