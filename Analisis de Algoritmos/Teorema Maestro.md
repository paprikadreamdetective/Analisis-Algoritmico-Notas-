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

1. Si $f(n)>n^{\log_{b}(a)}$ entonces $T(n)=\Theta(f(n))$ .
2. Si $f(n)<n^{\log_{b}(a)}$ entonces $T(n)=\Theta(n^{\log_{b}(a)})$
3. Si $f(n)=\Theta(n^{\log_{b}(a)})$ entonces $T(n)=\Theta(n\log(n))$
