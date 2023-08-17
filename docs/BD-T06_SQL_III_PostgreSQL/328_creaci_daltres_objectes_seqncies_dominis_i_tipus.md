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

[« Anterior](exercicis3.md) | [Següent »](3281_seqncies.md)
# <a name="main"></a>**3.2.8. Creació d'altres objectes: seqüències, dominis i tipus.**


Una de les característiques de PostgreSQL és la seua gran versatilitat.

En concret es poden crear molts objectes. A banda dels habituals, vistes, seqüències, ... es poden xcrear més tipus d'objectes. En aquest curs donarem una ulladeta als dominis i la definició de nous tipus de dades.



Hem de tenir en consideració que tots ens connectarem com el mateix usuari per a fer proves. Per tant els objectes que creem poden fastidiar a altres companys si utilitzem tots els mateixos noms.

En altres SGBD (com per exemple Oracle) existeix la possibilitat de crear els objectes posant **CREATE OR REPLACE ...**, que si no existeix el crea, i si existeix el substitueix. Lamentablement en PostgreSQL depén de la versió: en les més modernes sí que es pot, però en versions anteriors (com la 8.4 que és la que tenim ara en el servidor) no podrem, excepte en les vistes i les funcions. 

[« Anterior](exercicis3.md) | [Següent »](3281_seqncies.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
