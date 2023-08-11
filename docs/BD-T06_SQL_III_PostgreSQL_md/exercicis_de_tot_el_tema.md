Bases de Dades

- [Tema 6: SQL - DDL i consultes d'actualització (part III)](index.md)
- [3.1 Introducció](31_introducci.md)
- [3.2 DDL](32_ddl.md) 
  - [3.2.1 Tipus de dades](321_tipus_de_dades.md)
  - [3.2.2 CREATE TABLE](322_create_table.md) 
    - [Exercicis](exercicis.md)
  - [3.2.3 Restriccions (Constraint)](323_restriccions_constraint.md) 
    - [Exercicis](exercicis0.md)
  - [3.2.4 ALTER TABLE](324_alter_table.md) 
    - [Exercicis](exercicis1.md)
  - [3.2.5 DROP TABLE](325_drop_table.md)
  - [3.2.6 Índex](326_ndex.md) 
    - [Exercicis](exercicis2.md)
  - [3.2.7 Vistes](327_vistes.md) 
    - [Exercicis](exercicis3.md)
  - [3.2.8. Creació d'altres objectes: seqüències, dominis i tipus.](328_creaci_daltres_objectes_seqncies_dominis_i_tipus.md) 
    - [3.2.8.1 Seqüències](3281_seqncies.md)
    - [3.2.8.2 Dominis](3282_dominis.md)
    - [3.2.8.3 Tipus de dades](3283_tipus_de_dades.md)
- [3.3 Consultes d'actualització](33_consultes_dactualitzaci.md) 
  - [3.3.1 INSERT](331_insert.md) 
    - [Exercicis](exercicis4.md)
  - [3.3.2 DELETE](332_delete.md) 
    - [Exercicis](exercicis5.md)
  - [3.3.3 UPDATE](333_update.md) 
    - [Exercicis](exercicis6.md)
- [Exercicis de tot el tema](exercicis_de_tot_el_tema.md)

[« Anterior](exercicis6.md)
# <a name="main"></a>**Exercicis de tot el tema**
Al llarg d'aquesta tercera part, en el conjunt d'exercicis de DDL, crearem tota l'estructura de la Base de Dades **FACTURA**, però per a no interferir cadascú amb els altres companys, cadascú es connectarà a la seua Base de Dades **f\_grup\_9999x** (on grup és el vostre grup p.ex. 1cfsg, 1cfsh... ,  9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF).

L'esquema Entitat-Relació i l'esquema relacional que implementarem serà el següent:

![](exercicis_de_tot_el_tema.002.png)



En la Base de Dades anomenada **f\_grup\_9999x** (on grup és el vostre grup,  9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF), connectant com un usuari amb el mateix nom i contrasenya:

Nota

Durant tots aquestos exercicis de DDL pot ser molt convenient tenir obertes les dues connexions: la de **FACTURA** (per anar consultant) i la de **f\_grup\_9999x** (per anar creant i modificant), on grup és el vostre grup,  9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF.

**6.77** Creeu la taula **CATEGORIA**, amb els mateixos camps i del mateix tipus que en la taula CATEGORIA de **FACTURA**, però de moment sense clau principal ni cap altra restricció. Guardeu la consulta de creació com **Ex\_6\_77.sql**

**6.78** Creeu la taula **ARTICLE**, també sense restriccions. Guardar la consulta com **Ex\_6\_78.sql**

**6.79** Crear la taula **PROVINCIA**, amb la clau principal.

**6.80** Crear la taula **POBLE**, amb la clau principal i la restricció que el camp **cod\_pro** és clau externa que apunta a PROVINCIA.

**6.81** Crear la taula **VENEDOR**, amb la clau principal i la clau externa a POBLE (de moment no definim la clau externa a VENEDOR, que és reflexiva).

**6.82** Crear la taula **CLIENT**, amb la clau principal i la clau externa a POBLE

**6.83** Crear la taula **FACTURA**, amb la clau principal i les claus externes a CLIENT i VENEDOR. També heu d'exigir que **cod\_cli** siga no nul.

**6.84** Crear la taula **LINIA\_FAC**, amb la clau principal (observa que està formada per 2 camps) però de moment sense la clau externa que apunta a ARTICLE. A més **cod\_a** ha de ser no nul.

**6.85** Afegir un camp a la taula **VENEDOR** anomenat **alies** de tipus text, que ha de ser no nul i únic.

**6.86** Esborrar el camp anterior, **alies**, de la taula **VENEDOR**.

**6.87** Afegir la clau principal de **CATEGORIA**.

**6.88** En la taula **ARTICLE** afegir la clau principal i la clau externa a CATEGORIA.

**6.89** En la taula **LINIA\_FAC** afegir la clau externa que apunta a FACTURA, **exigint que s'esborre en cascada** (si s'esborra una factura, s'esborraran automàticament les seues línies de factura). I també la clau externa que apunta a ARTICLE (aquesta normal, és a dir NO ACTION)

**6.90** Afegir un índex anomenat **i\_nom\_cli** a la taula **CLIENT** pel camp **nom**.

**6.91** Afegir un índex anomenat **i\_adr\_ven** a  la taula **VENEDOR** per a que estiga ordenat per **cp** (ascendent) i **adreca** (descendent).

**6.92** Crear la vista **RESUM\_FACTURA**, que ens dóne el total dels diners de la factura, el total després del descompte d'articles, i el total després del descompte de la factura, tal i com teníem en la consulta **6.56**. A partir d'aquest moment podrem utilitzar la vista per a traure aquestos resultats

**6.93** Inserir en la taula **CATEGORIA** les següents files:

|**cod\_cat**|**descripcio**|
| :- | :- |
|BjcOlimpia|Components Bjc Seria Olimpia|
|Legrand|Components marca Legrand|
|IntMagn|Interruptor Magnetotérmico|
|Niessen|Components Niesen Serie Lisa|

**6.94** Inserir els següents articles.

|**cod\_art**|**descrip**|**preu**|**stock**|**stock\_min**|**cod\_cat**|
| :- | :- | :- | :- | :- | :- |
|B10028B|Cruzamiento  Bjc Serie Olimpia|4\.38|2|1|BjcOlimpia|
|B10200B|Cruzamiento Bjc Olimpia Con Visor|0\.88|29||BjcOlimpia|
|L16550|Cartucho Fusible Legrand T2 250 A|5\.89|1|1|Legrand|
|L16555|Cartucho Fusible Legrand T2 315 A|5\.89|3|3|Legrand|
|IM2P10L|Interruptor Magnetotermico  2p, 4|14\.84|2|1|IntMagn|
|N8008BA|Base Tt Lateral Niessen Trazo Bla|4\.38|6|6|Niessen|

**6.95** Inserir en la taula **CLIENT** tres files amb les següents dades

|**cod\_cli**|**nom**|**adreca**|**cp**|**cod\_pob**|
| :- | :- | :- | :- | :- |
|303|MIRAVET SALA, MARIA MERCEDES|URBANIZACION EL BALCO, 84-11|||
|306|SAMPEDRO SIMO, MARIA MERCEDES|FINELLO, 161|12217||
|387|TUR MARTIN, MANUEL FRANCISCO|CALLE PEDRO VIRUELA, 108-8|12008||
**6.96** Inserir la següent factura:

|**num\_f**|**data**|**cod\_cli**|**cod\_ven**|**iva**|**dte**|
| :- | :- | :- | :- | :- | :- |
|6535|2015-01-01|306||21|10|


|**num\_f**|**num\_l**|**cod\_art**|**quant**|**preu**|**dte**|
| :- | :- | :- | :- | :- | :- |
|6535|1|L16555|2|5\.89|25|

**6.97** Inserir la següent factura (aquesta té més d'una línia de factura).

|**num\_f**|**data**|**cod\_cli**|**cod\_ven**|**iva**|**dte**|
| :- | :- | :- | :- | :- | :- |
|6559|2015-02-16|387||10|10|


|**num\_f**|**num\_l**|**cod\_art**|**quant**|**preu**|**dte**|
| :- | :- | :- | :- | :- | :- |
|6559|1|IM2P10L|3|14\.84||
|6559|2|N8008BA|6|4\.38|20|

**6.98** Esborrar la factura **6559**. Comprovar que també s'han esborrat les seues línies de factura

**6.99** Esborrar els articles dels quals **no** tenim **stock mínim**.

**6.100** Llevar tots els codis postals dels clients.

**6.101** Pujar el preu dels articles de la categoria **BjcOlimpia** un **5%** (el resultat serà que l'únic article d'aquesta categoria haurà passat d'un preu de 4.38 a **4.60€**)

[« Anterior](exercicis6.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
