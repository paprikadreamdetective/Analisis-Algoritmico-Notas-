## Propiedades:

1- $\Omega(cf(n))=\Omega(f(n))$

2- Si $f(n) < g(n)$ entonces: $\Omega(min(f(n)+g(n)))=\Omega(f(n))$

3- $\Omega(f(n))+\Omega(g(n))=\Omega(f(n)+g(n))$

4- $\Omega(f(n))\Omega(g(n))=\Omega(f(n)g(n))$

5- Para $f(n)$ y $g(n)$ $\neq$ $c$

6- $\Omega(f(n)+c)=\Omega(f(n))$

Para calcular el tiempo de una cota inferior, se toma el mínimo como se ve en la siguiente parte:

$T_{if}(n)=\Omega(min(T_{1}(n), T_{2}(n)))$

Ejemplo:

```python
a = 0
if valor > 10:
	for i in range(1, n+1)
		for j in range(1, n+1)
			a = a + i + j
else:
	for k in range(1, n+1):
		a = a + k
```

