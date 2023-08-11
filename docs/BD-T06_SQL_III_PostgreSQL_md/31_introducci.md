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

[« Anterior](index.md) | [Següent »](32_ddl.md)
# <a name="main"></a>**3.1 Introducció**


Fins el moment només hem vist una sentència, el SELECT, una sentència molt potent per a poder consultar el contingut de les taules d'una Base de Dades. Però el llenguatge SQL és més complet, i permet també crear l'estructura de les taules i altres objectes. I també ens permetrà manipular la informació, introduint dades noves, eliminant-ne o modificant les ja existents.

Subdividirem, aquesta part del tema en dos grans blocs:

- **DDL** (*Data Definition Language*) llenguatge de definició de dades. És el que ens permetrà definir les estructures de dades: taules, vistes, i com veurem en altres temes, més objectes.
- **Consultes d'actualització**. No canvien cap estructura de cap taula, sinó que modifiquen el contingut de les taules. I només hi ha 3 possibilitats en la modificació del contingut: inserir noves files (INSERT), modificar les ja existents en algun camp determinat (UPDATE) o esborrar files (DELETE)

Durant tota aquesta tercera part de SQL farem consultes per a crear o modificar taules, o per a modificar les dades de les taules.

No ens convé en absolut treballar sobre la Base de Dades **geo** ni sobre **factura**, ja que el que faríem seria "boicotejar-nos" entre nosaltres. Treballarem amb dues Bases de Dades noves:

- **proves** (connectant-nos com l'usuari **proves**): servirà per a fer proves, com el seu propi nom indica. Tots els exemples els farem en aquesta BD
- **f\_grup\_9999x**, on grup és el codi del vostre grup (p.ex 1cfsg, 1cfsj, 1cfsl...), 9999 seran les 4 últimes xifres del vostre DNI, i x és la lletra del vostre NIF. És a dir, tindreu una Base de Dades per a cadascú de vosaltres, i un usuari amb el mateix nom. És on haureu de treballar els exercicis.

Us recomane vivament que us creeu una altra connexió per a cadascuna de les Bases de Dades anteriors. D'aquesta manera, segurament en tindreu quatre connexions: la de **geo**, la de **factura**, la de **proves** i la de **f\_grup\_9999x** (substituint per les dades del vostre grup i NIF)

[« Anterior](index.md) | [Següent »](32_ddl.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
