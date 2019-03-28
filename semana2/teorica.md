# Teorica 27/3
# Guia 4
## Resolucion de modelos de programacion lineal continua
### Problema de helados

#### Variables
> X<sub>1</sub>: Cantidad fabricada de helados de agua\
X<sub>2</sub>: Cantidad fabricada de helados de crema

#### Restricciones
> Azucar) 2 X<sub>1</sub> + 2 X<sub>2</sub> <= 600\
Crema) 0 X<sub>1</sub> + 4 X<sub>2</sub> <= 600\
Almidon) 2 X<sub>1</sub> + 4 X<sub>2</sub> <= 801

#### Funcional
> Z<sub>max</sub> = 8 X<sub>1</sub> + 10 X<sub>2</sub>

### Simplex
* Para poder resolver con el metodo de simplex se pide:
    * Todas las variables enten en el primer miembro.
    * Todas las restricciones sean igualdades.
        * Para lograr esto se agregan variables slack en cada restriccion.

#### Ejemplo para el ejercicio:
>Azucar) 2 X<sub>1</sub> + 2 X<sub>2</sub> + *X<sub>3</sub>* = 600\
Crema) 0 X<sub>1</sub> + 4 X<sub>2</sub> + *X<sub>4</sub>* = 600\
Almidon) 2 X<sub>1</sub> + 4 X<sub>2</sub> + *X<sub>5</sub>* = 801

*X<sub>3</sub>*, *X<sub>4</sub>*, *X<sub>5</sub>*: Sobrantes de azucar, crema y almidon respectivamente (*NO* van en el funcional).

##### Sistema de Matriz
|   |   |   |   |   | * |    | = |     |
|---|---|---|---|---|---|----|---|-----|
| 2 | 2 | 1 | 0 | 0 |   | X1 |   | 600 |
| 0 | 4 | 0 | 1 | 0 |   | X2 |   | 600 |
| 2 | 4 | 0 | 0 | 1 |   | X3 |   | 801 |
|   |   |   |   |   |   | X4 |   |     |
|   |   |   |   |   |   | X5 |   |     |

##### Para resolver
> C: C<sub>j</sub> variables mayores a 0 (_los del funcional_)\
X: Nombre de variables mayores a 0\
B: Valor variables mayores a 0

|   |    |       |    |                   8                   |   10   |       |       |       |
|:-:|:--:|:-----:|:--:|:-------------------------------------:|:------:|:-----:|:-----:|:-----:|
| C |  X |   B   | \| |                   A1                  |   A2   |   A3  |   A4  |  AA5  |
| 0 | X3 |  600  | \| |                   2                   |    2   |   1   |   0   |   0   |
| 0 | X4 |  600  | \| |                   0                   |    4   |   0   |   1   |   0   |
| 0 | X5 |  801  | \| |                   2                   |    4   |   0   |   0   |   1   |
|   |    | Z=CxB | \| | 0 - 8 (Z<sub>1</sub> - C<sub>1</sub>) | 0 - 10 | 0 - 0 | 0 - 0 | 0 - 0 |

> * Z<sub>1</sub> = 0x2 + 0x0 + 0x2 = 0\
> * Para algun (Z<sub>i</sub> - C<sub>i</sub>) que es negativo se puede afirmar que hay una solucion mejor cuando el problema es de maximo. (_Son candidatas a entrar en la base_)\
> * Cuando todos los (Z<sub>i</sub> - C<sub>i</sub>) son mayores a 0 llegamos al optimo.

* Entra A1
    * Para saber quien sale:
        * > Calculo Thetas: B / A y elijo al menor (_sale X3_)

|   |    |       |    |                   8                   |   10   |       |       |       |                                  |
|:-:|:--:|:-----:|:--:|:-------------------------------------:|:------:|:-----:|:-----:|:-----:|:--------------------------------:|
| C |  X |   B   | \| |                   A1                  |   A2   |   A3  |   A4  |  AA5  |          Theta ( B / A )         |
| 0 | X3 |  600  | \| |                   2                   |    2   |   1   |   0   |   0   |              600 / 2             |
| 0 | X4 |  600  | \| |                   0                   |    4   |   0   |   1   |   0   | - (por dividir con 0 o negativo) |
| 0 | X5 |  801  | \| |                   2                   |    4   |   0   |   0   |   1   |              801 / 2             |
|   |    | Z=CxB=0 | \| | 0 - 8 (Z<sub>1</sub> - C<sub>1</sub>) | 0 - 10 | 0 - 0 | 0 - 0 | 0 - 0 |                                  |

* Siguiente iteracion
    * Divido la fila del pivote por el pivote (elemento en la interseccion de fila de la que sale con la columna de la que entra)
    * B<sub>2</sub> = 600 - (B<sub>1</sub> A1<sub>2</sub>) / pivote = 600
    * B<sub>3</sub> = 801 - (B<sub>1</sub> A1<sub>3</sub>) / pivote = 600
    * Z<sub>1</sub> = 8x1 + 0x0 + 0x0 = 8
    * // Agregar lo de fila de X5

|   |    |                     |    |   8   |   10   |       |    |     |                 |
|:-:|:--:|:-------------------:|:--:|:-----:|:------:|:-----:|:--:|:---:|:---------------:|
| C |  X |          B          | \| |   A1  |   A2   |   A3  | A4 | AA5 | Theta ( B / A ) |
| 8 | X1 |         300         | \| |   1   |    1   |  1/2  |  0 |  0  |      300/1      |
| 0 | X4 | 600 (B<sub>2</sub>) | \| |   0   |    4   |   0   |  1 |  0  |      600/4      |
| 0 | X5 |  201 (B<sub>3</sub>) | \| |   0   |    2   |   -1  |  0 |  1  |      201/2      |
|   |    |        Z=2400       | \| | 8 - 8 | 8 - 10 | 4 - 0 |  0 |  0  |                 |

* Entra X2 sale X5
* Siguiente iteracion

|    |    |        |    |  8 | 10 |      |    |      |                 |
|:--:|:--:|:------:|:--:|:--:|:--:|:----:|:--:|:----:|:---------------:|
|  C |  X |    B   | \| | A1 | A2 |  A3  | A4 |  AA5 | Theta ( B / A ) |
|  8 | X1 |  199,5 | \| |  1 |  0 |   1  |  0 | -1/2 |                 |
|  0 | X4 |   198  | \| |  0 |  0 |   2  |  1 |  -2  |                 |
| 10 | X2 |  100,5 | \| |  0 |  1 | -1/2 |  0 |  1/2 |                 |
|    |    | Z=2601 | \| |  0 |  0 |   3  |  0 |   1  |                 |

*Es la optima*