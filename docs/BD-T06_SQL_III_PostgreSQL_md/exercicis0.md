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

[« Anterior](323_restriccions_constraint.md) | [Següent »](324_alter_table.md)
# <a name="main"></a>**Exercicis**
![ref1]
## **Exercicis apartat 3.2.3**
![ref2]

En **f\_grup\_9999x** (on grup és el vostre grup,  9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF)

**6.79** Crear la taula **PROVINCIA**, amb la clau principal.

**6.80** Crear la taula **POBLE**, amb la clau principal i la restricció que el camp **cod\_pro** és clau externa que apunta a PROVINCIA.

**6.81** Crear la taula **VENEDOR**, amb la clau principal i la clau externa a POBLE (de moment no definim la clau externa a VENEDOR, que és reflexiva).

**6.82** Crear la taula **CLIENT**, amb la clau principal i la clau externa a POBLE

**6.83** Crear la taula **FACTURA**, amb la clau principal i les claus externes a CLIENT i VENEDOR. També heu d'exigir que **cod\_cli** siga no nul.

**6.84** Crear la taula **LINIA\_FAC**, amb la clau principal (observa que està formada per 2 camps) però de moment sense la clau externa que apunta a ARTICLE. A més **cod\_a** ha de ser no nul.

[« Anterior](323_restriccions_constraint.md) | [Següent »](324_alter_table.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis0.002.png
[ref2]: exercicis0.003.png
