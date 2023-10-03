El teorema maestro trabaja de la siguiente manera:
$T(n)=aT(\frac{n}{b})+f(n)$
$a$ : Suma de los tiempos en pedazos pequeños.
$T(\frac{n}{b})$ : Tiempo con pedazos mas pequeños donde $b$, significa que tanto se divide.
$f(n)$ : Tiempo de unir los pedazos mas pequeños.
Si el tiempo $f(n)$ es muy grande, entonces sobrepasa, esperamos que este termino sea lo mas pequeño posible.
Analizando mergesort:
```python
mergesort(n)
# Dividir la lsita entre 2:
# (izq, der)
# Llamar a mergesort(izq) donde izq = n/2 con T(n/2)
# Llamar a mergesort(der) donde der = n/2 con T(n/2)
# merge izq y der donde T(n) = O(n)
```
El tiempo de mergesort esta dado por:
$T(n)=2T(\frac{n}{2})+n$

Ejemplo:
$T(n)=2T(\frac{n}{2})+n$
con $T(1)=1$ .
$Solucion$ :
1. $T(n)=2T(\frac{n}{2})+n$
- $n'=\frac{n}{2}$ entonces: $T(n)=2T(\frac{n'}{2})+n'$
- $T(n')=2T(\frac{\frac{n}{2}}{2})+\frac{n}{2}=2T(\frac{n}{2^{2}})+\frac{n}{2}$
2. 
Para deshacernos del termino $T(n/2^{r})$ sustituimos u numero $r$ veces

Cuando $r=\log_{2}(n)$ se tiene 



## Teorema maestro
Ejemplo:
$T(n)=3T(\frac{n}{2})+n^{2}$
En la $r-esima$ sustitucion:
$T(n)=3^{r}T(\frac{n}{2^{r}})+rn^{2}$

### Teorema Maestro.
$T(n)=aT(\frac{n}{b})+f(n)$

1. Si $f(n)>_{pol}n^{\log_{b}(a)}$ entonces $T(n)=\Theta(f(n))$ .
2. Si $f(n)<_{pol}n^{\log_{b}(a)}$ entonces $T(n)=\Theta(n^{\log_{b}(a)})$
3. Si $f(n)=\Theta(n^{\log_{b}(a)})$ entonces $T(n)=\Theta(n\log(n))$

¿Que significa que sea polinomialmente mayor?
Vamos a decir que una funcion $f(n)>_{pol} g(n)$ se existe un $\epsilon > 0$ tal que que ocurra lo siguiente:

$f(n)>g(n)n^{\epsilon}$

Ejemplo:
$n^{2} >_{pol} n$
Lo que se quiere probar es que existe un $\epsilon > 0$ tal que $n^{2}>nn^{\epsilon}>n$
queremos mostrar que si $f$ es mayor que $g$ por un factor ($n^{\epsilon}$).
$n^{2}>nn^{1.5}>n$
$n^{1+0.5}=nn^{0.5}$
Luego:
$n^{2}>nn^{0.5}$
Entonces si $\epsilon=0.5$, se tiene que 
$n^{2}>nn^{\epsilon}$
es decir $n^{2}>_{pol}n$
$f(n)>g(n)n^{\epsilon}>g(n)$

Ejemplo:
$f(n)=n^{0.1}$
$g(n)=n^{0.01}$
$f(n)>_{pol}g(n)$

$n^{0.1}>n^{0.05}n^{\epsilon}>n^{0.01}$
$n^{0.01+0.04}=n^{0.01}n^{0.04}$
por lo tanto, $\epsilon=0.04$

Ejemplo:
$f(n)=n\log(n)$
$g(n)=n$
$f(n)>_{pol} g(n)$ AFIRMACION: No es pol mayor que g(n)
entonces:
$n\log(n)>nn^{\epsilon}$, con $\epsilon > 0$
si esto fuese cierto, llegariamos a una afirmacion
$ab>ac$ si $a>0$ entonces $b>c$
luego:
$\log(n)>n^{\epsilon}$ <- CONTRADICCION

Por que es cierto que $\log(n) < n^{\epsilon}$ para cualquier $\epsilon > 0$ para n suficientemente grande.
Regla de l'hopital
$\lim_{x->\infty}(\frac{f(n)}{g(n)})$ con $\lim_{x->\infty}(f(n))=\infty$ , $\lim_{x->\infty}(g(n))=\infty$ 

$\lim_{x->\infty}(\frac{f(n)}{g(n)})=0$
luego para un $n$ sufientemente grande:
$f(n)<g(n)$
$\lim_{x->\infty}(\frac{\log(n)}{n^{\epsilon}})=0$
por lo tanto: $n^{\epsilon}>\log(n)$

Ejemplo teorema maestro:
$T(n)=9T(\frac{n}{3})+n$
Usando: 
$T(n)=aT(\frac{n}{b})+f(n)$

1. Si $f(n)>_{pol}n^{\log_{b}(a)}$ entonces $T(n)=\Theta(f(n))$ .
2. Si $n^{\log_{b}(a)}>_{pol}f(n)$ entonces $T(n)=\Theta(n^{\log_{b}(a)})$
3. Si $f(n)=\Theta(n^{\log_{b}(a)})$ entonces $T(n)=\Theta(n\log(n))$
- $n^{log_{3}(9)}=n^{2}$
- Se tiene que $n^{2}>n$ y ademas sabemos que $n^{2}>nn^{0.5}$ luego:
- $n^{2}>_{pol}n$ 
- Por lo tanto, $T(n)=\Theta(n^{log_{3}(9)})=\Theta(n^{2})$
Ejemplo: 
$T(n)=T(\frac{n}{\frac{5}{3})+1$

$a=1$, $b=5/3$, 





