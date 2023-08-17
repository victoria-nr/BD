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

[« Anterior](331_insert.md) | [Següent »](332_delete.md)
# <a name="main"></a>**Exercicis**
![](exercicis4.002.png)
## **Exercicis apartat 3.3.1**
En **f\_grup\_9999x** (on grup és el vostre grup,  9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF)

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

[« Anterior](331_insert.md) | [Següent »](332_delete.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
