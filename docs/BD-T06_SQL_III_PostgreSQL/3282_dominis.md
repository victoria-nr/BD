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

[« Anterior](3281_seqncies.md) | [Següent »](3283_tipus_de_dades.md)
# <a name="main"></a>**3.2.8.2 Dominis**


Els dominis són els conjunts de valors que pot agafar un determinat camp. Habitualment es posa senzillament un tipus de dades. Però el model relacional teòric és més restrictiu, i els dominis encara podrien ser subconjunts d'aquestos tipus de dades.

Normalment aquestos subconjunts es realitzen per mig dels ***check***, que permeten una regla de validació (una condició) per a donar les dades com a bones (per exemple, un sou sempre és positiu, per tant, a banda de fer que siga numèric podríem obligar a que fóra positiu).

PostgreSQL permet definir dominis, que seran d'un determinat tipus base, d'una grandària determinada (opcional), amb un valor per defecte (opcional) i fins i tot amb una clàusula ***check***. A partir d'aquest moment, un o més d'un camp els podrem definir d'aquest domini (amb l'avantatge que canviant el domini canviem el tipus de tots els camps que el tenen).

Anem a veure alguns exemples que es poden realitzar sobre l'usuari **proves**.

CREATE DOMAIN sou AS numeric(7,2)
CHECK (VALUE > 0);

Si us dóna error perquè ja existia el domini, senzillament esborreu el domini anterior i ho torneu a provar

Ara podríem definir la taula:

CREATE TABLE EMPLEAT5
( cod\_e varchar(5) primary key,
`  `nom\_e varchar(50),
`  `salari sou);

Si intentem introduir la dada del sou malament (per exemple posant-lo negatiu) veurem que dóna error.

![ref1]



Un altre exemple, que farem sobre la Base de Dades **proves**, encara que és un exemple basat en les taules que teníem en **geo**.

En la taula de **POBLACIONS** tenim les coordenades (**latitud** i **longitud**). Podríem intentar fer uns dominis per a marcar l'**hemisferi** (N S per a latitud, i E W per a longitud), els **graus de latitud** (-90º a 90º), **graus de longitud** (-180º a 180º) en longitud, per als **minuts** (0' a 59') , **segons** (0” a 59”). Centrem-nos en la latitud:

CREATE DOMAIN hemi\_lat AS char(1) 

CHECK (VALUE IN ('N','S'));


CREATE DOMAIN graus\_lat AS numeric(2) 

CHECK (VALUE BETWEEN 0 AND 90);


CREATE DOMAIN min\_seg AS numeric(2) 

CHECK (VALUE BETWEEN 0 AND 59);

Ara podríem definir una alternativa a la taula de POBLACIONS:

CREATE TABLE POBLACIONS2 
( nom VARCHAR(50) CONSTRAINT cp\_pob2 PRIMARY KEY,
`  `lat\_h hemi\_lat,
`  `lat\_g graus\_lat,
`  `lat\_m min\_seg,
`  `lat\_s min\_seg);

i comprovaríem que les latituds s'han d'introduir correctament. Si posem per exemple els minuts malament, dóna error

INSERT INTO POBLACIONS2
VALUES('Illes Columbretes','N',39,73,57);

![ref2]

Però no hi ha problema si les dades són correctes.

INSERT INTO POBLACIONS2
VALUES('Illes Columbretes','N',39,53,57);

![ref1]



Per a esborrar un domini, utilitzarem DROP DOMAIN.

DROP DOMAIN sou;

Si algun camp està definit amb el domini que esborrem, donarà error. Si esborràrem amb l'opció CASCADE, s'esborrarien els camps de les taules amb aquest domini. Per a deixar que els companys/es puguen treballar també, esborrem tot el que hem creat:

DROP TABLE EMPLEAT5;

DROP DOMAIN sou;

Encara no esborrem els dominis **hemi\_lat**, **graus\_lat** i **min\_seg**, perquè els utilitzarem en la següent pregunta.

[« Anterior](3281_seqncies.md) | [Següent »](3283_tipus_de_dades.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: 3282_dominis.002.png
[ref2]: 3282_dominis.003.png
