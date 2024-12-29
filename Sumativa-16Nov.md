# Sumativa: Operaciones en binario y álgebra de Boole
## Autor: Nicolás Valdés Rodríguez | 21.756.280-5

## 1. Suma en binario
Realiza las siguientes operaciones binarias, describiendo el proceso y mostrando claramente el resultado:

### a) 10101 + 11011, en notación de 1 byte con signo

#### 1.  **Convertir a 8-bits:**

* `10101` → `00010101`

* `11011` → `00011011`

#### 2.  **Suma binaria:**

```plaintext
  00010101
+ 00011011
----------
  00110000
```

#### 3.  **Interpretación en decimal:**

| Bit Posición | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
| :----------- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| Dígito binario | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
| Valor decimal  | 2<sup>7</sup>=128 | 2<sup>6</sup>=64 | 2<sup>5</sup>=32 | 2<sup>4</sup>=16 | 2<sup>3</sup>=8 | 2<sup>2</sup>=4 | 2<sup>1</sup>=2 | 2<sup>0</sup>=1  |
| Cálculo  | 0 * 128 | 0 * 64 | 1 * 32 | 1 * 16 | 0 * 8 | 0 * 4 | 0 * 2 | 0 * 1 |

De esta forma: `00110000` → `32 + 16 = 48`

### b) 11110101 + 1011011, en notación de 2 bytes sin signo

#### 1. Convertir a 16-bits:

* `11110101` → `0000000011110101`

* `1011011` → `0000000001011011`

#### 2. Suma binaria:

```plaintext
  0000000011110101
+ 0000000001011011
------------------
  0000000101010000
```

#### 3. Interpretación en decimal:

| Bit Posición | 15 | 14 | 13 | 12 | 11 | 10 | 9 | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
| :----------- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| Dígito binario | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 0 |
| Valor decimal  | 2<sup>15</sup>=32768 | 2<sup>14</sup>=16384 | 2<sup>13</sup>=8192 | 2<sup>12</sup>=4096 | 2<sup>11</sup>=2048 | 2<sup>10</sup>=1024 | 2<sup>9</sup>=512 | 2<sup>8</sup>=256 | 2<sup>7</sup>=128 | 2<sup>6</sup>=64 | 2<sup>5</sup>=32 | 2<sup>4</sup>=16 | 2<sup>3</sup>=8 | 2<sup>2</sup>=4 | 2<sup>1</sup>=2 | 2<sup>0</sup>=1 |
| Cálculo  | 0*32768 | 0*16384 | 0*8192 | 0*4096 | 0*2048 | 0*1024 | 0*512 | 1*256 | 0*128 | 1*64 | 0*32 | 1*16 | 0*8 | 0*4 | 0*2 | 0*1 |

De esta forma: `0000000101010000` → `256 + 64 + 16 = 336`

### c) 10101011 + 00011011, en notación de 1 byte con signo

#### 1. Suma binaria:

```plaintext
  10101011
+ 00011011
----------
  11000110
```

#### 2. Interpretación en decimal:

El resultado de la suma es `11000110`. Como el bit más significativo es `1`, el resultado es un número negativo:
* Para encontrar la magnitud del número negativo, tomamos el complemento a dos del resultado:
  
  **1. Invertimos:** `11000110` → `00111001`
  
  **2. Sumamos 1:** `00111001` → `00111010`

  | Bit Posición | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
  | :----------- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
  | Dígito binario | 0 | 0 | 1 | 1 | 1 | 0 | 1 | 0 |
  | Valor decimal  | 2<sup>7</sup>=128 | 2<sup>6</sup>=64 | 2<sup>5</sup>=32 | 2<sup>4</sup>=16 | 2<sup>3</sup>=8 | 2<sup>2</sup>=4 | 2<sup>1</sup>=2 | 2<sup>0</sup>=1  |
  | Cálculo  | 0 * 128 | 0 * 64 | 1 * 32 | 1 * 16 | 1 * 8 | 0 * 4 | 1 * 2 | 0 * 1 |

  De esta forma: `00111010` → `32 + 16 + 8 + 2 = 58`

* Considerando el signo negativo del bit más significativo, `11000110` → `-58`

---

## 2. Resta en binario

Realiza las siguientes operaciones binarias, describiendo el proceso y mostrando claramente el resultado:

### a) 10101 - 11011, en notación de 1 byte con signo

#### 1. Convertir a 8-bits y pasar el sustraendo a su complemento a dos:

* `10101` → `00010101`

* `11011` → `00011011`

  1. **Invertimos:** `00011011` → `11100100`
  
  2. **Sumamos 1:** `11100100` → `11100101`

#### 2. Suma binaria:

```plaintext
  00010101
+ 11100101
----------
  11111010
```

#### 3. Interpretación en decimal:

El resultado de la resta es `11111010`. Como el bit más significativo es `1`, el resultado es un número negativo:
* Para encontrar la magnitud del número negativo, tomamos el complemento a dos del resultado:
  
  **1. Invertimos:** `11111010` → `00000101`
  
  **2. Sumamos 1:** `00111001` → `00000110`

  | Bit Posición | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
  | :----------- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
  | Dígito binario | 0 | 0 | 0 | 0 | 0 | 1 | 1 | 0 |
  | Valor decimal  | 2<sup>7</sup>=128 | 2<sup>6</sup>=64 | 2<sup>5</sup>=32 | 2<sup>4</sup>=16 | 2<sup>3</sup>=8 | 2<sup>2</sup>=4 | 2<sup>1</sup>=2 | 2<sup>0</sup>=1  |
  | Cálculo  | 0 * 128 | 0 * 64 | 0 * 32 | 0 * 16 | 0 * 8 | 1 * 4 | 1 * 2 | 0 * 1 |

  De esta forma: `00000110` → `4 + 2 = 6`

* Considerando el signo negativo del bit más significativo, `11111010` → `-6`

### b) 11110101 - 1011011, en notación de 2 bytes sin signo

#### 1. Convertir a 16-bits y pasar el sustraendo a su complemento a dos:

* `11110101` → `0000000011110101`

* `1011011` → `0000000001011011`

  1. **Invertimos:** `0000000001011011` → `1111111110100100`
  
  2. **Sumamos 1:** `1111111110100100` → `1111111110100101`

#### 2. Suma binaria:

```plaintext
  0000000011110101
+ 1111111110100101
------------------
1 0000000010011010
```
Tenemos un Carry-out de `1`. Como estamos trabajando sin signo, lo descartamos considerando solo `0000000010011010`.

#### 3. Interpretación en decimal:

| Bit Posición | 15 | 14 | 13 | 12 | 11 | 10 | 9 | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
| :----------- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| Dígito binario | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 1 | 1 | 0 | 1 | 0 |
| Valor decimal  | 2<sup>15</sup>=32768 | 2<sup>14</sup>=16384 | 2<sup>13</sup>=8192 | 2<sup>12</sup>=4096 | 2<sup>11</sup>=2048 | 2<sup>10</sup>=1024 | 2<sup>9</sup>=512 | 2<sup>8</sup>=256 | 2<sup>7</sup>=128 | 2<sup>6</sup>=64 | 2<sup>5</sup>=32 | 2<sup>4</sup>=16 | 2<sup>3</sup>=8 | 2<sup>2</sup>=4 | 2<sup>1</sup>=2 | 2<sup>0</sup>=1 |
| Cálculo  | 0*32768| 0*16384| 0*8192| 0*4096| 0*2048| 0*1024| 0*512| 0*256| 1*128| 0*64| 0*32| 1*16| 1*8| 0*4| 1*2| 0*1|

De esta forma: `0000000010011010` → `128 + 16 + 8 + 2 = 154`

### c) 10101011 - 00011011, en notación de 1 byte con signo

#### 1. Pasar el sustraendo a su complemento a dos:

1. **Invertimos:** `00011011` → `11100100`
  
2. **Sumamos 1:** `11100100` → `11100101`

#### 2. Suma binaria:

```plaintext
  10101011
+ 11100101
----------
1 10010000
```

Tenemos un Carry-out de `1`. Como estamos trabajando con ambos números en complemento a dos, lo descartamos considerando solo `10010000`.

#### 3. Interpretación en decimal:

El resultado de la resta es `10010000`. Como el bit más significativo es `1`, el resultado es un número negativo:
* Para encontrar la magnitud del número negativo, tomamos el complemento a dos del resultado:
  
  **1. Invertimos:** `10010000` → `01101111`
  
  **2. Sumamos 1:** `01101111` → `01110000`

  | Bit Posición | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |
  | :----------- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
  | Dígito binario | 0 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
  | Valor decimal  | 2<sup>7</sup>=128 | 2<sup>6</sup>=64 | 2<sup>5</sup>=32 | 2<sup>4</sup>=16 | 2<sup>3</sup>=8 | 2<sup>2</sup>=4 | 2<sup>1</sup>=2 | 2<sup>0</sup>=1  |
  | Cálculo  | 0 * 128 | 1 * 64 | 1 * 32 | 1 * 16 | 0 * 8 | 0 * 4 | 0 * 2 | 0 * 1 |

  De esta forma: `01110000` → `64 + 32 + 16 = 112`

* Considerando el signo negativo del bit más significativo, `10010000` → `-112`

---

## 3. Álgebra Booleana

Resuelva los siguientes ejercicios aplicando teoremas y operaciones de álgebra de Boole, indicando en casa paso qué usó para componer/descomponer la expresión mostrada.

### a) Simplificar la siguiente expresión: (𝐴 + 𝐴𝐵) ⋅ (𝐵 + 𝐶)

1. Distribución:

    `(𝐴 + 𝐴𝐵) ⋅ (𝐵 + 𝐶)` → `((𝐴 + 𝐴𝐵) ⋅ 𝐵) + ((𝐴 + 𝐴𝐵) ⋅ 𝐶)`

2. Distribución (2):

    `((𝐴 + 𝐴𝐵) ⋅ 𝐵) + ((𝐴 + 𝐴𝐵) ⋅ 𝐶)` → `(𝐴𝐵 + 𝐴𝐵²) + (𝐴𝐶 + 𝐴𝐵𝐶)`

3. Simplificación por álgebra booleana:

    `(𝐴𝐵 + 𝐴𝐵²) + (𝐴𝐶 + 𝐴𝐵𝐶)` → `𝐴𝐵 + 𝐴𝐵 + 𝐴𝐶 + 𝐴𝐵𝐶`

    `𝐴𝐵 + 𝐴𝐵 + 𝐴𝐶 + 𝐴𝐵𝐶` → `𝐴𝐵 + 𝐴𝐶 + 𝐴𝐵𝐶`

4. Factorización de 𝐴:

    `𝐴𝐵 + 𝐴𝐶 + 𝐴𝐵𝐶` → `𝐴 ⋅ (𝐵 + 𝐶 + 𝐵𝐶)`

5. Absorción de 𝐵𝐶:

    `𝐴 ⋅ (𝐵 + 𝐶 + 𝐵𝐶)` → `𝐴 ⋅ (𝐵 + 𝐶)`

#### Resultado Final: `𝐴 ⋅ (𝐵 + 𝐶)`

### b) Crear la tabla de verdad de la siguiente expresión: 𝐹(𝐴, 𝐵, 𝐶) = (𝐴 ⋅ 𝐵) + (~𝐴 ⋅ 𝐶)

| 𝐴 | 𝐵 | 𝐶 | 𝐴 ⋅ 𝐵 | ~𝐴 | ~𝐴 ⋅ 𝐶 | (𝐴 ⋅ 𝐵) + (~𝐴 ⋅ 𝐶) |
|:-:|:-:|:-:|:-----:|:--:|:-----:|:-----------------:|
| 0 | 0 | 0 |   0   |  1 |   0   |         0         |
| 0 | 0 | 1 |   0   |  1 |   1   |         1         |
| 0 | 1 | 0 |   0   |  1 |   0   |         0         |
| 0 | 1 | 1 |   0   |  1 |   1   |         1         |
| 1 | 0 | 0 |   0   |  0 |   0   |         0         |
| 1 | 0 | 1 |   0   |  0 |   0   |         0         |
| 1 | 1 | 0 |   1   |  0 |   0   |         1         |
| 1 | 1 | 1 |   1   |  0 |   0   |         1         |

### c) Cree el circuito lógico para la expresión del ejercicio (b)

```plaintext
     +-------+
     |       |
 𝐴 --+  AND  +--> (𝐴 ⋅ 𝐵) ---+
     |       |               |
     +-------+               |
                             |
     +-------+               |
     |       |               |
 𝐴 --+  NOT  +--> (~𝐴) --+   ++------+
     |       |           |    |      |
     +-------+           |    |      |
                         |    |      |
  +----------------------+    |  OR  |
  |                           |      |
  |  +-------+                |      |
  |  |       |                |      |
 ~𝐴 -+       +--> (~𝐴 ⋅ 𝐶) ---+      +--> (𝐴 ⋅ 𝐵) + (~𝐴 ⋅ 𝐶)
     |  AND  |                |      |
 𝐶 --+       |                +------+
     |       |
     +-------+
```
---