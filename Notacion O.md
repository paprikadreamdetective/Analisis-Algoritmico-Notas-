
Por definicion, decimos que:

$f(n)=O(n)$

Si existe un numero $M > 0$   y  un  $n_{0} >0$ tal que:

$f(n)<Mg(n)$

para $n > n_{0}$

## Ejemplo:

Supongamos que:

$f(n) = 2n + 1$ con $g(n) = n$

Funciones las cuales podemos representar como: 

![[Pasted image 20230813202546.png]]

Basándonos en la definición anterior, podemos usar un numero $M > 0$   y  un  $n_{0} >0$ tal que 
$f(n)<Mg(n)$, donde nuestro ejemplo de cota superior se define como $M=3$ y $n=10$: 

$3g(n)$
$n = 0$, $3g(0)=0$
$n=10$, $3g(10)=30$

la grafica se mostraria de la siguiente manera:

![[Pasted image 20230813231618.png]]


Por lo tanto, $f(n)$ se puede acotar superiormente por un múltiplo de $n$

La notación O la usamos para poder acotar una función y poder encontrar el peor de los casos.


