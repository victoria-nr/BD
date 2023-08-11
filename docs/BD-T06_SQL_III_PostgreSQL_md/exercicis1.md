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

[« Anterior](324_alter_table.md) | [Següent »](325_drop_table.md)
# <a name="main"></a>**Exercicis**
![ref1]
## **Exercicis apartat 3.2.4**
![ref2]

En **f\_grup\_9999x** (on grup és el vostre grup,  9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF)

**6.85** Afegir un camp a la taula **VENEDOR** anomenat **alies** de tipus text, que ha de ser no nul i únic.

**6.86** Esborrar el camp anterior, **alies**, de la taula **VENEDOR**.

**6.87** Afegir la clau principal de **CATEGORIA**.

**6.88** En la taula **ARTICLE** afegir la clau principal i la clau externa a CATEGORIA.

**6.89** En la taula **LINIA\_FAC** afegir la clau externa que apunta a FACTURA, **exigint que s'esborre en cascada** (si s'esborra una factura, s'esborraran automàticament les seues línies de factura). I també la clau externa que apunta a ARTICLE (aquesta normal, és a dir NO ACTION)

**Nota**

Per a no fer-lo massa llarg s'han deixat de definir alguna restricció, concretament la reflexiva de VENEDOR a VENEDOR (que marca el cap)

[« Anterior](324_alter_table.md) | [Següent »](325_drop_table.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis1.002.png
[ref2]: exercicis1.003.png
