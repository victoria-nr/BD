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

[« Anterior](0_nota_inicial.md) | [Següent »](2_plpgsql.md)
# <a name="main"></a>**1. Introducció**
Una vegada vist amb suficient profunditat el SQL, anem a enfocar l'atac a una base de dades des d'un altre punt de vista. No com un comando que l'executem i ens dóna la resposta, sinó des d'un llenguatge procedimental, amb les estructures de control pròpies d'aquestos (condicionals, bucles, funcions, ...), però accedint òbviament a les dades. Ara, quan fem una consulta obtindrem un conjunt de dades al qual anomenarem **cursor**, i que segurament l'haurem de recórrer des del principi fins al final per a fer el tractament que siga.

La part bàsica de tot açò serà la construcció de funcions. Aquestes es poden construir utilitzant molts llenguatges, començant per **SQL**, on agruparem en una funció unes quantes sentències SQL o una sentència complicada. Anem a veure algun exemple, sobre l'usuari **geo\_grup\_9999x**, bé des de **psql** o bé des d'una finestra de SQL de **DBeaver**, que el que fa és sumar la població dels pobles de la comarca passada com a paràmetre. Hem utilitzat l'opció **CREATE OR REPLACE**, així en cas que estiga ja creada, dons la substituirem.

CREATE OR REPLACE FUNCTION gent\_com(text) RETURNS numeric AS '

`        `SELECT SUM(poblacio)

`            `FROM POBLACIONS

`            `WHERE nom\_c=$1;

' LANGUAGE SQL;

I ara, així ens dirà quina és la població de **Baix Maestrat**:

SELECT gent\_com('Baix Maestrat');

O una altra també interessant, on traurem totes les comarques amb la seua població, utilitzant la funció anterior:

SELECT nom\_c,gent\_com(nom\_c)

`    `FROM COMARQUES;

Però on realment traurem profit és amb els llenguatges procedimentals. Podríem triar entre molts: **C**, **Tcl**, **Perl**, **Python**, ... En aquest curs optarem per **PL/pgSQL** (*ProceduraL PostGreSQL*).

En versions anteriors podia passar que s'haguera de preparar la Base de Dades per a utilitzar el llenguatge. És a dir, podia passar que no estiguera disponible el llenguatge de programació en la Base de Dades. Aleshores s'havia d'instal·lar amb la sentència:

CREATE PROCEDURAL LANGUAGE plpgsql;

Però **no serà el nostre cas**. Podem utilitzar sense problemes tant el llenguatge **SQL** com el **PL/pgSQL**, que és el que realment ens interessa.

[« Anterior](0_nota_inicial.md) | [Següent »](2_plpgsql.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
