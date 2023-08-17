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

[« Anterior](33_consultes_dactualitzaci.md) | [Següent »](exercicis4.md)
# <a name="main"></a>**3.3.1 INSERT**


Servirà per a introduir noves files en una determinada taula. Hi ha dues variants d'aquesta sentència. La primera servirà per a introduir noves files proporcionant-li les dades, és a dir, indicant expressament els nous valors dels camps. L'altra podria servir per a introduir noves files de forma més massiva, agafant les dades de les taules ja existents per mig d'una sentència SELECT.

Sintaxi per a inserció amb valors

INSERT INTO taula [ (camp1 [,camp2 [,...]]) ] 
VALUES (valor1 [,valor2 [,...]]) [,(...)]

Com es pot comprovar d'aquesta manera s'introduirà una fila nova, i es proporcionen les dades directament, com a constants. Opcionalment podem introduir els valors per a una segona fila o quantes es vulguen, sempre posant les dades de cada fila entre parèntesis, i si hi ha més d'una fila, separats per comes.

És opcional posar la llista de camps de la taula. Si no es posen, s'haurà de posar un valor per a cada camp de la taula, i en el mateix ordre com estan definits en la taula.

Si posem expressament els camps de la taula, els podrem posar amb l'ordre que vulguem, i no caldrà posar-los tots. Els camps no especificats quedaran amb el valor nul (a no ser que tinguen un valor predeterminat, un valor per defecte). Per tant, haurem de posar obligatòriament tots els camps definits com a no nuls (inclosa la clau principal).

Per a posar el valor nul a un camp posarem explícitament **NULL**.

Si tenim definit un camp autonumèric (SERIAL) i volem continuar amb el següent de la seqüència, no li hem de posar cap valor. Per tant en la sentència SQL no haurà de constar el camp: haurem de posar la llista de camps, i en aquest no ha d'estar el camp autonumèric. Veurem després un exemple per veure-ho més clar.

Per contra, podem trencar la seqüència posant-li un valor al camp autonumèric, però això no haurà modificat la seqüència. Si volem modificar-la hauríem de fer-ho amb la sentència **ALTER SEQUENCE**.

Exemples

1. Introduir un departament nou amb les següents dades: Número: **6**; Nom: **Personal**; Director: **18922222** i Data: **01/05/99**. La taula **DEPARTAMENT** la vam crear en la pregunta **3.2.3** (Restriccions)

INSERT INTO DEPARTAMENT 
VALUES (6,'Personal','18922222','01/05/99');

2. Introduir dos departaments nous, aquest vegada sense posar la data: Número: **7**; Nom: **Vendes**; Director: **18876543**.  I Número: **8**; Nom: **Internacional**; Director: **18999999**. Podem posar a més l'ordre que vulguem:

INSERT INTO DEPARTAMENT (num\_d,director,nom\_d) 
VALUES (7,'18876543','Vendes') , (8,'18999999','Internacional');

També ho podíem haver fet així. Observeu que ara l'ordre ha de ser exactament el de la definició de la taula.

INSERT INTO DEPARTAMENT 
VALUES (7,'Vendes','18876543',NULL) , (8,'Internacional','18999999',NULL);

3. Introduir 3 empleats en la taula **EMPLEAT1**, amb els valors següents (la taula **EMPLEAT1** la vam crear en la primera sentència d'exemple de la pregunta 3.2.2, CREATE TABLE):
   1. Dni: **11111111a**; Nom: **Albert**
   1. Dni: **22222222b**; Nom: **Berta**
   1. Dni: **33333333c**; Nom: **Clàudia**

INSERT INTO EMPLEAT1 
VALUES ('11111111a','Albert') , ('22222222b','Berta') , ('33333333c','Clàudia')

4. Introduir 3 empleats en la taula EMPLEAT2, amb els valors següents (la taula **EMPLEAT2** la vam crear en la segona sentència d'exemple de la pregunta 3.2.2, CREATE TABLE):
   1. Dni: **44444444d**; Nom: **David**; Departament: **6**; Sou: **1000**
   1. Dni: **55555555e**; Nom: **Elena**; Departament: **6**; Sou: **1500**
   1. Dni: **66666666f**; Nom: **Ferran**; Departament: **7**; Sou: **1750**

INSERT INTO EMPLEAT2 (dni,nom,departament,sou)
VALUES ('**44444444d**','**David**',6,1000) , ('**55555555e**','**Elena**',6,1500) , ('**66666666f**','**Ferran**',7,1750)

5. Suposem que tenim una taula de **FACTURES** en la BD **proves**, amb una clau principal que és un **autonumèric** (**SERIAL**). Com volem practicar únicament l'autonumèric, la crearem senzilleta, amb la següent estructura:

CREATE TABLE FACTURES
( num\_f SERIAL PRIMARY KEY,
`  `descripcio VARCHAR,
`  `import NUMERIC );

La manera d'anar introduint normalment serà sense especificar num\_f, per a que vaja agafant valors consecutius.

INSERT INTO FACTURES (descripcio,import)
VALUES ('Factura 1',54.23);

Però si volem trencar la seqüència, sí que posarem num\_f.

INSERT INTO FACTURES
VALUES (2016001,'Factura 1 del 2016',23.98);

Això sí, si introduïm un altra fila sense especificar el número de factura, l'agafarà de la seqüència, que no s'hava modificat, i per tant el valor que ens donarà serà **2**.

INSERT INTO FACTURES (descripcio,import)
VALUES ('Factura 2',36.27);

Per a canviar definitivament el valor que ha d'anar autoincrementant-se, hauríem de modificar la seqüència (**ALTER SEQUENCE**).

Després de les 3 insercions anteriors, el contingut de la taula FACTURES serà aquest:

![](331_insert.002.png)

Sintaxi per a inserció amb subconsulta

INSERT INTO taula [ (camp1 [,camp2 [,...]]) ] 
SELECT ...

És a dir, les dades que van a inserir-se les traiem a partir d'una sentència SELECT. La sentència SELECT pot ser tan complicada com faça falta, i podem posar les clàusules necessàries: WHERE, GROUP BY, ... El requisit és que haurà de tornar tants camps com tinga la taula o com estiguen especificats en la sentència INSERT, i que les dades que tornen siguen del mateix tipus (o tipus compatibles, encara que Access pot fer una conversió de tipus automàtica). Igual que en l'anterior format, quan no s'especifique un camp se li assignarà el valor nul, o el valor predeterminat si en té definit.

Es podria especificar fins i tot una taula d'una base de dades externa. Consulteu la sentència SELECT, l'apartat "Especificació d'una B.D. externa".

Exemples

1. Inserir tots els registres de la taula **EMPLEAT1** en **EMPLEAT3** , suposant que existeixen aquestes taules i encara que tenen una estructura diferent, les dues tenen els camps **dni** i **nom**. Si no existeix la taula **EMPLEAT3**, pots tornar a crear-la, utilitzant l'última sentència de la pregunta 3.2.3 (Restriccions)

INSERT INTO EMPLEAT3(dni,nom) 
SELECT dni,nom FROM EMPLEAT1;

2. Inserir en la taula **EMPLEAT3** tots els empleats de la taula **EMPLEAT2** dels departaments 6 i 7.

INSERT INTO EMPLEAT3 
SELECT \* FROM EMPLEAT2 
`    `WHERE departament IN (6,7);

3. Inserir en la taula EMPLEAT3 els empleats que tenen més d'un familiar. Aquesta sentència no la podrem executar, ja que no tenim la taula **FAMILIAR**. Està únicament de manera il·lustrativa.

INSERT INTO EMPLEAT3 
SELECT \* FROM EMPLEAT 
`    `WHERE dni IN (SELECT dni 
`                      `FROM FAMILIAR 
`                      `GROUP BY dni 
`                      `HAVING COUNT(\*) > 1);

[« Anterior](33_consultes_dactualitzaci.md) | [Següent »](exercicis4.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
