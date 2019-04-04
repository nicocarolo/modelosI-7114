# Teorica 3/4
## Modelos de programacion lineal ENTERA

### Variables enteras
- enteras discretas
- bivalentes o binarias

### Ejemplo Costo Fijo
Tenemos que decidir en base a 6 productos con sus correspondientes costos de publicidad, cuales 3 lanzamos.

#### Definimos
> Y<sub>i</sub>:
> - 1 *si* se lanza el producto i.
> - 2 *si no* se lanza el producto i.

> Minmo de productos) Y<sub>1</sub> + Y<sub>2</sub> + Y<sub>3</sub> + Y<sub>4</sub> + Y<sub>5</sub> + Y<sub>6</sub> >= 3

#### Funcional
> Funcional) Z<sub>Min</sub> = 200 Y<sub>1</sub> + 200 150 <sub>2</sub> + 120 Y<sub>3</sub> + 140 Y<sub>4</sub> + 90 Y<sub>5</sub> + 115 Y<sub>6</sub>

### Ejemplo Relaciones Logicas
Siguiendo con ejercicio anterior

*Que ocurriria si nos obligan a que si lanzamos el producto 5 o el 6, se debe lanzar el producto 1?*

#### Tabla de verdad
|Y<sub>5</sub>|Y<sub>6</sub>|Y<sub>1</sub>|
|---|---|---|
| 0 | 0 | 0 ó 1 |
| 1 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 1 | 1 |

##### 2 opciones
- Primera
> Relacion) 2 Y<sub>1</sub> => Y<sub>5</sub> + Y<sub>6</sub>
- Segunda
> Relacion) Y<sub>1</sub> => Y<sub>5</sub>\
Relacion) Y<sub>1</sub> => Y<sub>6</sub>

*Que ocurriria si por promocion si lanzaramos el producto 3 y el 4, se produce un ahorro de $100 en publicidad?*

#### Definimos
> Y<sub>Ahorro</sub>:
> - 1 *si* se lanza el producto 3 y 4.
> - 2 *si no* se lanza el producto 3 y 4.

#### Tabla de verdad
|Y<sub>3</sub>|Y<sub>4</sub>|Y<sub>Ahorro</sub>|
|---|---|---|
| 0 | 0 | 0 |
| 1 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 1 | 1 |

##### Agregamos
> Relacion) 2 Y<sub>Ahorro</sub> <= Y<sub>3</sub> + Y<sub>4</sub>\
Relacion) Y<sub>Ahorro</sub> + 1 => Y<sub>3</sub> + Y<sub>4</sub>

##### Funcional
> Funcional) Z<sub>Min</sub> = 200 Y<sub>1</sub> + 150 Y<sub>2</sub> + 120 Y<sub>3</sub> + 140 Y<sub>4</sub> + 90 Y<sub>5</sub> + 115 Y<sub>6</sub> - 100 Y<sub>Ahorro</sub>

##### AND Forma General
> n Y<sub>AND</sub> <= Sumatoria<sup>n</sup>(Y<sub>i</sub>) <= + Y<sub>AND</sub> + (n - 1)\

### Si agregamos el proceso productivo al ejemplo
#### Cambiamos
> Y<sub>i</sub>:
> - 1 *si* X<sub>i</sub> > 0.
> - 2 *si* X<sub>i</sub> = 0.

>Relacion Y con X) m Y<sub>i</sub> <= M X<sub>i</sub> <= Y<sub>i</sub>


> Materia prima) 2 X<sub>1</sub> + 3 X<sub>2</sub> + 5 X<sub>3</sub> + X<sub>4</sub> + 2 X<sub>5</sub> + 3 X<sub>6</sub> <= 50\
Materia de Obra) 5 X<sub>1</sub> + 1 X<sub>2</sub> + 1 X<sub>3</sub> + 4 X<sub>4</sub> + 2 X<sub>5</sub> +  X<sub>6</sub> <= 40\
> Horas de Maquina) 2 X<sub>1</sub> + 3 X<sub>2</sub> + 2 X<sub>3</sub> + X<sub>4</sub> + 3 X<sub>5</sub> + 4 X<sub>6</sub> <= 150\

##### Funcional
> Funcional) Z<sub>Max</sub> = 15 X<sub>1</sub> + 18 X<sub>2</sub> + 4 X<sub>3</sub> + 20 X<sub>4</sub> + 3 X<sub>5</sub> + 8 X<sub>6</sub> - 200 Y<sub>1</sub> - 150 Y<sub>2</sub> - 120 Y<sub>3</sub> - 140 Y<sub>4</sub> - 90 Y<sub>5</sub> - 115 Y<sub>6</sub> + 100 Y<sub>Ahorro</sub>

### El mercado es el que manda
Si se quiere hacer que si se fabrica producto 1, no hay mercado para el producto 2 y viceversa:
> Y<sub>1</sub> + Y<sub>2</sub> <= 1