$T(n)=$Tiempo de mergsort

Pasos:

```python
mergesort(n)
# Dividir la lsita entre 2:
# (izq, der)
# Llamar a mergesort(izq) donde izq = n/2 con T(n/2)
# Llamar a mergesort(der) donde der = n/2 con T(n/2)
# merge izq y der donde T(n) = O(n)
```

$T(n)=T_{izq}(\frac{n}{2})+T_{der}(\frac{n}{2})+O(n)$
$T(n)=2T(\frac{n}{2})+O(n)$

Cuando trabajamos con algoritmos recursivos, salen relaciones de recurrencia.
