```python
	# Se tienen 5 diccionarios como entrada
	# 5 


	gatos1={"munchkin":3, "esfinge":1, "bombay":2}  # c1
    gatos2={"bombay":1, "manx":2, "esfinge":1}      # c2
    gatos3={"ragdoll":1, "munchkin":1}              # c3
    gatos4={"maine coon":3}                         # c4
    gatos5={"munchkin":1, "maine coon":4}           #c4
# Definimos una lista con los diccionarios de los gatos
    lista = [gatos1, gatos2, gatos3, gatos4, gatos5]    #c5
# Inicializamos el diccionario que almacenara el total de gatos
    totalGatos = {}                                     #c6
# Usamos un ciclo anidado para definir las claves del diccionario destino
    for it in lista:                                    # m=5
        for clave, valor in it.items():                 # n
            totalGatos[clave] = 0                       # c7
# De nueva cuenta usamos un ciclo anidado para poder ir sumando
# los valores asociados a las claves de cada diccionario y asignarlos al diccionario destino
    for it in lista:                                    # n
        for clave, valor in it.items():                 # n
            totalGatos[clave] = totalGatos[clave] + valor   # c8
    print(totalGatos)                                       # c9

'''
La complejidad temporal del programa esta representada de la siguiente manera:

    T(n) = c1 + c2 + c3 + c4 + c5 + c6 + c7*5*n + c8*5*n + c9

rescribiendo c1 + c2 + c3 + c4 + c5 + c6 + c9 = c10, c7*n*n = c7*n**(2) y c8*n*n = c8*n**(2)

    T(n) = c10 + c7*5*n + c8*5*n
    
por lo tanto

    T(n) = O(n)

el programa tiene una complejidad temporal de orden lineal.

'''

```