# Teorica 3/4
## Modelos de programacion lineal ENTERA

### Siguiendo con ejercicio de clase anterior
#### Si se modifican los costos de las maquinas, siendo posible:
-   Si la maquina funciona entre 1 y 30 hs, se pagara $1 por hora.
    -   Definimos Y<sub>hs1</sub> _(Y<sub>hs1</sub> = 1 si se cumple)_
-   Si la maquina funciona mas de 30 hs pero menos de 60 hs, se pagara $0,70 por hora.
    -   Definimos Y<sub>hs2</sub> _(Idem Y<sub>hs1</sub>)_
-   Si la maquina funciona entre 60 hs, se pagara $0,50 por hora.
    -   Definimos Y<sub>hs3</sub> _(Idem Y<sub>hs1</sub>)_

Por exclusividad de los rangos:
> Y<sub>hs1</sub> + Y<sub>hs2</sub> + Y<sub>hs3</sub> ≤ 1\

Para cada rango (funcion de n valores posibles):
> Y<sub>hs1</sub> + 30,01 Y<sub>hs2</sub> + 60 Y<sub>hs3</sub> ≤ HS ≤ 30 <sub>hs1</sub> + 59,99 Y<sub>hs2</sub> + 150 Y<sub>hs3</sub>

Para calcular los costos segun en que rango estamos, asi como estamos deberiamos multiplicar HS con alguna de las Y<sub>hs</sub>: **PROHIBIDO**
- Para eso definimos:
  - H<sub>s1</sub>: Cantidad de horas mantenimiento si se usan entre 1 y 30 hs.
  - H<sub>s2</sub>: Cantidad de horas mantenimiento si se usan entre 30,01 hs y 50,9 hs.
  - H<sub>s3</sub>: Cantidad de horas mantenimiento si se usan entre 60 y 150 hs.

Definimos HS:
> HS = H<sub>s1</sub> + H<sub>s2</sub> + H<sub>s3</sub>

Corregimos la restriccion para cada rango, haciendo una restriccion para cada H<sub>s</sub>:
> Y<sub>hs1</sub> ≤ H<sub>s1</sub> ≤ 30 <sub>hs1</sub>\
> 30,01 Y<sub>hs2</sub> ≤ H<sub>s2</sub> ≤ 59,99 Y<sub>hs2</sub>\
> 60 Y<sub>hs3</sub> ≤ H<sub>s3</sub> ≤ 150 Y<sub>hs3</sub>

**En definitiva, la solucion seria:**
> Exclusividad de rangos) Y<sub>hs1</sub> + Y<sub>hs2</sub> + Y<sub>hs3</sub> ≤ 1\
> Composicion de HS) HS = H<sub>s1</sub> + H<sub>s2</sub> + H<sub>s3</sub>\
> 1er Rango) Y<sub>hs1</sub> ≤ H<sub>s1</sub> ≤ 30 <sub>hs1</sub>\
> 2do Rango) 30,01 Y<sub>hs2</sub> ≤ H<sub>s2</sub> ≤ 59,99 Y<sub>hs2</sub>\
> 3er Rango) 60 Y<sub>hs3</sub> ≤ H<sub>s3</sub> ≤ 150 Y<sub>hs3</sub>

> Funcional) Z<sub>max</sub> = ... + Y<sub>Ahorro</sub> - 1 H<sub>s1</sub> - 0,7 H<sub>s2</sub> - 0,5 H<sub>s3</sub>

#### Ahora se modifican los precios de venta del producto 2 segun cantidad, siendo posible:
- Hasta que vendamos 10 unidades => precio = $18.
- Hasta que vendamos 7 despues de las primeras 10 unidades => precio = $20.
- A partir de 17 unidades => precio = $24.
  
Por ejemplo, si vendemos 25 unidades: cobraremos 10 a $18, 7 a $20 y 8 a $24.

En la clase anterior definimos X<sub>2</sub>, ahora la abrimos:
- X<sub>2a</sub>: Primeras 10 unidades.
- X<sub>2b</sub>: Unidades por encima de 10 y debajo de 17.
- X<sub>2c</sub> Unidades por encima de 17.
> X<sub>2</sub> = X<sub>2a</sub> + X<sub>2b</sub> + X<sub>2c</sub>

En el funcional, lo que busco, es agregar (sacando 18 X<sub>2</sub> de la semana pasada):
> Funcional) Z<sub>max</sub> = ... + 18 X<sub>2a</sub> + 20 X<sub>2b</sub> + 24 X<sub>2c</sub> + ....

Ahora necesitamos variables binarias para avisarle al modelo que para hacer unidades de X<sub>2b</sub> primero debe llenar el cupo de X<sub>2a</sub> (Idem para X<sub>2c</sub>).
Definimos:
- Y<sup>'</sup>: 1 si X<sub>2a</sub> = 10
- Y<sup>''</sup>: 1 si X<sub>2b</sub> = 7

El limite de X<sub>2a</sub> es 10 y cuando Y<sup>'</sup> = 1, X<sub>2a</sub> esta obligada a ser 10.
> 10 Y<sup>'</sup> ≤ X<sub>2a</sub> ≤ 10

Idem con rangos de X<sub>2b</sub> y X<sub>2c</sub>
> 7 Y<sup>''</sup> ≤ X<sub>2b</sub> ≤ 10 Y<sup>'</sup>\
> X<sub>2c</sub> ≤ M Y<sup>''</sup>

### Problema del viajante
```Un viajante tiene que partir de su casa, visitar todos los lugares y volver a su casa.```

Se define:
- Y<sub>ij</sub>: 1 si el viajante hace el tramo entre la ciudad i y la j.

Funcional
> Z<sub>min</sub> = $\sum^n_i\sum^n_j$ C<sub>ij</sub> Y<sub>ij</sub>

Siendo C<sub>ij</sub> constantes de costo

Si quiero llegar al nodo C una sola vez *(Idem para todas las ciudades)*:
> $\sum^n_i$ Y<sub>iC</sub> = 1

Si quiero salir del nodo C una sola vez *(Idem para todas las ciudades)*:
> $\sum^n_j$ Y<sub>Cj</sub> = 1 

Faltan agregar condiciones para que busque caminos conexos, porque puede pasar que encuentre una solucion con dos caminos separados.

Se le da un orden a cada nodo al que se llega, pudiendo solo el proxima ser posterior.
> U<sub>i</sub> - U<sub>j</sub> + N ≤ N - 1 // siendo N = # de nodos