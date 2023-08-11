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

[« Anterior](3282_dominis.md) | [Següent »](33_consultes_dactualitzaci.md)
# <a name="main"></a>**3.2.8.3 Tipus de dades**


Ja havíem comentat que PosgreSQL és molt versàtil, i permet a l'usuari crear tipus de dades personals.

Tres són les maneres de crear un tipus de dades: compost, enumerat i extern.

- El **compost** és com un registre, on s'especifiquen els *camps* i els *tipus*.
- **Enumenat**: posarem els possibles *valors* entre parèntesis.
- L'**extern** és molt més complet i complex que permet crear un nou tipus base, amb una estructura interna i amb funcions, normalment creades en C, d'entrada (per a introduir la dada) i eixida (per a representar-la), d'anàlisi, ... Aquest tipus s'escapa dels objectius d'aquest curs



Compost

Posarem entre parèntesi el nom dels camps i el tipus que formaran part d'aquest tipus compost. Per exemple, sobre la Base de Dades **proves**:

CREATE TYPE num\_complex AS (a float4, b float4);

que ens serviria per a representar números complexes. Si us dóna error perquè ja existieix el tipus (perquè l'ha creat un company/a), senzillament esborreu-lo abans i ho torneu a provar

Un altre exemple (no cal fer-lo, és il·lustratiu només):

CREATE TYPE lat AS (
h char(1),
g numeric(2,0),
m numeric(2,0),
s numeric(2,0));

per a representar la latitud, encara que podríem aprofitar els dominis creats en el punt anterior, i ens eixirà millor (aquest sí que el podeu fer):

CREATE TYPE lat AS (
h hemi\_lat,
g graus\_lat,
m min\_seg,
s min\_seg);

i el tipus **lat** haurà de respectar les restriccions de cada domini dels quatre camps.

Ara podríem definir una taula

CREATE TABLE POBLACIONS3 (
nom VARCHAR(50) CONSTRAINT cp\_pob3 PRIMARY KEY,
latitud lat,
comarca varchar(50));

D'aquesta manera queda molt compacte.

Per exemple, aquesta introducció de dades donarà un error, ja que l'hemisferi no és correcte:

INSERT INTO POBLACIONS3
VALUES ('Castelló','(K,39,59,10)','Plana Alta');

En canvi aquesta funcionarà perfectament:

INSERT INTO POBLACIONS3
VALUES ('Castelló','(N,39,59,10)','Plana Alta');

Per a accedir als camps dels tipus compostos, bé ja definits, bé definits per nosaltres, haurem de posar el nom de la columna seguida d'un punt i seguit del nom del camp. Però en les sentències SQL se'ns presenta un problema: que aquesta sintaxi serveix per a posar també el nom de la taula seguit del nom de la columna. Així per exemple ens donarà error la següent sentència, en la que volem traure el nom de la població, la latitud i si està en l'hemisferi nord o sud:

SELECT nom, latitud, latitud.h FROM POBLACIONS3;

L'error el dóna perquè en **latitud.h** espera que latitud siga una taula i h una columna. La manera d'esquivar aquest error és posar entre parèntesis la columna:

SELECT nom, latitud, (latitud).h FROM POBLACIONS3;

En el tema següent, el de programació en **PL/pgSQL** veurem que allà no caldrà posar els parèntesis, perquè no hi haurà la confusió de taula.columna



Enumerat

El tipus enumerat és un conjunt de dades *estàtiques* definides en el moment de la creació del tipus, amb un ordre també predefinit. Està disponible des de la versió **8.3** de **PostgreSQL**.

Ací tenim un exemple:

CREATE TYPE d\_set AS ENUM ('dilluns','dimarts','dimecres','dijous','divendres','dissabte','diumenge');

Posteriorment el podrem utilitzar, per exemple, en la definició d'una taula:

CREATE TABLE HORARI (
cod\_pr NUMERIC(5) PRIMARY KEY,
d\_tut d\_set,
h\_tut NUMERIC(4,2));

Ara el podem utilitzar. Haurem de tenir en compte que els valors són únicament els definits. I s'ha de respectar majúscules i minuscules.

INSERT INTO HORARI VALUES (1,'dimarts',10);

En canvi, aquesta donaria error:

INSERT INTO HORARI VALUES (2,'Dimecres',12);

ja que el nom de la setmana comença en majúscula.

Introduïm algunes dades més

INSERT INTO HORARI VALUES (2, 'dimecres',12) , (3,'dilluns',9) , (4,'divendres',11);

Podem comprovar com l'ordre predefint és el del moment de la creació del tipus:

SELECT \* FROM HORARI ORDER BY d\_tut;

I com també es pot comprovar en aquesta sentència:

SELECT \* FROM HORARI WHERE d\_tut > 'dimarts';

on només eixiran les files corresponents al dimecres i al divendres (files 2 i 4).

Per últim, anem a esborrar els objectes que hem creat, per a no interferir amb els companys:

DROP TABLE POBLACIONS2 , POBLACIONS3 , HORARI ;

DROP TYPE num\_complex , lat , d\_set ;

DROP DOMAIN hemi\_lat , graus\_lat , min\_seg ;

[« Anterior](3282_dominis.md) | [Següent »](33_consultes_dactualitzaci.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
