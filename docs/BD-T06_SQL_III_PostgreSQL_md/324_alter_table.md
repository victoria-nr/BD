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

[« Anterior](exercicis0.md) | [Següent »](exercicis1.md)
# <a name="main"></a>**3.2.4 ALTER TABLE**


Permet modificar l'estructura d'una taula ja existent, bé afegint, llevant o modificant camps (columnes), bé afegint o llevant restriccions. També servirà per a canviar el nom d'un camp i fins i tot canviar el nom de la taula

Sintaxi

Per a alterar l'estructura d'algun camp o restricció utilitzarem aquesta sintaxi:

ALTER TABLE taula 
{ADD | DROP | ALTER} {COLUMN camp | CONSTRAINT restricciómúltiple}

Per a canviar el nom d'un camp:

ALTER TABLE taula 
RENAME [COLUMN] camp TO nou\_nom\_camp

Per a canviar el nom de la taula:

ALTER TABLE taula 
RENAME TO nou\_nom\_taula

**Afegir camp o restricció**

Si volem afegir una columna o una restricció, l'haurem de definir totalment.

- En el cas d'un camp, haurem d'especificar el nom, el tipus i opcionalment una restricció que afecte només al camp. Per exemple, aquesta sentència afegeix el camp supervisor (de tipus text de 10) a la taula EMPLEAT3. Observeu que en la definició del camp poden entrar restriccions de camp únic.

ALTER TABLE EMPLEAT3 
ADD COLUMN supervisor VARCHAR(10)

- En el cas d'una restricció, aquesta serà del tipus de restricció múltiple, amb la sintaxi que vam veure en l'apartat de restriccions. Per exemple, aquesta sentència afegeix la clau externa reflexiva (de EMPLEAT3 a EMPLEAT3) que indica els supervisors. El dni hauria de ser la clau principal de EMPLEAT3

ALTER TABLE EMPLEAT3 
ADD CONSTRAINT ce\_emp3\_emp3 FOREIGN KEY (supervisor) REFERENCES EMPLEAT3 (dni)

**Modificar un camp**

Podem fer dues coses: modificar el tipus del camp o modificar el valor per defecte (posar valor per defecte o llevar-lo)

Per a canviar el tipus haurem d'utilitzar la sintaxi **... ALTER COLUMN *camp* TYPE *nou\_tipus*** . Per exemple anem a fer que el camp poblacio siga de 25 caràcters

ALTER TABLE EMPLEAT3 
ALTER COLUMN poblacio TYPE VARCHAR(25)

Canviar el tipus de dades és automàtic quan els tipus són compatibles entre ells. Si no ho són ens donarà error, però segurament ho podrem esquivar amb la clàusula **USING**, que ens permet posar a continuació el camp i aprofitem per a posar un **operador de conversió de tipus** (**::**) amb aquesta sintaxi:

ALTER TABLE *TAULA*
ALTER COLUMN *camp* TYPE *tipus\_nou* USING *camp*::*tipus\_nou*

Per a canviar el valor per defecte utilitzarem la sintaxi: **... ALTER COLUMN *camp* {SET | DROP} DEFAULT [*expressió*]** 

ALTER TABLE EMPLEAT3 
ALTER COLUMN poblacio DROP DEFAULT

**Esborrar camp o restricció**

Si volem llevar un camp o una restricció és suficient amb especificar el nom del camp o de la restricció (per això pot ser molt interessant donar nom a les restriccions). En el primer exemple llevem la clau externa del supervisor. En la segona llevem el camp supervisor.

ALTER TABLE EMPLEAT3 
DROP CONSTRAINT ce\_emp3\_emp3;

ALTER TABLE EMPLEAT3 
DROP COLUMN supervisor



**Renomenar un camp**

Per exemple renomenem el camp **data\_incorporacio** a **data\_inc**:

ALTER TABLE EMPLEAT3 
RENAME COLUMN data\_incorporacio TO data\_inc

**Renomenar la taula**

Ara li posarem el nom EMP3 a la taula EMPLEAT3

ALTER TABLE EMPLEAT3 
RENAME TO EMP3

Exemples

1. Modificar la taula **EMP3** per afegir el camp cp (codi postal) de tipus text de 5 caràcters.

ALTER TABLE EMP3 ADD COLUMN cp VARCHAR(5);



2. Modificar la taula **EMP3** per modificar el camp anterior i que siga de tipus numèric.

ALTER TABLE EMP3 ALTER COLUMN cp TYPE NUMERIC(5) USING CP::NUMERIC;



3. Modificar la taula **EMP3** per afegir la restricció (encara que siga un poc estranya) que no es pot repetir la combinació codi postal i població.

ALTER TABLE EMP3 ADD CONSTRAINT u\_cp\_pobl UNIQUE (cp,poblacio);



4. Modificar la taula **EMP3** per esborrar la restricció anterior

ALTER TABLE EMP3 DROP CONSTRAINT u\_cp\_pobl;



5. Modificar la taula **EMP3** per modificar el nom del camp **cp** a **codi\_postal**

ALTER TABLE EMP3 RENAME COLUMN  cp TO codi\_postal;



6. Renomenar la taula **EMP3** a **EMPLEAT3**

ALTER TABLE EMP3 RENAME TO EMPLEAT3;



[« Anterior](exercicis0.md) | [Següent »](exercicis1.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
