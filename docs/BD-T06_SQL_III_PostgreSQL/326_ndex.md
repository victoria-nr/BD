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

[« Anterior](325_drop_table.md) | [Següent »](exercicis2.md)
# <a name="main"></a>**3.2.6 Índex**


Els índex són estructures de dades que permeten mantenir ordenada una taula respecte a un o més d'un camp, cadascun d'ells de forma ascendent o descendent.

Tenir un índex per un determinat camp o camps permet reduir dràsticament el temps utilitzat en ordenar per ells (perquè ja es manté aquest ordre) i també quan es busca un determinat valor d'aquest camp, ja que com està ordenat es poden fer recerques binàries o dicotòmiques. Quan no està ordenat no hi ha més remei que fer una recerca seqüencial, que és considerablement més lenta.

De tota manera no s'ha d'abusar dels índex, ja que és una estructura addicional de dades que ocuparà espai, i que com s'han de mantenir els índex constantment actualitzats, cada vegada que es realitza una operació d'actualització (inserció, modificació o esborrat) s'ha de reestructurar l'índex, per a posar o llevar l'element al seu lloc.

El següent vídeo intenta explicar de forma molt senzilla com es podria implementar un índex, per poder observar les característiques anteriors. Hem de ser conscients, però, que tot aquest procés és transparent per a l'usuari, que només notaria, en crear un índex, que els SELECT van més ràpids, i els INSERT, DELETE i UPDATE van més lents.





Creació d'índex

A banda de la creació explícita d'índex que farem en aquesta pregunta, PostgreSQL crea implícitament un índex cada vegada que:

- Creem una clau princpal
- Creem una restricció d'unicitat (UNIQUE)

En ambdós casos serà un índex que no es podrà repetir. Per tant, en els casos anteriors no cal crear un índex, perquè PostgreSQL ja ho ha fet automàticament.

En PostgreSQL la creació d'índex és molt completa. Anem a veure una versió resumida:

CREATE [UNIQUE] INDEX nom\_índex 
ON taula (c1 [ASC|DESC][, c2 [ASC|DESC], ...] [NULLS { FIRST | LAST }] )

Si posem l'opció UNIQUE impedirà que es repetesquen els valors del camp (o camps) que formen l'índex, de forma similar a la restricció UNIQUE del CONSTRAINT.

L'opció d'ordenació per defecte és l'ascendent.

Podem fer que els nuls estiguen al principi de tot o al final de tot, segons ens convinga:

- **FIRST**: farà que en l'ordenació els valors nuls vagen abans de qualsevol altre valor. Aquesta és l'opció per defecte si l'ordre és descendenta més de crear l'índex fa que siga clau principal. Evidentment no ha d'haver una clau principal creada amb anterioritat.
- **LAST**: els valors nuls estaran al final de tot, després de qualsevol altre valor. És l'opció per defecte quan l'ordre és ascendent.



Exemples

1. Crear un índex en la taula **EMPLEAT4** per al camp **departament** en ordre ascendent .

CREATE INDEX i\_dep ON EMPLEAT4 (departament);



2. Crear un index per al camp **data\_naixement** (descendent) i **sou** (ascendent) en la taula **EMPLEAT4**. En els dos casos, **data\_naixement** i **sou**, s'han d'ordenar els valors nuls al final

CREATE INDEX i\_dat\_sou ON EMPLEAT4 (data\_naixement DESC NULLS LAST, sou NULLS LAST);

Esborrar un índex 

La sentència d'esborrar un índex és molt senzilla. Només hem d'especificar el nom de l'índex i la taula on està definit. 

DROP INDEX nom\_índex ON taula 

[« Anterior](325_drop_table.md) | [Següent »](exercicis2.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
