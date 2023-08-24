
## Propiedades:

1- $O(cf(n))=O(f(n))$

2- Si $f(n) > g(n)$ entonces: $O(f(n)+g(n))=O(f(n))$

3- $O(f(n))+O(g(n))=O(f(n)+g(n))$

4- $O(f(n))O(g(n))=O(f(n)g(n))$

5- $O(f(n))+c=O(f(n))$

6- $f(n)O(g(n))=O(f(n)g(n))$

Ejemplos: 

$O(7n^{2})=O(n^{2})$
$O(7\log(n^{2}))=O(\log(n^{2}))$

Ejemplos:

$O(n^{2}+n)=O(n^{2})$
$O(n^{2}+n\log(n))=O(n^{2})$
$O(\log(n)+n+7)=O(\log(n)+n)=O(n)$
$O(nn!+n2^{n}+n^{1000000})=O(nn!)$

Nota: Recordar las propiedades de las desigualdades.

Ejemplos:

```python
suma = 5 # O(c1)
for i in range(1, n+1) # O(n)
	suma = suma + i # O(c3)
print(suma) # O(c2)
```

$T(n)=O(c_{1})+O(c_{c2}+nO(c_{3}))=O(c_{1}+c_{2})+O(nc_{3})=O(c_{1}+c_{2}+c_{3}n)=O(c_{4}+c_{3}n)$

Por definicion:

$n > c_{4}$ entonces:

$c_{3}n>n>c_{4}$

reescribiendo:

$T(n)=O(c_{3}n)=O(n)$

Por lo tanto, su complejidad temporal es linea.

## Ejemplo:

Supongamos que $f(n)=1$
$T(n)=O(c)=O(cf(n))=O(f(n))$
Por lo tanto:
$O(1)$

## Ejemplo:

```python
if condicion:
# instrucciones O(n)
else:
#instrucciones O(n^2)

```

$T(n)=O(max(T_{if},T_{else}))$

$T(n)=O(max(n, n^{2}))$

Por lo tanto: 

$T(n)=O(n^{2})$

Ya que nos interesa el peor caso.

## Ejemplo:

```python
# Busqueda lineal

arreglo = [range(0, n)] # O(1)

for i in range(0, len(arreglo)): # O(n)
	if buscando == arreglo[i]    # O(1)
		return(True)
return(False) # O(1)

# T(n) = O(n) + O(1) O(1)
# T(n) = O(n) + O(1+1)
# T(n) = O(n) + O(1)
# T(n) = O(n)
```

Por lo tanto, este programa que realiza la búsqueda lineal tiene una complejidad temporal de 
$T(n)=O(n)$

## Ejemplo:

```python
def miFuncion(n):
	a = 0    # O(1)
	for i in range(1, n+1):  # O(n)
		for j in range(1, n+1): # O(n)
			a = a + i + j     # O(1)


```
Si queremos calcular la complejidad temporal, realizamos lo siguiente:

$T(n) = O(1) + O(1) + O(1) + O(n^{2})$

Ejercicio: 

Como tenemos 3 bucles, hay que considerar que cada uno tiene un tiempo n, por lo cual definimos lo siguiente:

```python
def miFuncion(n):
	a = 0   # O(1)
	for i in range(1, n+1) # O(n)
		for j in range(1, n+1) # O(n)
			for k in range(1, n+1) # O(n)
				a = a + i + j + k # O(1)
```


$T(n) = O(n)*O(n)*O(n)*O(1)+O(1)$
$T(n) = O(n*n*n*1*1) = O(n^{3})$
Por lo tanto la complejidad temporal es:
$T(n)=O(n^{3})$

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

$\begin{cases} T(n) = O(n^{2}), & \text{si } valor > 10 \\ T(n) = O(n), & \text{si }valor < 10\end{cases}$}

Obtenemos $T_{max}$:
$T(n) = T_{max}(O(n^{2}), O(n))$
$T(n) = O(n^{2})$

## Ejemplo:

```python
def buscar(arreglo, num):
	n = len(arreglo) # O(1)
	for i in range(0, n): # O(n)
		if arreglo[i] == num: # O(1)
			return(True) # O(1)
	return(False) # O(1)

```

## Identificar logaritmos.

¿Necesitamos saber cuantas veces podemos dividir $n$ entre $2$ para llegar a $1$?

```python
n = input()
suma = 0
div = n
while div > 1:
	suma = suma + div
	div = div/2
print(suma)


```

Empezaremos por decir que el tiempo del bucle while esta dado de la siguiente manera:

$T_{while}(n)=($numero de veces que se repite$)*O(1)$

Podemos realizar la siguiente tabla: 

|  | 8 | 4 | 2| 1 |
|--------------|--------------| --------------|--------------|--------------| --------------|--------------|
| Iteracion | 0 | 1 | 2 | 3 | ... | $i$ |
| div | $n$ | $\frac{n}{2}$ | $\frac{(\frac{n}{2})}{2}$ | $\frac{(\frac{n}{2^{2}})}{2}$ |
| div reescrito | $\frac{n}{2^{0}}$ |$\frac{n}{2^{1}}$| $\frac{n}{2^{2}}$ | $\frac{n}{2^{3}}$ | ... | $\frac{n}{2^{i}}$ |

 Para esto debemos considerar que el bucle while se detiene cuando la variable div vale 1, es decir:
 ```python   
 div = 1
 ```
 Puesto que la condición es:
 ```python
 while div > 1:
``` 
donde:

$div = \frac{n}{2^{i}} = 1$

$i$ es la i-esima iteración.

Definimos la igualdad como:

$\frac{n}{2^{i}}=1$
$n = 2^{i}$

Aplicamos el operador de logaritmo en ambos lados de la igualdad:

$\log(n)=\log(2^{i})$
$\log(n)=i\log(2)$
$i=\frac{\log(n)}{\log(2)}$
$i=\frac{1}{\log(2)}\log(n)$

Podemos observar que el valor $i$ con el cual denotamos las iteraciones del bucle, da como resultado una complejidad logarítmica, si aplicamos las propiedades de la notación asintótica nos queda que:

$T(n)=\frac{1}{\log(2)}\log(n)$

Aplicamos: $O(cf(n))=O(f(n))$

$T(n)=O(\frac{1}{\log(2)}\log(n))=O(\log(n))$

$T(n)=O(\log(n))$
 
Por lo tanto, el bucle tiene una complejidad temporal de orden logaritmico

$\log_{a}(x)=\frac{\log_{b}(x)}{\log_{b}(a)}$
