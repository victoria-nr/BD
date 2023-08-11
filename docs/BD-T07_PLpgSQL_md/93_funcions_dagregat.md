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

[« Anterior](92_operadors_de_classe.md) | [Següent »](exercicis3.md)
# <a name="main"></a>**9.3 Funcions d'agregat**
En PostgreSQL també podem definir funcions d'agregat, de l'estil de **MAX**, **SUM**, **AVG**, ... Podem fer-ho sobre qualsevol tipus, existent o definit per l'usuari

Una funció d'agregat vindrà definida pel seu nom i pel tipus de dades. Per això encara no funciona la sentència

SELECT MAX(latitud) 

FROM POBLACIONS3;

ja que **MAX** no està definida sobre el tipus de dades nou.

A banda del tipus de dades, podrem jugar amb un tipus de dades intern, mentre es calcula la funció d'agregat, que no té per què ser igual al tipus de dades de la funció. I la funció d'agregat vindrà definida per una o dues funcions: una funció de transició d'estat (***sfunc***) que anirà calculant l'estat intern mentre van arribant nous valors; i opcionalment una altra funció final (***ffunc***) per a fer un últim càlcul i donar el valor final (per exemple en la mitjana ***sfunc*** anirà calculant la suma dels valors, i ***ffunc*** haurà de dividir pel nombre total d'elements).

sfunc( estat-intern, següent-item-dades ) ---> següent-estat-intern

ffunc( estat-intern ) ---> valor-final

Opcionalment també podrem donar un valor inicial. La sintaxi és:

CREATE AGGREGATE nom ( 

BASETYPE = tipus\_dades,
SFUNC = sfunc,
STYPE = tipus\_dades\_intern
[ , FINALFUNC = ffunc ]
[ , INITCOND = condició\_inicial ]
[ , SORTOP = operador\_ordenació ]

)

Anem a crear la funció d'agregat MAX per al tipus de dades lat. Comencem per la funció d'estat, que en aquest cas senzillament anirà agafant el màxim. És, per tant, com la funció que calcula el màxim de dos números, però en lat. No tindrem en consideració els valors nuls, per no complicar la cosa.

CREATE OR REPLACE FUNCTION MAX2(lat1 lat,lat2 lat) RETURNS lat AS $cos$

BEGIN

`	`IF lat2 > lat1 THEN RETURN lat2;

`	`ELSE RETURN lat1;

`	`END IF;

END; $cos$ 

LANGUAGE plpgsql;

Ara ja va la funció d'agregat:

CREATE AGGREGATE MAX (

`	`BASETYPE = lat,

`	`SFUNC = MAX2,

`	`STYPE = lat,

`	`INITCOND = '(S,90,0,0)');

Hem posat com a valor inicial el pol sud, per evitar el problema dels nuls. Si tot ha anat bé, ja podrem fer consultes com la del principi d'aquesta pregunta.

SELECT MAX(latitud)

`    `FROM POBLACIONS3;

Si havíem creat també l'operador de classe, les podrem complicar ordenant-les. Per exemple, podem traure la latitud màxima de cada comarca, ordenades de nord a sud:

SELECT comarca,MAX(latitud)

`	`FROM POBLACIONS3

`	`GROUP BY comarca

`	`ORDER BY MAX(latitud) DESC;

Com sempre, la sentència d'esborrar és més senzilla. Per a esborrar una funció d'agregat, hem d'especificar el nom de la funció d'agregat i entre parèntesis el tipus implicat:

DROP AGGREGATE MAX (lat);

[« Anterior](92_operadors_de_classe.md) | [Següent »](exercicis3.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
