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

[« Anterior](31_introducci.md) | [Següent »](321_tipus_de_dades.md)
# <a name="main"></a>**3.2 DDL**


**DDL** (*Data Definition Language*) o **Llenguatge de Definició de Dades** és el conjunt de sentències que ens permeten definir, retocar o esborrar l'estructura de la Base de Dades. I com que l'estructura bàsica d'una Base de Dades Relacional és la taula, ens dedicarem bàsicament a estudiar les sentències que ens permeten definir les taules (o modificar-les o esborrar-les), amb totes les restriccions que hem vist en el Model Relacional: clau principal, claus externes, camps no nuls, ... També veurem altres objectes que podrem definir, sobretot **vistes**, que es corresponen a l'esquema extern que vam veure en el Tema 1, és a dir, la visió particular que pot tenir un usuari.

Seran 3 sentències les que veurem:

- **CREATE**, que permet crear un objecte nou.
- **DROP**, que permet esborrar un objecte ja existent.
- **ALTER**, que permet modificar un objecte ja existent.

En el moment de crear una taula definirem tots els seus camps, amb les restriccions pertinents a cadascun d'ells. Cada camp haurà de ser d'un tipus de dades. En cada SGBD hi ha uns tipus de dades particulars, encara que els més bàsics són similars, i en ells serà on incidirem més.



[« Anterior](31_introducci.md) | [Següent »](321_tipus_de_dades.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
