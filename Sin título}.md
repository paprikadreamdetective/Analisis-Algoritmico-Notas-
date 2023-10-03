

$T_{n+1}=\alpha t_{n}+(1+\alpha)T_{n}$
$T_{n+1}=\alpha t_{n}+(1+\alpha)[\alpha t_{n}(1+\alpha)T_{n}]$


1:
$T(n)=T(n-1)+2n$
$T(n-1)=T(n-2)+2(n-1)$
Sustituyendo en $T(n)$:
$T(n)=T(n-2)+2(n-1)+2n$

2:
$T(n)=T(n-1)+2n$
$T(n-2)=T(n-3)+2(n-2)$
Sustituyendo en $T(n)$:
$T(n)=T(n-3)+2(n-2)+2(n-1)+2n$

$T(n)=T(n-r)+2(n-(r-1))+2(n-(r-2))+2n$

$T(n-r)=T(1)=2$ , $r=n-1$
$T(n)=T(n-(n-1))+2(n-(n-1-1))+2(n-(n-1-2))+2n$
$T(n)=T(1)+2(1+1)+2(1+2)+ ... + 2n$
$T(n)=2(1)+2(2)+2(3)+ ... + 2n$
$T(n)=2(1+2+3+ ... +n)$
$T(n)=2(\frac{n(n+1)}{2})$
$T(n)=n(n+1)$

Conidera la secuencia de de fibonacci:

$f(n)=f(n-1)+f(n-2)$ donde $f(0)=0$ y $f(1)=1$


Considera la siguiente sucesion:
$T(n)=2T(n-1)+1$, $T(1)=1$
Encuentre una formula explicita para la siguiente funcion de recurrencia:

1- $T(n)=2T(n-1)+1$
Si $n´=n-1$ entonces:
$T(n')=2T(n'-1)+1$
$T(n-1)=2T(n-1-1)+1=2T(n-2)+1$
Sustituyendo:
$T(n)=2T(n-1)+1$
$T(n)=2(2T(n-2)+1)+1$

2- $T(n)=2^{2}T(n-2)+2+1$
Si $n´=n-2$ entonces:
$T(n')=2T(n'-1)+1$
$T(n-2)=2T(n-2-1)+1=2T(n-3)+1$
Sustituyendo:
$T(n)=2^{2}T(n-2)+2+1$
$T(n)=2^{2}(2T(n-3)+1)+2+1$
$T(n)=2^{3}T(n-3)+4+2+1$
$T(n)=2^{3}T(n-3)+4+2+1$
donde $$




