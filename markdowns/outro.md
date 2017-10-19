# Mejoras

Aquí está el algoritmo de Dijkstra de nuevo:
1. Marca el nodo inicial que elegiste con una distancia actual de 0 y el resto con infinito.
2. Establece el nodo no visitado con la menor distancia actual como el nodo actual `A`.
3. Para cada vecino `V` de tu nodo actual `A`: suma la distancia actual de `A` con el peso de la arista que conecta a `A` con `V`. Si el resultado es menor que la distancia actual de `V`, establécelo como la nueva distancia actual de `V`.
4. Marca el nodo actual `A` como visitado.
5. Si hay nodos no visitados, ve al paso 2.

Veamos algunas mejoras pequeñas que podemos hacerle al algoritmo:
* Si sólo necesitas la ruta entre dos nodos específicos, puedes detener el algoritmo tan pronto como el segundo nodo sea marcado como visitado.
* A veces, hay varias rutas mínimas entre dos nodos (diferentes rutas con el mismo peso). Si quieres, puedes llevar la cuenta de todas esas variantes: en el paso 3, si hay un empate entre el valor calculado y la distancia actual, almacena tanto la ruta antigua como la nueva. Esto complica las cuentas, pero podría serte útil.
* Si terminas el algoritmo porque no hay más nodos no visitados pero todavía existen nodos cuya distancia mínima es todavía infinita, esos nodos no tienen ninguna ruta válida al nodo inicial.

# Finalización

¡Es todo! ¡Si tienes preguntas o propuestas para mejorar este tutorial, por favor ponte en contacto!
