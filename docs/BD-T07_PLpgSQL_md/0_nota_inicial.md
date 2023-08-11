Bases de Dades

- [Tema 7: Programació en PostgreSQL](index.md)
- [Objectius i Coneixements previs](objectius_i_coneixements_previs.md)
- [0. Nota inicial](0_nota_inicial.md)
- [1. Introducció](1_introducci.md)
- [2. PL/pgSQL](2_plpgsql.md)
- [3. Declaració de variables](3_declaraci_de_variables.md)
- [4. Instruccions](4_instruccions.md)
- [5. Funcions](5_funcions.md) 
  - [Exercicis](exercicis.md)
- [6. Utilització de cursors](6_utilitzaci_de_cursors.md) 
  - [Exercicis](exercicis0.md)
- [7. Missatges i excepcions](7_missatges_i_excepcions.md)
- [8. Triggers](8_triggers.md) 
  - [Exercicis](exercicis1.md)
- [9. Creació d'altres objectes basats en funcions](9_creaci_daltres_objectes_basats_en_funcions.md) 
  - [9.1 Operadors](91_operadors.md) 
    - [Exercicis](exercicis2.md)
  - [9.2 Operadors de classe](92_operadors_de_classe.md)
  - [9.3 Funcions d'agregat](93_funcions_dagregat.md) 
    - [Exercicis](exercicis3.md)
- [Exercicis de tot el tema](exercicis_de_tot_el_tema.md)

[« Anterior](objectius_i_coneixements_previs.md) | [Següent »](1_introducci.md)
# <a name="main"></a>**0. Nota inicial**
En aquest tema també construirem molts objectes, per tant podem "boicotejar-nos" entre nosaltres si utilitzem tots el mateix usuari.

És per això que en aquest tema tots els exemples i tots els exercicis els farem sobre un usuari (i contrasenya) i una Base de Dades anomenada **geo\_grup\_9999x**, on heu de substituir **grup** pel codi del vostre grup, **9999** per les 4 últimes xifres del vostre DNI, i la **x** per la lletra del vostre NIF. La connexió serà per tant:

Servidor: **89.36.214.106**

Usuari: **geo\_grup\_9999x** (on **grup** és el codi del vostre grup, **9999** són les 4 últimes xifres del vostre DNI, i **x** la vostra lletra del NIF)

Contrasenya: **geo\_grup\_9999x** (el mateix d'abans)

Base de Dades: **geo\_grup\_9999x** (el mateix d'abans)

En la Base de Dades **geo\_grup\_9999x** ja teniu les taules de prova que estem utilitzant: **COMARQUES**, **POBLACIONS** i **INSTITUTS**.

Per a poder desenvolupar correctament el tema, us faran falta alguns altres objectes creats en el tema anterior, però observeu com ara no interferireu entre vosaltres.

Ací teniu les sentències de creació dels objectes que us faran falta:

- Creació de la taula **PROVINCIES** :

CREATE TABLE PROVINCIES AS
SELECT provincia, SUM(poblacio) AS habitants, SUM(Q) AS instituts
`   `FROM (COMARQUES INNER JOIN POBLACIONS ON COMARQUES.nom\_c=POBLACIONS.nom\_c)
`     `LEFT JOIN (SELECT cod\_m, count(\*) AS Q
`                  `FROM INSTITUTS
`                  `GROUP BY cod\_m) I ON POBLACIONS.cod\_m=I.cod\_m
`   `GROUP BY provincia;

- Creació dels dominis **hemi\_lat**, **graus\_lat**, i **min\_seg** :

CREATE DOMAIN hemi\_lat AS char(1)
`    `CHECK (VALUE IN ('N','S'));

CREATE DOMAIN graus\_lat AS numeric(2)
`    `CHECK (VALUE BETWEEN 0 AND 90);

CREATE DOMAIN min\_seg AS numeric(2)
`    `CHECK (VALUE BETWEEN 0 AND 59);

- Creació del tipus **lat** :

CREATE TYPE lat AS (
`    `h hemi\_lat,
`    `g graus\_lat,
`    `m min\_seg,
`    `s min\_seg );

- Creació de la taula **POBLACIONS3** :

CREATE TABLE POBLACIONS3 (
`    `nom VARCHAR(50) CONSTRAINT cp\_pob3 PRIMARY KEY,
`    `latitud lat,
`    `comarca varchar(50) );

[« Anterior](objectius_i_coneixements_previs.md) | [Següent »](1_introducci.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
