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

[« Anterior](321_tipus_de_dades.md) | [Següent »](exercicis.md)
# <a name="main"></a>**3.2.2 CREATE TABLE**


Permet crear una nova taula. Obligatòriament s'hauran d'especificar els camps i els tipus de dades de cada camp. Òbviament, una vegada creada la taula estarà buida, sense cap fila.

Sintaxi

CREATE TABLE taula 
` `( camp1 tipus [(grandària)] [DEFAULT valor] [restricció11] [restricció12] [...] 
[, camp2 tipus [(grandària)] [DEFAULT valor] [restricció21] [restricció22] [...] 
[, ...]] 
[, restricciómultiple1 [, ...]] )

Podem observar que la definició de l'estructura de la taula va entre parèntesis, separant per comes la definició de cada camp.



- El nom de la taula no ha de ser el de cap altre objecte anterior (taula o vista). Si volem posar un nom amb més d'una paraula o amb una paraula reservada, l'haurem de posar entre cometes dobles; però no us ho aconselle, és preferible la utilització del guió baix, i així només és una paraula.
- En cada camp posarem el seu nom i el tipus. Si el tipus de dades és VARCHAR, podrem posar opcionalment la grandària màxima (si no la posem serà de 255 en el cas de text). Si el tipus de dades és NUMERIC, podrem posar opcionalment la grandària (número de xifres significatives) i número de xifres de la part fraccionària.
- Podem posar ocionalment un valor per defecte amb la clàusula **DEFAULT**. D'aquesta manera, en introduir una nova fila en la taula, si no li posem valor a aquest camp, agafarà el valor per defecte. En el valor es pot posar una constant del tipus del camp, o una expressió amb funcions, sempre que torne una dada dels tipus del camp.
- Podem posar opcionalment restriccions a cada camp. Hauran d'anar abans de la coma que separa del següent camp. També poden haver restriccions que afecten a més d'un camp, que preferiblement posarem al final de la definició de la taula. Veurem les restriccions en el següent punt.



Exemples

Si voleu practicar aquestos exemples, feu-lo sobre la Base de Dades **proves** (usuari **proves**, contrasenya **proves**). Si us dóna error perquè la taula que aneu a crear ja està creada la taula, esborreu-la primer, i torneu a executar la sentència.

1. Crear una nova taula anomenada **EMPLEAT1** amb dos camps, un anomenat **dni** de tipus text i llargària 10 i un altre anomenat **nom** amb llargària 50.

CREATE TABLE EMPLEAT1 (dni VARCHAR (10) , nom VARCHAR (50));



2. Crear una taula anomenada **EMPLEAT2** amb un camp text de 10 caràcters anomenat **dni**; un altre camp de tipus text de llargària predeterminada (255) anomenat **nom;** un altre camp anomenat **data\_naixement** de tipus data; un altre anomenat **sou** de tipus numèric, amb 6 xifres significatives, de les quals 2 ha de ser de la part fraccionària i un últim anomenat **departament** de tipus numèric menudet (INT2 o SMALLINT).

CREATE TABLE EMPLEAT2 
( dni VARCHAR(10) , 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 )



3. Crear una taula anomenada **EMPLEAT3** com el de l'exemple anterior, però amb dos camps més al final: un camp anomenat **poblacio** de tipus text de 50 caràcters, i amb el valor per defecte **Castelló** i un últim anomenat **data\_incorporacio** de tipus data i valor per defecte la data d'avui

CREATE TABLE EMPLEAT3 
( dni VARCHAR(10) , 
`  `nom VARCHAR , 
`  `data\_naixement DATE , 
`  `sou NUMERIC(6,2) , 
`  `departament INT2 ,
`  `poblacio VARCHAR(50) DEFAULT 'Castelló' , 
`  `data\_incorporacio DATE DEFAULT CURRENT\_DATE )





[« Anterior](321_tipus_de_dades.md) | [Següent »](exercicis.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
