
Se dice que $f(n)=\Theta(g(n))$ si se cumplen las siguientes dos condiciones:

1- $f(n)=O(g(n))$
2- $f(n)=\Omega(g(n))$


La forma de loa curva es la misma, pero multiplicada por una constante esta un poco abajo y por otra constante esta por debajo del tiempo $T(n)$:

Representación grafica:

Si son iguales, esa función esta ajustada:

```python
for i in range(0, len(arreglo)): # O(n)
	if buscando == arreglo[i]    # O(1)
		return(True)
return(False) # O(1)

```

$T(n)=O(n)$
$T(n)=\Omega(n)$

Como son iguales, es una cota ajustada:

$T(n)=\Theta(n)$

