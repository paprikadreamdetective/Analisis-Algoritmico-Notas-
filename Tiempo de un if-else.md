```python
if (condicion):
-------------------
-------------------
else:

-------------------
-------------------

```

Definimos la funcion por partes:

$\begin{cases} T(n) = 5n, & \text{si } condicion = true \\ T(n) = 7, & \text{si }condicion = false\end{cases}$

El tiempo del bloque if anterior se define como:

$T(n) = max(T_{if}(n),  T_{else}(n))$

Sustituyendo nos queda:

$T(n) = max(5n,  7)$

Como solo nos interesa el pero de los casos, sabemos que por la definición: 

$n > c$

donde $n$ esta definida como una función lineal y $c$ como una constante podemos partir de la propiedad de $a > b, c >0 \iff ac>bc$:

$5n > n > c$

por lo tanto:

$T(n)=O(5n)=O(n)$






