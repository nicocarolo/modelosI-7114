# Practica 26/3 

## Ejercicio 2.1

![alt text](diagramas/ejDos1.png "2.1")

### Hipótesis
- Se vende todo lo producido.
- No hay desperdicio.
- Todo lo producido sirve, no tiene defectos.
- No hay tiempo perdido entre maquinas.
- Las maquinas no se rompen
- No hay costos

### Objetivo
Determinar cuanto producir de A, B y C para maximizar el beneficio en una semana.

### Variables
> X<sub>A</sub>: Cantidad producida de producto A.\
X<sub>B</sub>: Cantidad producida de producto B.\
X<sub>C</sub>: Cantidad producida de producto C.\
X<sub>B<sub>i</sub></sub>: Cantidad producida de producto B en la maquina I.\
X<sub>B<sub>ii</sub></sub>: Cantidad producida de producto B en la maquina II.


### Modelo
- ##### Producto B por Maquina
> B) X<sub>B</sub> = X<sub>B<sub>i</sub></sub> + X<sub>B<sub>ii</sub></sub>\
MinimoB) X<sub>B</sub> <= 10

- ##### Disponibilidad Maquinas
>MaqI) 5 [<sup>Hs</sup>/<sub>Pullover</sub>] X<sub>A</sub> + 6 [<sup>Hs</sup>/<sub>Pullover</sub>] X<sub>B<sub>i</sub></sub> <= 80\
MaqII) 4 [<sup>Hs</sup>/<sub>Pullover</sub>] X<sub>C</sub> + 4 [<sup>Hs</sup>/<sub>Pullover</sub>] X<sub>B<sub>ii</sub></sub> <= 80

- ##### Disponibilidad de materia prima
> LM) 1.8 [<sup>Ks</sup>/<sub>Pullover</sub>] X<sub>B</sub> <= 20 [<sup>Ks</sup>/<sub>Semana</sub>]\
LN) 1.6 [<sup>Ks</sup>/<sub>Pullover</sub>] X<sub>A</sub> + 1.2 [<sup>Ks</sup>/<sub>Pullover</sub>] X<sub>C</sub> <= 36 [<sup>Ks</sup>/<sub>Semana</sub>]

- ##### Funcional
> Funcional) Z<sub>Max</sub> = $10 X<sub>A</sub> + $15 X<sub>B</sub> + $18 X<sub>C</sub> 

## Ejercicio 2.2 (Ejercicio de mezcla)

![alt text](diagramas/ejDos2.png "2.2")

### Hipótesis
- Se vende todo lo producido.
- No hay desperdicio.
- Todo lo extraido sirve, no tiene defectos.
- La calidad es igual sin importar el yacimiento.
- Lo extraido de otros no sirve para nada.

### Objetivo
Determinar cuanto extraer de cada yacimiento y producir de A y B asi como su composicion para maximizar las ganancias en un tiempo determinado.

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
_Seria importante cambiar las igualdades por <= para no limitar al modelo y evitar incompatibilidades_
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


*Esta mal => se tiene que abrir lo extraido de cada mineral para cada aleacion*

*Agregar un restriccion para que el Zinc no puede ser todo en A*
- ##### Funcional
> Funcional) Z<sub>Max</sub> = $A X<sub>A</sub> + $B X<sub>B</sub> - (10 SA + 40 SC + 50 EA)

## Ejercicio 2.4 (Ejercicio de Recursividad)

![alt text](diagramas/ejDos4.png "2.4")

### Hipótesis
- Lo comprado y fabricado son identicos.
- Los tiempos son netos, no se pierde tiempo entre procesos.
- No hay desperdicio de tiempos.
- El dinero no es limitante.

### Objetivo
Determinar la cantidad de produccion y compra de tableros para minimizar costos para un determinado tiempo.

### Variables
> X<sub>A<sub>Aprob</sub></sub>: Cantidad aprobada de tableros A.\
X<sub>A<sub>Prod</sub></sub>: Cantidad producida de tableros A.\
X<sub>A<sub>Compra</sub></sub>: Cantidad comprada de tableros A.\

_Idem demas tableros_

### Modelo
- ##### Minimo
>MinA) X<sub>A<sub>Aprob</sub></sub> = 4000\
MinB) X<sub>B<sub>Aprob</sub></sub> = 3000\
MinC) X<sub>C<sub>Aprob</sub></sub> = 8000\
MinD) X<sub>D<sub>Aprob</sub></sub> = 5000
_Corregir: Seria sumando Producido con Comprados_

- ##### Disponibilidad Hs
> Fabricacion) 0,34 X<sub>A<sub>Prod</sub></sub> + 0,38 X<sub>B<sub>Prod</sub></sub> + 0,47 X<sub>C<sub>Prod</sub></sub> + 0,50 X<sub>D<sub>Prod</sub></sub><=  6500\
Ajuste) 1/ (1 - 0,1)(0,08 X<sub>A<sub>Prod</sub></sub> + 0,06 X<sub>B<sub>Prod</sub></sub> + 0,10 X<sub>C<sub>Prod</sub></sub> + 0,12 X<sub>D<sub>Prod</sub></sub>)<=  1000\
Calidad) 1/ (1 - 0,1)(0,02 X<sub>A<sub>Prod</sub></sub> + 0,03 X<sub>B<sub>Prod</sub></sub> + 0,03 X<sub>C<sub>Prod</sub></sub> + 0,03 X<sub>D<sub>Prod</sub></sub>) + 1/ (1 - 0,2)(0,03 X<sub>A<sub>Compra</sub></sub> + 0,05 X<sub>B<sub>Compra</sub></sub> + 0,04 X<sub>C<sub>Compra</sub></sub> + 0,04 X<sub>D<sub>Compra</sub></sub>)<=  600

_Para la recursividad:_

*1/ (1 - Tasa de Rechazo)*

_Entran 100, con ajuste pasan 90 vuelven 10, la segunda vez, con ajuste pasa 9 vuelve 1, ...._

- ##### Porcentaje Aprob
>Aprobacion) X<sub>A<sub>Aprob</sub></sub> + X<sub>B<sub>Aprob</sub></sub> + X<sub>C<sub>Aprob</sub></sub> + X<sub>D<sub>Aprob</sub></sub> =  0.9(X<sub>A<sub>Prod</sub></sub> + X<sub>B<sub>Prod</sub></sub> + X<sub>C<sub>Prod</sub></sub> + X<sub>D<sub>Prod</sub></sub>) + 0.8(X<sub>A<sub>Compra</sub></sub> + X<sub>B<sub>Compra</sub></sub> + X<sub>C<sub>Compra</sub></sub> + X<sub>D<sub>Compra</sub></sub>)

_Corregir: no es necesario_

- ##### Funcional
> Funcional) Z<sub>Min</sub> = 50 X<sub>A<sub>Prod</sub></sub> + 80 X<sub>A<sub>Compra</sub></sub> + 60 X<sub>B<sub>Prod</sub></sub> + 75 X<sub>B<sub>Compra</sub></sub> + 120 X<sub>C<sub>Prod</sub></sub> + 180 X<sub>C<sub>Compra</sub></sub> + 100 X<sub>D<sub>Prod</sub></sub> + 80 X<sub>D<sub>Compra</sub></sub>

## Ejercicio 2.10 (Ejercicio de armado)

![alt text](diagramas/ejDos10.png "2.10")

### Hipótesis
- No hay costos
- El tiempo es despreciable, no hay limitante.
- No hay limitante de dinero para comprar.
- No hay desperdicio, todas las flores sirven.
- Vendo todo lo que produzco

### Objetivo
Determinar la cantidad de atados de flores a comprar y fabricar para maximizar ganancias para un dia.

### Variables
> X<sub>A<sub>Aprob</sub></sub>: Cantidad aprobada de tableros A.\
X<sub>A<sub>Prod</sub></sub>: Cantidad producida de tableros A.\
X<sub>A<sub>Compra</sub></sub>: Cantidad comprada de tableros A.\

### Modelo

## Ejercicio 2.14

![alt text](diagramas/ejDos14.png "2.14")