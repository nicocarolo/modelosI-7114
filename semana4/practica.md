# Practica 9/4

## Ejercicio 4.2
- Se transforma a igualdades el sistema de inecuaciones agregando variables (slack) para equilibrar el cambio a =.
- La primer tabla es cuando X1 y X2 son 0.

|   |    |        |    |  10 |  3 |    |    |    |                 |
|:-:|:--:|:------:|:--:|:---:|:--:|:--:|----|----|:---------------:|
| C |  X |    B   | \| |  A1 | A2 | A3 | A4 | A5 | Theta ( B / A ) |
| 0 | X3 |    2   | \| |  -2 |  1 |  1 | 0  | 0  |        -1       |
| 0 | X4 |    2   | \| |  1  | -1 |  0 | 1  | 0  |        2        |
| 0 | X5 |    5   | \| |  1  |  1 |  0 | 0  | 1  |        5        |
|   |    |   Z=0  | \| | -10 | -3 |  3 |    |    |                 |

- X4 sale por 'menor valor positivo'.
- X1 candidato a entrar (Obs: Entra con su valor de Theta).
- Pivote es A1 con X4 = 1.

|    |    |      |    | 10 |  3  |    |    |    |                 |
|:--:|:--:|:----:|:--:|:--:|:---:|:--:|----|----|:---------------:|
|  C |  X |   B  | \| | A1 |  A2 | A3 | A4 | A5 | Theta ( B / A ) |
|  0 | X3 |   6  | \| |  0 |  -1 |  1 | 2  | 0  |        -6       |
| 10 | X1 |   2  | \| |  1 |  -1 |  0 | 1  | 0  |        -2       |
|  0 | X5 |   3  | \| |  0 |  2  |  0 | 0  | 1  |       1,5       |
|    |    | Z=20 | \| |  0 | -13 |  0 | 10 | 0  |                 |

- X5 sale.
- X2 candidato a entrar.
- Pivote es A2 con X5 = 2.

|    |    |        |    | 10 |  3 |    |      |     |                 |
|:--:|:--:|:------:|:--:|:--:|:--:|:--:|:----:|:---:|:---------------:|
|  C |  X |    B   | \| | A1 | A2 | A3 |  A4  |  A5 | Theta ( B / A ) |
|  0 | X3 |   7,5  | \| |  0 |  0 |  1 |  1,5 | 0,5 |        -6       |
| 10 | X1 |   3,5  | \| |  1 |  0 |  0 |  0,5 | 0,5 |        -2       |
|  3 | X2 |   1,5  | \| |  0 |  1 |  0 | -0,5 | 0,5 |       1,5       |
|    |    | Z=39,5 | \| |  0 |  0 |  0 |  3,5 | 6,5 |                 |

- Llegamos al optimo porque la todos los Z<sub>j</sub> - C<sub>j</sub> son mayores iguales a 0

## Ejercicio 4.13
- Cuando es minimo se agrega un slack restando y se suma (por ser problema de minimo) una constante M multiplicando a variable artificial (si fuera un problema de maximo se deberia restar M).

|   |    |        |    |  1  |   3  |    |    |    |    |                 |
|:-:|:--:|:------:|:--:|:---:|:----:|:--:|:--:|:--:|:--:|:---------------:|
| C |  X |    B   | \| |  A1 |  A2  | A3 | A4 | A5 | A6 | Theta ( B / A ) |
| M |  M |    4   | \| |  1  |   2  | -1 |  0 |  0 |  1 |        2        |
| 0 | X4 |    2   | \| |  1  |   0  |  0 |  1 |  0 |  0 |        -        |
| 0 | X5 |    5   | \| |  1  |   1  |  0 |  0 |  1 |  0 |        5        |
|   |    | Z=39,5 | \| | M-1 | 2M-3 | -M |  0 |  0 |  M |                 |

- Sale M.
- Entra X2.

|   |    |        |    |  1  |  3 |      |    |    |      |                 |
|:-:|:--:|:------:|:--:|:---:|:--:|:----:|:--:|:--:|:----:|:---------------:|
| C |  X |    B   | \| |  A1 | A2 |  A3  | A4 | A5 |  A6  | Theta ( B / A ) |
| 3 | X2 |    2   | \| | 1/2 |  1 | -1/2 |  0 |  0 |  1/2 |        4        |
| 0 | X4 |    2   | \| |  1  |  0 |   0  |  1 |  0 |   0  |        2        |
| 0 | X5 |    3   | \| | 1/2 |  0 |  1/2 |  0 |  1 | -1/2 |        6        |
|   |    | Z=39,5 | \| | 1/2 |  0 | -3/2 |  0 |  0 |  3/2 |                 |

- Sale X4.
- Entra X1.

|   |    |        |    |  1 |  3 |      |      |    |        |                 |
|:-:|:--:|:------:|:--:|:--:|:--:|:----:|:----:|:--:|:------:|:---------------:|
| C |  X |    B   | \| | A1 | A2 |  A3  |  A4  | A5 |   A6   | Theta ( B / A ) |
| 3 | X2 |    1   | \| |  0 |  1 | -1/2 | -1/2 |  0 |   1/2  |        4        |
| 1 | X1 |    2   | \| |  1 |  0 |   0  |   1  |  0 |    0   |        2        |
| 0 | X5 |    2   | \| |  0 |  0 |  1/2 | -1/2 |  1 |  -1/2  |        6        |
|   |    | Z=39,5 | \| |  0 |  0 | -3/2 | -1/2 |  0 | 3/2 -M |                 |

Tabla óptima por que todas Z<sub>j</sub> - C<sub>j</sub> son menores iguales a 0

## Ejercicio 2.17
### Objetivo
### Hipotesis
- Si no trabajo el dia anterior no mejora eficiencia.
- No hay desperdicio de tiempo.

### Variables
> E<sub>i</sub>: Empleados de dia I.\
E<sub>i,j</sub>: Empleados que hacen i el dia j.\
E<sub>i,j => k</sub>: Empleados que hacen i el dia j y pasan a ser k.\
### Modelo
- Viernes
> E<sub>V</sub>  = E<sub>R,V</sub> + E<sub>0,V</sub> + E<sub>M,V</sub> + E<sub>NT,V</sub> // Idem Sabado sin ordenar, Idem Domingo. (Empleados de viernes: son los que reponen, ....)\
E<sub>V</sub>  = 18 //Idem sabado, idem domingo.\
15 E<sub>R,V</sub> 8 => A //Idem para ordenar y marcar el viernes.

- Entrada Reponen Sabado
> E<sub>R,V</sub> = E<sub>R,V => R</sub> + E<sub>R,V => M</sub> + E<sub>R,V => NT</sub>\

- Sabado Reponen (Idem Sabado Marcar)
> E<sub>R,S</sub> = E<sub>R,S Normal</sub> + E<sub>R,S Eficiente</sub>\
E<sub>R,S Normal</sub> = E<sub>R,V => R</sub>  + E<sub>NT,V => R</sub>\
E<sub>R,S Eficiente</sub> = E<sub>O,V => R</sub> + E<sub>M,V => R</sub> // linkeo dia anterior (viernes) que pasan a reponer.\
15 . 8 . E<sub>R,S Normal</sub> + 1,1 . 15 . 8 E<sub>R,S Eficiente</sub> => 500

- Salida Reponen Sabado
> E<sub>R,S</sub> = E<sub>R,S => R</sub> + E<sub>R,S => M</sub> + E<sub>R,S => NT</sub> +  E<sub>R,S => O</sub>

## Ejercicio 3.3
> a) Y<sub>2</sub> => Y<sub>1</sub>\
b) MES - 12 Y<sub>1</sub> => 0\
MES - 12 Y<sub>1</sub> <= 11\
c) Y<sub>1</sub> <= Y<sub>2</sub> + Y<sub>3</sub> + Y<sub>4</sub> <= 3 Y<sub>1</sub>\
d) 2 Y<sub>1</sub> <= Y<sub>2</sub> + Y<sub>3</sub> <= 1 + Y<sub>1</sub>\
e)  Y<sub>1</sub> + Y<sub>2</sub> = 1\
f) creo Y<sub>1</sub> que es 1 si E<sub>1</sub> esta entre 5 y 7\
1 <= E<sub>1</sub> <= 3 + M Y<sub>1</sub>\
-M (1 - Y<sub>1</sub>) + 5 <= E<sub>1</sub> <= 7\
Haciendolo con rangos:
1 (1 - Y<sub>1</sub>) + 5 Y<sub>1</sub> <= E<sub>1</sub> <= 3 (1 - Y<sub>1</sub>) + 7 Y<sub>1</sub>\
g) C<sub>1</sub> => 10 + m\
h) E<sub>1</sub> = 1 + 2 E<sub>2</sub>\
i) E<sub>1</sub> = 4 Y<sub>1</sub> + 9 Y<sub>2</sub> + 16 Y<sub>3</sub>\
Y<sub>1</sub> + Y<sub>2</sub> + Y<sub>3</sub> = 1\
j) 75 - 25 Y<sub>1</sub> + m <= C<sub>1</sub>\
k) E<sub>1</sub> => 101 Y<sub>1</sub>\
E<sub>1</sub> <= 79 Y<sub>2</sub> + M Y<sub>1</sub>\
Y<sub>1</sub> + Y<sub>2</sub> = 1

## Ejercicio 3.4
### Objetivo
Determinar el personal a seleccionar según restricciones para minimizar costo de reemplazo en un periodo determinado.

### Hipotesis
- Todas las personas estan disponibles para sumarse al proyecto.
- Ninguna persona cambia su caracter.
- No se generan nuevos conflictos.
- El protegido solo puede estar en el grupo si esta en el mentor.

### Variables
> Y<sub>i</sub>: Si se toma a la persona i para el proyecto {i: 1..12}.\
> P<sub>c</sub>: Cantidad de contadores en el equipo.\
> P<sub>q</sub>: Cantidad de quimicos en el equipo.\
> P<sub>i</sub>: Cantidad de ingenieros en el equipo.\
> A: Si hay partidarios del trabajo en grupo en el equipo.\
> PTG: Si hay autoritarios en el equipo.\
> B: Si hay 2 benevolentes o mas en el equipo.\
> Y<sub>vs</sub>: Si vidal y smith estan en el equipo.

### Modelo
> Tamaño Grupo) Sumatoria(Y<sub>i</sub>) = 6\

#### Antagonicas
> Y<sub>2</sub> + Y<sub>11</sub> ≤ 1\
> Y<sub>3</sub> + Y<sub>4</sub> ≤ 1

#### Vidal y Smith
> 2 Y<sub>vs</sub> ≤ Y<sub>7</sub> + Y<sub>11</sub> ≤ 1 + Y<sub>vs</sub>

#### Limite contadores
> P<sub>c</sub> ≤ 3 + Y<sub>vs</sub>

#### Protegido y mentor
> Y<sub>4</sub> ≥ Y<sub>6</sub>

#### Caracteres antagonicos
> A + PTG ≤ 1</sub>

#### Contadores
> Y<sub>1</sub> + Y<sub>4</sub> + Y<sub>5</sub> + Y<sub>8</sub>+ Y<sub>11</sub> = P<sub>c</sub>

#### Quimicos
> Y<sub>2</sub> + Y<sub>7</sub> = P<sub>q</sub>

#### Profesiones minimas
> P<sub>q</sub> ≥ 1\
> P<sub>i</sub> ≥ 1\
> P<sub>c</sub> ≥ 2\

#### Autoritarios
> A ≤ Y<sub>1</sub> + Y<sub>5</sub> + Y<sub>7</sub> ≤ 3 A

#### Hay PTG
> PTG ≤ Y<sub>2</sub> + Y<sub>6</sub> ≤ 2 PTG

#### 2 o mas benevolentes
> 2 B ≤ Y<sub>4</sub> + Y<sub>8</sub> + Y<sub>11</sub> + Y<sub>12</sub> ≤ 3 B + 1

### Funcional
> Z<sub>min</sub> = Sumatoria(Costo - Reemplazo Y<sub>i</sub>) - 100 B\
> _Costo y Reemplazo son constantes_

## OBSERVACIONES PARA LA GUIA:
-   4.8 tiene punto degenerado.
-   4.10 es poliedro abierto.
-   4.12 es incompatible.