### En el modelo RAM, para todas las siguientes operaciones basicas, se requiere 1 unidad de tiempo (1 paso)
- ### Hacer sumas y restas. $a + b$
- ### Hacer productos y divisiones. $ab$
- ### Asignar/inicializar variables. ``int a;(1 paso) , a = 1;(1 paso)``
- ### Acceder a una posicion de memoria de un arreglo ``a[2] (1 paso)`` 
- ### Evaluar condiciones logicas ``(==, !=, <, >, etc)``
## Ejemplo:

```c
int main(){
	int a = 5; // 2
	int b = 6; // 2
	int resultado = a + b; // 2
	int x; // 1
	x = 10; // 1
	int arreglo[3]; // 1
	arreglo[0] = 5; // 2
	arreglo[1] = 2;  // 2
	arreglo[2] = 20; // 2
	bool bandera = 5 > 3; // 3
}
```
 La suma de todos estos pasos es el resultado de la complejidad temporal, en este caso, la suma de los pasos seria $T_{A} = 18$
## Ejemplo:

```c
int miFuncion(int N, int M){
	int a = 0;  // 2
	int b = 0;  // 2
	int i,j;    // 2
	// Donde 2 + 2 + 2 = C1, la cual es nuestra primer constante.
	for (i = 1; i <= N; ++i){ // Se ejecuta N veces el ciclo for, ya que
		a = a + 3;            // esta instruccion se traduce como 2 pasos
	}                         // Esto se traduce como C2*N
	for (j = 1; j <= M; ++j){ // Los mismo ocurre en este ciclo, por lo cual
		b = b + 2;            // se ejecuta un total de M veces, multiplicado
	}                         // por el numero de pasos dentro del bloque.
	                          // Esto se traduce como C3*M
}
```
Por lo cual el tiempo del programa seria: $T_{programa}(N, M) = C_{2}N + C_{3}M + C_{1}$

## Ejemplo:

```c
// En este caso, tenemos un bucle for el cual
// tiene una complejidad temporal de n + 1, esto se
// puede verificar de la siguiente manera:
// Tfor = TB + TB + TB + ... + TB
for (i = 0; i <= n; ++i){
	// Donde este bloque se ejecuta las n+1 veces, al cual 
	// denotaremos como TB (tiempo de bloque)
}
// - Entonces decimos que:
//    Tprograma = (n+1)*TB
// - Como TB representa un valor constante, entonces podemos decir que 
//    TB = C1
// - Reescribiendo nos queda:
//    Tprograma = (n+1)*C1
//    Tprograma = C1*n + C1
```
Por lo tanto, la complejidad temporal es: $T_{programa}(n) = C_{1}n + C_{1}$

## Ejemplo:

```c
// En este caso se tienen bucles anidados, lo cual indica un mayor grado en la 
// complejidad temporal del programa.
for (i = 1; i <= N; ++i){ // Bucle externo se ejecuta un total de N veces. (Tfor1) 
	for (j = 1; j <= N; ++j){ // Bucle interno se ejecuta un total de N veces. (Tfor2)
		// instrucciones tomadas como una constante C1
	}
// - Tomando estos datos podemos decir que:
//    Tfor2 = C1 + C1 + C1 + ... + C1
//    Tfor2 = N*(C1)
// - En cuanto al bucle externo tomamos como punto de partida Tfor2:
//    Tfor1 = Tfor2 + Tfor2 + Tfor2 + ... + Tfor2
//    Tfor1 = N*Tfor2
// - Rescribimos: 
//    Tfor1 = N*(N*C1)
//    Tfor1 = C1*N**2
// - Por lo cual nos queda:
//    Tprograma = C1*N**2
}

```

Por lo tanto, la complejidad se define como: $T_{programa} = C_{1}N^{2}$