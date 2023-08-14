
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