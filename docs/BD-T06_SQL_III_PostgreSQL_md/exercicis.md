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

[« Anterior](322_create_table.md) | [Següent »](323_restriccions_constraint.md)
# <a name="main"></a>**Exercicis**
![ref1]
## **Exercicis apartat 3.2.2**
Al llarg d'aquesta tercera part, en el conjunt d'exercicis de DDL, crearem tota l'estructura de la Base de Dades **FACTURA**, però per a no interferir cadascú amb els altres companys, cadascú es connectarà a la seua Base de Dades **f\_grup\_9999x** (on grup és el vostre grup p.ex. 1cfsg, 1cfsh... ,  9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF).

L'esquema Entitat-Relació i l'esquema relacional que implementarem serà el següent:

![ref2]



En la Base de Dades anomenada  **f\_grup\_9999x** (on grup és el vostre grup,  9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF), connectant com un usuari amb el mateix nom i contrasenya:

**6.77** Creeu la taula **CATEGORIA**, amb els mateixos camps i del mateix tipus que en la taula CATEGORIA de **FACTURA**, però de moment sense clau principal ni cap altra restricció. Guardeu la consulta de creació com **Ex\_6\_77.sql**

**6.78** Creeu la taula **ARTICLE**, també sense restriccions. Guardar la consulta com **Ex\_6\_78.sql**

Nota

Durant tots aquestos exercicis de DDL pot ser molt convenient tenir obertes les dues connexions: la de **FACTURA** (per anar consultant) i la de **f\_grup\_9999x** (per anar creant i modificant), on grup és el vostre grup, 9999 són les 4 últimes xifres del vostre DNI, i x la lletra del NIF.

[« Anterior](322_create_table.md) | [Següent »](323_restriccions_constraint.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**

[ref1]: exercicis.002.png
[ref2]: exercicis.003.png
