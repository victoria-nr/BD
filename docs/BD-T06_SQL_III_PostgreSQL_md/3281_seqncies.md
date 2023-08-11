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

[« Anterior](328_creaci_daltres_objectes_seqncies_dominis_i_tipus.md) | [Següent »](3282_dominis.md)
# <a name="main"></a>**3.2.8.1 Seqüències**


També es poden crear seqüències (**SEQUENCE)**, que són objectes que agafen valors numèrics que van incrementant-se (com l'autonumèric).

CREATE SEQUENCE *nom\_seqüència* 
[START WITH *valor\_inicial*] 
[INCREMENTED BY *valor\_increment*] ... ;

La sentència és més llarga, per a considerar més casos. Per a nosaltres està bé així.

Per defecte, el valor inicial és 1, i l'increment també 1.

És un objecte independent de les taules. S'utilitza de la següent manera:

**CURRVAL ('*nom\_seqüència*')** torna el valor actual (ha d'estar inicialitzat)

**NEXTVAL('*nom\_seqüència*')** incrementa la seqüència i torna el nou valor (excepte la primera vegada que l'inicia amb el valor inicial)

La manera habitual d'utilitzar-lo serà per obtenir un valor que s'afegirà a un camp d'una taula (normalment la clau principal).

Suposem que tenim una taula anomenada **FACTURA** amb l'estructura que ve a continuació, i volem que la clau principal siga un autonumèric. Ho podem provar sobre la Base de Dades i usuari **proves**.

CREATE TABLE FACTURA
( num\_f NUMERIC(7) CONSTRAINT cp\_fact PRIMARY KEY,
data DATE,
client VARCHAR(10));

Primer ens crearem la seqüència:

CREATE SEQUENCE s\_num\_fac START WITH 2016001;

Després l'utilitzem:

INSERT INTO FACTURA VALUES (NEXTVAL('s\_num\_fac'), '15-01-2016','cli001');

Si ara mirem el contingut de la taula **FACTURA** obtindrem:

![ref1]

O fins i tot en el moment de declarar la taula, li posem un valor per defecte al camp, que serà el següent de la seqüència. No haurem d'introduir ara res en la columna **num\_f**,  que agafa el valor de la seqüència

CREATE TABLE FACTURA2
( num\_f NUMERIC(7) CONSTRAINT cp\_fact2 PRIMARY KEY DEFAULT NEXTVAL('s\_num\_fac'),
data DATE,
client VARCHAR(10));

INSERT INTO FACTURA2(data,client) VALUES ('15-01-2016','cli001');

Observeu també que en la taula **FACTURA2**, el valor comença per **2016002**, ja que el primer valor l'havíem utilitzat en **FACTURA**. Per tant el contingut de la taula **FACTURA2** serà:![ref2]

També ho podríem haver fet declarant la clau de tipus **SERIAL**, que el que fa és implementar una seqüència, i donar valors successius per al camp on està definida. Però d'aquesta manera la seqüència comença sempre per 1

CREATE TABLE FACTURA3
( num\_f SERIAL CONSTRAINT cp\_fact3 PRIMARY KEY,
data DATE,
client VARCHAR(10));

I després fer la inserció d'aquesta manera:

INSERT INTO FACTURA3(data,client) VALUES ('15-01-2016','cli001')

Com comentàvem, el valor introduït per la seqüència serà **1**:

![ref3]

Tornarem a veure aquest exemple en les consultes d'actualització, concretament el **INSERT**.

Per a esborrar una seqüència utilitzarem la sentència **DROP SEQUENCE**:

DROP SEQUENCE s\_num\_fac

De moment aquesta sentència ens donaria error, ja que la taula **FACTURA2** utilitza aquesta seqüència. Esborrarem primer les 3 taules, i després la seqüència per a no interferir amb els companys/es.

DROP TABLE FACTURA, FACTURA2, FACTURA3;

DROP SEQUENCE s\_num\_fac;

[« Anterior](328_creaci_daltres_objectes_seqncies_dominis_i_tipus.md) | [Següent »](3282_dominis.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 3281_seqncies.002.png
[ref2]: 3281_seqncies.003.png
[ref3]: 3281_seqncies.004.png
