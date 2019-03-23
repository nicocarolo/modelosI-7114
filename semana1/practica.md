# Practica 19/3 

## Ejercicio 1.2

![alt text](diagramas/ejUno2.png "1.2")

### Hipótesis
- Se vende todo lo producido.
- No hay desperdicio.
- Todo lo producido sirve, no tiene defectos.
- No hay tiempo perdido entre maquinas.

### Objetivo
Determinar cuanto producir de 1 y 2 para maximizar las ventas en un mes.

### Variables
> X<sub>1</sub>: Cantidad producida de producto 1.\
X<sub>2</sub>: Cantidad producida de producto 2.

### Modelo
> MaqA) 2 [<sup>Hs</sup>/<sub>Mes</sub>] X<sub>1</sub> + 4 [<sup>Hs</sup>/<sub>Mes</sub>] X<sub>2</sub> <= 80[<sup>Hs</sup>/<sub>Mes</sub>]\
MaqB) 3 [<sup>Hs</sup>/<sub>Mes</sub>] X<sub>1</sub> + 2 [<sup>Hs</sup>/<sub>Mes</sub>] X<sub>2</sub> <= 60[<sup>Hs</sup>/<sub>Mes</sub>]\
MaqC) 4 [<sup>Hs</sup>/<sub>Mes</sub>] X<sub>1</sub> + 2 [<sup>Hs</sup>/<sub>Mes</sub>] X<sub>2</sub> <= 100[<sup>Hs</sup>/<sub>Mes</sub>]

> Funcional) Z<sub>Max</sub> = $60 X<sub>1</sub> + $50 X<sub>2</sub> 

## Ejercicio 1.2

![alt text](diagramas/ejUno3.png "1.3")

### Hipótesis
- Se vende todo lo producido.
- No hay desperdicio.
- Precio no varia.
- No es necesaria pasar por las dos maquinas para un producto.
- Todo lo producido sirve y tiene la misma calidad sin depender de la maquina, no tiene defectos.
- No hay tiempo perdido entre maquinas.

### Objetivo
Determinar cuanto producir de A y B para maximizar las ganancias en un periodo determinado.

### Variables
> X<sub>A</sub>: Cantidad producida de producto A.\
X<sub>A<sub>i</sub></sub>: Cantidad producida de producto A en maquina I.\
X<sub>A<sub>ii</sub></sub>: Cantidad producida de producto A en maquina II.

_Idem para producto B (Mismas cantidad de variables)_

### Modelo
> A) X<sub>A</sub> = X<sub>A<sub>i</sub></sub> + X<sub>A<sub>ii</sub></sub>\
B) X<sub>B</sub> = X<sub>B<sub>i</sub></sub> + X<sub>B<sub>ii</sub></sub>\
MinimoA) X<sub>A</sub> => 50\
MinimoB) X<sub>B</sub> => 4 X<sub>A</sub>\
MaqI) X<sub>A<sub>i</sub></sub> + 0,4 X<sub>B<sub>i</sub></sub> <= 200\
MaqII) 0,5 X<sub>A<sub>ii</sub></sub> + X<sub>B<sub>ii</sub></sub> <= 200

> Funcional) Z<sub>Max</sub> = $12 X<sub>A</sub> + $8 X<sub>B</sub> 

## Ejercicio 1.5

![alt text](diagramas/ejUno5.png "1.5")

### Hipótesis
- No hay stock inicial.
- Precio no varia.
- No cambian los nutrientes de c/kilo.
- Todo lo comprado se consume.
- La calidad sin depender de los nutrientes en M y N es la misma.

### Objetivo
Determinar cuanto alimentos de A y B debe suministrarse en un dia a un ganado para minimizar costos.

### Variables
> X<sub>M</sub>: Cantidad de alimentos de M.\
X<sub>N</sub>: Cantidad de alimentos de N.

_Idem para producto B (Mismas cantidad de variables)_

### Modelo
> A) 100 X<sub>M</sub> + 0 X<sub>N</sub> => 400\
B) 0 X<sub>M</sub> + 100 X<sub>N</sub> => 600\
C) 100 X<sub>M</sub> + 200 X<sub>N</sub> => 2000\
B) 200 X<sub>M</sub> + 100 X<sub>N</sub> => 1700

_Es una mezcla y no se usan variables para los nutrientes porque si lo hiciera dejaria que el modelo cambia la composicion de los alimentos M y N._

> Funcional) Z<sub>Min</sub> = $10 X<sub>M</sub> + $4 X<sub>N</sub> 