# Practica 26/3 

## Ejercicio 2.1

![alt text](diagramas/ejDos1.png "2.1")

### Hipótesis
- Se vende todo lo producido.
- No hay desperdicio.
- Todo lo producido sirve, no tiene defectos.
- No hay tiempo perdido entre maquinas.

### Objetivo
Determinar cuanto producir de A, B y C para maximizar las ganancias en una semana.

### Variables
> X<sub>A</sub>: Cantidad producida de producto A.\
X<sub>B</sub>: Cantidad producida de producto B.\
X<sub>C</sub>: Cantidad producida de producto C.\
X<sub>B<sub>i</sub></sub>: Cantidad producida de producto B en la maquina I.\
X<sub>B<sub>ii</sub></sub>: Cantidad producida de producto B en la maquina II.


### Modelo
- ##### Producto B por Maquina
> B) X<sub>B</sub> = X<sub>B<sub>i</sub></sub> + X<sub>B<sub>ii</sub></sub>\
MinimoB) X<sub>B</sub> <= 10\

- ##### Disponibilidad Maquinas
>MaqI) 5 [<sup>Hs</sup>/<sub>Pullover</sub>] X<sub>A</sub> + 6 [<sup>Hs</sup>/<sub>Pullover</sub>] X<sub>B<sub>i</sub></sub> <= 80\
MaqII) 4 [<sup>Hs</sup>/<sub>Pullover</sub>] X<sub>A</sub> + 4 [<sup>Hs</sup>/<sub>Pullover</sub>] X<sub>B<sub>ii</sub></sub> <= 80

- ##### Disponibilidad de materia prima
> LM) 1.8 [<sup>Ks</sup>/<sub>Pullover</sub>] X<sub>B</sub> <= 20 [<sup>Ks</sup>/<sub>Semana</sub>]
LN) 1.6 [<sup>Ks</sup>/<sub>Pullover</sub>] X<sub>A</sub> + 1.2 [<sup>Ks</sup>/<sub>Pullover</sub>] X<sub>C</sub> <= 36 [<sup>Ks</sup>/<sub>Semana</sub>]

- ##### Funcional
> Funcional) Z<sub>Max</sub> = $10 X<sub>A</sub> + $15 X<sub>B</sub> + $18 X<sub>C</sub> 

## Ejercicio 2.2

![alt text](diagramas/ejDos2.png "2.2")

### Hipótesis
- Se vende todo lo producido.
- No hay desperdicio.
- Todo lo producido sirve, no tiene defectos.
- La calidad es igual sin importar el yacimiento.
- Lo extraido de otros no sirve para nada.

### Objetivo
Determinar cuanto producir de A y B para maximizar las ganancias en un tiempo determinado.

### Variables
> X<sub>A</sub>: Cantidad producida de la aleacion A.\
X<sub>B</sub>: Cantidad producida de la aleacion B.\
SA: Cantidad extraida de Sierra Alta.\
SC: Cantidad extraida de Sierra Chica.\
EA: Cantidad extraida de El Abra.\
E<sub>Cu</sub>: Cantidad extraida de cobre.\
E<sub>Es</sub>: Cantidad extraida de estaño.\
E<sub>Mg</sub>: Cantidad extraida de magneso.\
E<sub>Z</sub>: Cantidad extraida de zinc.

### Modelo

- ##### Disponibilidad
> SA) SA <=  1000\
SC) SC <=  2000\
EA) EA <=  3000

- ##### Composicion extraccion
>Cu) E<sub>Cu</sub> =  0,20 SA + 0,10 SC + 0,05 EA\
Es) E<sub>Es</sub> =  0,10 SA + 0,20 SC + 0,05 EA\
Mg) E<sub>Mg</sub> =  0,30 SA + 0,30 SC + 0,70 EA\
Z) E<sub>Z</sub> =  0,30 SA + 0,30 SC + 0,20 EA

- ##### Mezcla
> Cu-A) X<sub>A</sub> <= 0,8 E<sub>Cu</sub>\
Es-A) X<sub>A</sub> <= 0,3 E<sub>Es</sub>\
Z-A) X<sub>A</sub> => 0,5 E<sub>Z</sub>\
Es-B) 0,6 E<sub>Es</sub> => X<sub>B</sub> => 0,4 E<sub>Es</sub>\
Mg-B) X<sub>B</sub> => 0,3 E<sub>Mg</sub>\
Z-B) X<sub>B</sub> <= 0,7 E<sub>Z</sub>

## Ejercicio 2.4

![alt text](diagramas/ejDos4.png "2.4")

## Ejercicio 2.10

![alt text](diagramas/ejDos10.png "2.10")

## Ejercicio 2.14

![alt text](diagramas/ejDos14.png "2.14")