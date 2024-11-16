# Laboratorio 18 de Octubre - Nicolás Valdés Rodríguez - 21.756.280-5
## 1. Ordenamiento arreglos:
<p style="text-align: justify;">
Considere dos arreglos de tamaño n, uno con una serie de nombres de estudiantes que rindieron la PES, y otro con los puntajes ponderados que dichas personas
obtuvieron. Ordene ambos arreglos basados en las notas, de manera descendente (de mayor a menor).
HINT: Cuando una nota se mueva de lugar en el arreglo de notas, el nombre de la persona debe moverse también.
</p>

### Solución (Pseudocódigo):
<p style="text-align: justify;">
Para términos prácticos, asumimos que existe la función <cite>Largo(lista)</cite> previamente definida, que tiene las mismas propiedades de <cite>len(n)</cite> en Python; existen los arreglos <cite>Nombres</cite> y <cite>Notas</cite> también previamente definidos y con todos sus elementos.
</p>

```plaintext
INICIO PROCESO
1.  Contador = 0
2.  Para X = 0 hasta Largo(Notas) con paso 1 hacer:
3.      Contador = Contador + 1
4.  Fin Para
5.  I = 0
6.  Mientras I < Contador hacer:
7.      J = 0
8.      Mientras J < (Contador - I - 1) hacer:
9.          Si Notas[J] < Notas[J + 1] entonces:
10.             Temp1 = Notas[J]
11.             Temp2 = Notas[J + 1]
12.             Notas[J] = Temp2
13.             Notas[J + 1] = Temp1
14.             Temp1 = Nombres[J]
15.             Temp2 = Nombres[J + 1]
16.             Nombres[J] = Temp2
17.             Nombres[J + 1] = Temp1
18.         Fin Si
19.         J = J + 1
20.     Fin Mientras
21.     I = I + 1
22. Fin Mientras
FIN PROCESO
```

## 2. Ordenamiento matrices:
<p style="text-align: justify;">
Ordene las columnas de una matriz de m×n de manera ascendente (de menor a mayor).
</p>

### Solución (Pseudocódigo):
<p style="text-align: justify;">
Para términos prácticos, asumimos que existe la función <cite>Largo(lista)</cite> previamente definida, que tiene las mismas propiedades de <cite>len(n)</cite> en Python; existe la matriz <cite>Matriz</cite> también previamente definida como una lista de 2 dimensiones y con todos sus elementos.
</p>

```plaintext
INICIO PROCESO
1.  N = Largo(Matriz[0])
2.  M = Largo(Matriz)
3.  C = 0
4.  Mientras C < N hacer:
5.      I = 0
6.      Mientras I < M hacer:
7.          J = I
8.          Mientras (J > 0) y (Matriz[J][C] < Matriz[J - 1][C]) hacer:
9.              Temp = Matriz[J][C]
10.             Matriz[J][C] = Matriz[J - 1][C]
11.             Matriz[J - 1][C] = Temp
12.             J = J - 1
13.         Fin Mientras
14.         I = I + 1
15.     Fin Mientras
16.     C = C + 1
17. Fin Mientras
FIN PROCESO
```

## 3. Búsqueda Matrices:
<p style="text-align: justify;">
Considere una matriz de tamaño m×n que contiene nombres de personas. Implemente un algoritmo de búsqueda que imprima en pantalla la posición (fila,columna) de un nombre ingresado por el usuario.
</p>

### Solución (Pseudocódigo):
<p style="text-align: justify;">
Para términos prácticos, asumimos que existe la función <cite>Largo(lista)</cite> previamente definida, que tiene las mismas propiedades de <cite>len(n)</cite> en Python; existe la matriz <cite>Matriz</cite> también previamente definida como una lista de 2 dimensiones y con todos sus elementos.
</p>

```plaintext
INICIO PROCESO
1.  N = Largo(Matriz[0])
2.  M = Largo(Matriz)
3.  Leer Nombre
4.  Encontrado = Falso
5.  Fila = 0
6.  Mientras (Fila < M) y (Encontrado == Falso) hacer:
7.      Columna = 0
8.      Mientras (Columna < N) y (Encontrado == Falso) hacer:
9.          Si Matriz[Fila][Columna] == Nombre entonces:
10.             Imprimir (Fila,Columna)
11.             Encontrado = Verdadero
12.         Fin Si
13.         Columna = Columna + 1
14.     Fin Mientras
15.     Fila = Fila + 1
16. Fin Mientras
FIN PROCESO
```