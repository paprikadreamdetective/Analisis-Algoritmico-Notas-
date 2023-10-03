En backtraking, se puede construir un arbol de busqueda que representa las decisiones que vamos tomando.
En poda y ramificacion (Branch and Bound) hacemos una busqueda en anchura.
- En vuelta hacia atras queremos emumerar
- En poda y ramificacion queremos encontrar una solucion optima
Pseudocodigo:
```python
from queue import Queue
cola = Queue()
cola.put("a") # Insertar elementos a la cola
cola.put("b")
cola.put("c")
cola.popLeft() # suprimir un elemento de la cola
# Pseudocodigo de poda y ramificacion:
# Busqueda en anchura para arboles:
def BA(arbol, nodoRaiz):
	fila = Queue()
	fila.put(nodoRaiz)
	while (not fila.empty()):
		nodo = fila.popLeft()
			for hijo in nodo.hijos:
				fila.put(hijo)
# Nodo   |   Fila
#  x          [] 
#  x          [A] put 
#  A          []  popLeft
#  A          [B, H] put, put
#  B          [H] popLeft
#  B          [H, C, D] put, put
#  H          [C, D] popLeft
#  H          [C, D, I, O] put, put
#  C          [D, I, O] popLeft
#  C          [D, I, O, E, F] put, put
#  D          [I, O, E, F] popLeft
#  D          [I, O, E, F, G, J] put, put
#  I          [O, E, F, G, J] popLeft
#  I          [O, E, F, G, J, K, L] put, put
#  O          [E, F, G, J, K, L] popLeft
#  O          [E, F, G, J, K, L, M, N] put, put
#  E          [F, G, J, K, L, M, N] popLeft
#  F          [G, J, K, L, M, N] popLeft
#  G          [J, K, L, M, N] popLeft
#  J          [K, L, M, N] popLeft
#  K          [L, M, N] popLeft
#  L          [M, N] popLeft
#  M          [N] popLeft
#  N          [] popLeft
#  fin
# Imprime: A, B, H, C, D, I, O, E, F, G, J, K, L, M, N
```
Los problemas tienen las mismas condiciones que vuelta hacia atrás:
- "$n$" Decisiones
- Cada decisión se toma de un conjunto finito de decisiones
- La solución se expresa como un vector.
Además se tienen las siguientes condiciones:
- Cada decision tiene un costo/ganancia asociada
Nos interesa maximizar la ganancia o minimizar el costo.

Problema de asignacion de tareas:
```python
     T1  T2  T3  T4
A    2   9   5   3 
B    4   3   3   9
C    6   2   4   1
D    2   7   3   5

SOL: {T1, T3, T2, T4}
      A,  B,  C,   D
COSTO: {2 + 3 + 2 + 5} = 12
        A   B   C   D
La tecnica de poda y ramificacion no nos da la solucion optima, nos da un valor cercano!!!

Una solucion optima es la mejor solucion posible.
```
La funcion de acotamiento nos dara soluciones rapidas, para minimizar el costo.
Funcion de acotamiento:
Nos fijamos en los trabajos por decidir y elegimos los que tengan el menor tiempo, aunque se repitan
