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
- B no tiene cobre.
- A no tiene magnesio.

### Objetivo
Determinar cuanto extraer de cada yacimiento y producir de A y B asi como su composicion para maximizar las ganancias en un tiempo determinado.

### Variables
> X<sub>A</sub>: Cantidad producida de la aleacion A.\
X<sub>B</sub>: Cantidad producida de la aleacion B.\
SA: Cantidad extraida de Sierra Alta.\
SC: Cantidad extraida de Sierra Chica.\
EA: Cantidad extraida de El Abra.\
Cu<sub>A</sub>: Cobre en A. (Idem para Es, Mg y Z)\
Cu<sub>B</sub>: Cobre en B. (Idem para Es, Mg y Z)

### Modelo

- ##### Disponibilidad
> SA) SA <=  1000\
SC) SC <=  2000\
EA) EA <=  3000

- ##### Composicion extraccion
_Seria importante cambiar las igualdades por <= para no limitar al modelo y evitar incompatibilidades_
>Cu) Cu<sub>A</sub> =  0,20 SA + 0,10 SC + 0,05 EA\
Es) Es<sub>A</sub> + Es<sub>B</sub> =  0,10 SA + 0,20 SC + 0,05 EA\
Mg) Mg<sub>B</sub> =  0,30 SA + 0,30 SC + 0,70 EA\
Z) Z<sub>A</sub> + Z<sub>B</sub> =  0,30 SA + 0,30 SC + 0,20 EA\

- ##### Mezcla
> A) X<sub>A</sub> = Cu<sub>A</sub> + Es<sub>A</sub> + Z<sub>A</sub>\
B) X<sub>B/sub> = Mg<sub>B</sub> + Es<sub>B</sub> + Z<sub>B</sub>\
Cu en A) 0,8 X<sub>A</sub> <=  Cu<sub>A</sub>\
Es en A) 0,3 X<sub>A</sub> <= Es<sub>A</sub>\
Z en A) 0,5 X<sub>A</sub> => Z<sub>A</sub>\
Minimo dos metales en A) m <= 0,3 Es<sub>A</sub> + Cu<sub>A</sub> _(m es una constante muy chiquita para obligar a que si o si sea mayor que 0 y la aleacion tenga al menos 2 metales)_\
Es en B) 0,6 Es<sub>B</sub> => X<sub>B</sub>\
Es en B) X<sub>B</sub> => 0,4 Es<sub>B</sub>\
Mg en B) 0,3 X<sub>B</sub> => Mg<sub>B</sub>\
Z en B) 0,7 X<sub>B</sub> <= Z<sub>B</sub>


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
> X<sub>A<sub>Prod</sub></sub>: Cantidad producida de tableros A.\
X<sub>A<sub>Compra</sub></sub>: Cantidad comprada de tableros A.

_Idem demas tableros_

### Modelo
- ##### Minimo
>MinA) X<sub>A<sub>Prod</sub></sub> + X<sub>A<sub>Compra</sub></sub> = 4000\
MinB) X<sub>B<sub>Prod</sub></sub> + X<sub>B<sub>Compra</sub></sub> = 3000\
MinC) X<sub>C<sub>Prod</sub></sub> + X<sub>C<sub>Compra</sub></sub> = 8000\
MinD) X<sub>D<sub>Prod</sub></sub> + X<sub>D<sub>Compra</sub></sub> = 5000


- ##### Disponibilidad Hs
> Fabricacion) 0,34 X<sub>A<sub>Prod</sub></sub> + 0,38 X<sub>B<sub>Prod</sub></sub> + 0,47 X<sub>C<sub>Prod</sub></sub> + 0,50 X<sub>D<sub>Prod</sub></sub><=  6500\
Ajuste) 1/ (1 - 0,1)(0,08 X<sub>A<sub>Prod</sub></sub> + 0,06 X<sub>B<sub>Prod</sub></sub> + 0,10 X<sub>C<sub>Prod</sub></sub> + 0,12 X<sub>D<sub>Prod</sub></sub>)<=  1000\
Calidad) 1/ (1 - 0,1)(0,02 X<sub>A<sub>Prod</sub></sub> + 0,03 X<sub>B<sub>Prod</sub></sub> + 0,03 X<sub>C<sub>Prod</sub></sub> + 0,03 X<sub>D<sub>Prod</sub></sub>) + 1/ (1 - 0,2)(0,03 X<sub>A<sub>Compra</sub></sub> + 0,05 X<sub>B<sub>Compra</sub></sub> + 0,04 X<sub>C<sub>Compra</sub></sub> + 0,04 X<sub>D<sub>Compra</sub></sub>)<=  600

_Para la recursividad:_

*1/ (1 - Tasa de Rechazo)*

_Entran 100, con ajuste pasan 90 vuelven 10, la segunda vez, con ajuste pasa 9 vuelve 1, ...._

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
> A<sub>i</sub>: Cantidad de atados de i a comprar (i= {RTL, RA, RR, C, M}).\
R<sub>i</sub>: Cantidad de ramos de i a armar (i= {RTL, RA, RR, CH, M, G}).\
F<sub>i - j</sub>: Flores de tipo i usados en el ramo j (i= {RTL, RA, RR, C, M}), (j= {RRTL, RRA, RRR, RCH, RM, RG}).\

### Modelo
- ##### Cantidad de flores (desarmo atados)
> RTL) 20 A<sub>RTL</sub> => F<sub>RTL - RRTL</sub> + F<sub>RTL - RM</sub> + F<sub>RTL - RG</sub>\
RA) 20 A<sub>RA</sub> => F<sub>RA - RRA</sub> + F<sub>RA - RM</sub> + F<sub>RA - RG</sub>\
RR) 20 A<sub>RR</sub> => F<sub>RR - RRR</sub> + F<sub>RR - RM</sub> + F<sub>RR - RG</sub>\
C) 20 A<sub>C</sub> => F<sub>C - RC</sub> + F<sub>C - RM</sub> + F<sub>C - RG</sub> + F<sub>C - RCH</sub>\
M) 20 A<sub>M</sub> => F<sub>M - RCH</sub> + F<sub>M - RM</sub> + F<sub>M - RG</sub>

- ##### Armado - Rosas
> RTL) 1 R<sub>RTL</sub> => F<sub>RTL - RRTL</sub>\
RA) 9 R<sub>RA</sub> => F<sub>RA - RRA</sub>\
RR) 7 R<sub>RR</sub> => F<sub>RR - RRR</sub>

- ##### Armado - Crisantemos
> C) 18 R<sub>C</sub> => F<sub>C - RC</sub>

- ##### Armado - Chicos
> C) 6 R<sub>CH</sub> => F<sub>C - RCH</sub>\
M) 8 R<sub>CH</sub> => F<sub>M - RCH</sub>

- ##### Armado - Medianos
> C) 10 R<sub>M</sub> => F<sub>C - RM</sub>\
M) 10 R<sub>M</sub> => F<sub>M - RM</sub>\
R) 1 R<sub>M</sub> => F<sub>R - RM</sub>

- ##### Armado - Grandes
> C) 10 R<sub>G</sub> => F<sub>C - RG</sub>\
M) 15 R<sub>G</sub> => F<sub>M - RG</sub>\
R) 5 R<sub>G</sub> => F<sub>R - RG</sub>

- ##### Definicion F<sub>R - RM</sub>, F<sub>R - RG</sub> (Para que cualquier rosa pueda usarse en los ramos medianos y grandes)
> RG) F<sub>R - RG</sub> = F<sub>RTL - RG</sub> + F<sub>RA - RG</sub> + F<sub>RR - RG</sub>\
RM) F<sub>R - RM</sub> = F<sub>RTL - RM</sub> + F<sub>RA - RM</sub> + F<sub>RR - RM</sub>

- ##### Demanda
> R<sub>RTL</sub> < 650\
R<sub>RA</sub> < 350\
R<sub>RR</sub> < 250\
R<sub>CH</sub> < 1100\
R<sub>M</sub> < 950\
R<sub>G</sub> < 625\
R<sub>C</sub> < 650

- ##### Funcional
> Funcional) Z<sub>Max</sub> = Ganancia de los R<sub>i</sub> - Costos de los A<sub>i</sub>

## Ejercicio 2.14 (Centros con mezcla a la entrada y metas)

![alt text](diagramas/ejDos14.png "2.14")

### Hipótesis
- IMPORTANTE hipotesis sobre donde se aplica el rendimiento/disponibolidad
- No se rompen las maquinas.
- Todo lo producido se vende.
- El rendimiento no varia.
- No hay desperdicio de tiempo.
- No hay mezcla a la salida.
- El centro 2 y 3 funcionan a la par.

### Objetivo
Determinar cuanta materia prima comprar, cuanto producir de P1 y P2, y cuantas horas trabajo una persona para maximizar la ganancia en una semana.

### Variables
> A<sub>i</sub>: Cantidad de atados de i a comprar (i= {RTL, RA, RR, C, M}).\
R<sub>i</sub>: Cantidad de ramos de i a armar (i= {RTL, RA, RR, CH, M, G}).\
F<sub>i - j</sub>: Flores de tipo i usados en el ramo j (i= {RTL, RA, RR, C, M}), (j= {RRTL, RRA, RRR, RCH, RM, RG}).\
E<sub>i-j</sub>: Entrada de producto i a centro j.\
S<sub>i-j</sub>: Salida de centro i a centro j

### Modelo
- ##### Centro 3
- ###### Rendimiento
> Rendimiento) 0,9 (E<sub>B-3</sub> + E<sub>C-3</sub>) = S<sub>3-5</sub>\
Mezcla Entrada) 0,4 (E<sub>B-3</sub> + E<sub>C-3</sub>) = E<sub>B-3</sub>\
0,6 (E<sub>B-3</sub> + E<sub>C-3</sub>) = E<sub>C-3</sub> //No es necesaria, la obliga la anterior\
Capacidad) 1/25 (E<sub>B-3</sub> + E<sub>C-3</sub>) <= 35 //Aplicando el rendimiento a la salida, si fuera a la entrada multiplicaria la suma de E por 0,9 o poniendo S<sub>3-5</sub>

Falta agregar lo de las horas por empleado.