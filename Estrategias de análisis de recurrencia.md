- Sustitución.
- Teorema maestro.
- Inducción
- Cambio de variable
- Ecuaciones homogeneas
- Algebra lineal

# Sustitución.

Ejemplo:

$T(n)=T(n-1)+n$

Donde $T(1)=1$:

$T(n)=T(n-1)+n$
1- $T(n)=T(n-1)+n$
- Si $n'=n-1$,  $T(n')=T(n'-1)+n'=T(n-1-1)+T(n-1)=T(n-2)+(n-1)$

2- $T(n)=T(n-1)+n=T(n-2)+(n-1)+n$

3- Si $n'=n-2$, $T(n')=T(n'-1)+n'=T((n-2)-1)+(n-2)=T(n-3)+(n+2)$
## Sustituyendo: $T(n-2)$

$T(n)=T(n-2)+(n-1)+n=T(n-3)+(n-2)+(n-1)+n$
4- 
$T(n)=T(n-4)+(n-3)+(n-2)+(n-1)+n$
Definiendo la formula:
$T(n)=T(n-r)+(n-(r-1))+(n-(r-2))+(n-(r-3))+...+n$
Tenemos esta formula donde r es la r-esima sustitucion, por lo cual el $n-r$ tiene que llegar en algun momento a $T(1).$
Con $n=5$:
	¿Cuando ocurre $T(n-r)=T(1)$
	donde $n-r=1$ => $r=n-1$
Si $r=n-1$ etnonces:
$T(n)=T(n-(n-1))+(n-((n-1)-1))+...+n$
Entonces podemos definir:
$T(n)=n+(n-1)+(n-2)+(n-3)+(n-4)=\frac{n(n+1)}{2}$

¿Para que valor debe tenmer "r" para que se cumpla que T(n)?

$2^{\log_{2}(n)}=n$

