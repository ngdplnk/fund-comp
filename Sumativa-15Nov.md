# Sumativa 15 de Noviembre - Nicolás Valdés Rodríguez - 21.756.280-5
## 1. Promedio de temperaturas diarias:
<p style="text-align: justify;">
Diseñe y escriba pseudocódigo o código Python que permita al usuario ingresar las temperaturas diarias de una semana (7 días) en un arreglo. Luego, el programa debe calcular y mostrar:
</p>

- La temperatura promedio de la semana.
- La temperatura más alta y la más baja registrada durante la semana.
- La cantidad de días en que la temperatura fue superior al promedio.

### Solución (Python):
```python
NumeroDias = int(input('Ingrese número de días: ')) # Guardamos el número de días.
Dias = [] # Creamos una lista vacía para guardar las temperaturas de los días

i = 1
while i <= NumeroDias:
    Dias.append(int(input(f'Ingrese la temperatura del día {i}: '))) # Guardamos la temperatura de cada día en la lista
    i += 1

Promedio = 0 # Inicializamos la variable 'Promedio' que primero usaremos para guardar la suma de las temperaturas
i = 0
while i < NumeroDias:
    Promedio += Dias[i] # Sumamos todas las temperaturas
    i += 1
Promedio = Promedio / NumeroDias # Dividimos la suma de las temperaturas entre el número de días para obtener el promedio

print(f'Temperatura promedio de la semana: {Promedio}') # Mostramos el promedio de las temperaturas

TempMax = Dias[0] # Inicializamos la temperatura más alta con la primera temperatura
i = 0
while i < NumeroDias:
    if Dias[i] > TempMax: # Si la temperatura del día es mayor a la temperatura más alta, se guarda la nueva temperatura
        TempMax = Dias[i]
    i += 1

print(f'Temperatura más alta: {TempMax}') # Mostramos la temperatura más alta

TempMin = Dias[0] # Inicializamos la temperatura más baja con la primera temperatura
i = 0
while i < NumeroDias:
    if Dias[i] < TempMin: # Si la temperatura del día es menor a la temperatura más baja, se guarda la nueva temperatura
        TempMin = Dias[i]
    i += 1

print(f'Temperatura más baja: {TempMin}') # Mostramos la temperatura más baja

DiasMayoresPromedio = 0 # Inicializamos un contador para los días con temperatura superior al promedio
i = 0
while i < NumeroDias:
    if Dias[i] > Promedio: # Si la temperatura del día es mayor al promedio se suma 1 al contador
        DiasMayoresPromedio += 1
    i += 1

print(f'Días con temperatura superior al promedio: {DiasMayoresPromedio}') # Mostramos el número de días con temperatura superior al promedio
```

## 2. Filtrado de números pares e impares:
<p style="text-align: justify;">
Diseñe y escriba pseudocódigo o código Python que permita al usuario ingresar 10 números enteros en un arreglo. El programa debe separar los números en dos arreglos diferentes: uno que contenga solo los números pares y otro que contenga solo los números impares. Finalmente, el programa debe mostrar ambos arreglos por separado.
</p>

### Solución (Python):
```python
NumeroNumeros = int(input("Ingrese la cantidad de numeros enteros a ingresar: ")) # Guardamos la cantidad de números que se van a ingresar
ListaNumeros = [] # Creamos una lista vacía para guardar los números
i = 1
while i <= NumeroNumeros:
    ListaNumeros.append(int(input(f'({i}) Ingrese un número entero: '))) # Guardamos los números en la lista
    i += 1

NumerosPares = [] # Creamos una lista vacía para guardar los números pares
NumerosImpares = [] # Creamos una lista vacía para guardar los números impares

i = 0
while i < len(ListaNumeros):
    if ListaNumeros[i] % 2 == 0:
        NumerosPares.append(ListaNumeros[i]) # Guardamos los números pares en la lista de números pares
    else:
        NumerosImpares.append(ListaNumeros[i]) # Guardamos los números impares en la lista de números impares
    i += 1

Pares = '' # Creamos un string vacío que usaremos para mostrar los números pares
i = 0
while i < len(NumerosPares): # Recorremos la lista de números pares para agregarlos al string
    if i == len(NumerosPares) - 1:
        Pares += str(NumerosPares[i]) # Si es el último número par, no se agrega la coma
    else:
        Pares += str(NumerosPares[i]) + ', ' # Si no es el último número par, se agrega la coma
    i += 1

print(f'Números pares: {Pares}') # Mostramos los números pares

Impares = '' # Creamos un string vacío que usaremos para mostrar los números impares
i = 0
while i < len(NumerosImpares): # Recorremos la lista de números impares para agregarlos al string
    if i == len(NumerosImpares) - 1:
        Impares += str(NumerosImpares[i]) # Si es el último número impar, no se agrega la coma
    else:
        Impares += str(NumerosImpares[i]) + ', ' # Si no es el último número impar, se agrega la coma
    i += 1

print(f'Números impares: {Impares}') # Mostramos los números impares
```

## 3. Suma de valores de una matriz:
<p style="text-align: justify;">
Diseñe y escriba pseudocódigo o código Python que permita al usuario ingresar una matriz de enteros de tamaño 3 x 3. El programa debe calcular y mostrar la suma de todos los elementos de la matriz, así como la suma de los elementos de cada fila y cada columna por separado.
</p>

### Solución (Python):
```python
CantidadDeFilas = int(input("Ingrese la cantidad de filas de la matriz: ")) # Guardamos la cantidad de filas de la matriz
CantidadDeColumnas = int(input("Ingrese la cantidad de columnas de la matriz: ")) # Guardamos la cantidad de columnas de la matriz

Matriz = [] # Creamos una lista vacía que contendrá las filas de la matriz
i = 0
while i < CantidadDeFilas:
    j = 0
    fila = [] # Creamos una lista vacía que contendrá los valores de la fila actual
    while j < CantidadDeColumnas:
        fila.append(int(input(f"Ingrese el valor de la posición ({i},{j}): "))) # Guardamos los valores de la fila actual
        j += 1
    Matriz.append(fila) # Agregamos la fila actual a la matriz
    i += 1

SumaTotal = 0 # Inicializamos la variable que contendrá la suma de todos los elementos de la matriz
i = 0
while i < CantidadDeFilas:
    j = 0
    while j < CantidadDeColumnas:
        SumaTotal += Matriz[i][j] # Sumamos cada uno de los elementos de la matriz
        j += 1
    i += 1

print(f'Suma de todos los elementos: {SumaTotal}') # Mostramos la suma de todos los elementos de la matriz

i = 0
while i < CantidadDeFilas:
    SumaFila = 0 # Inicializamos la variable que contendrá la suma de los elementos de la fila actual
    j = 0
    while j < CantidadDeColumnas:
        SumaFila += Matriz[i][j] # Sumamos cada uno de los elementos de la fila actual
        j += 1
    print(f'Suma de la fila {i+1}: {SumaFila}') # Mostramos la suma de los elementos de la fila actual
    i += 1

i = 0
while i < CantidadDeColumnas:
    SumaColumna = 0 # Inicializamos la variable que contendrá la suma de los elementos de la columna actual
    j = 0
    while j < CantidadDeFilas:
        SumaColumna += Matriz[j][i] # Sumamos cada uno de los elementos de la columna actual
        j += 1
    print(f'Suma de la columna {i+1}: {SumaColumna}') # Mostramos la suma de los elementos de la columna actual
    i += 1
```
