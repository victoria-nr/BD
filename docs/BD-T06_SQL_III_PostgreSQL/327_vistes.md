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

[« Anterior](exercicis2.md) | [Següent »](exercicis3.md)
# <a name="main"></a>**3.2.7 Vistes**
Les vistes, també anomenades esquemes externs, consisteixen en visions particulars de la B.D. Es correspon al nivell extern de l'arquitectura a tres nivells. Les taules, que són les que realment contenen les dades i donen la visió global de la B.D., corresponen al nivell conceptual.

La sintaxi bàsica és la següent:

CREATE VIEW *nom\_vista* 
AS *subconsulta*
[WITH READ ONLY];

on se li dóna un nom, és el resultat d'una subconsulta (un SELECT), i tenim la possibilitat d'impedir la modificació de les dades.

Per exemple, una vista amb les comarques, el número de poblacions de cada comarca, el total d'habitats i l'altura mitjana:

CREATE OR REPLACE VIEW ESTADISTICA AS 

SELECT nom\_c, count(nom) AS num\_p,sum(poblacio) AS pobl, avg(altura) AS alt\_mitjana 

FROM POBLACIONS
GROUP BY nom\_c
ORDER BY nom\_c;

**Nota**

Si voleu provar aquesta vista, ho podeu fer en la Base de Dades **geo**, ja que en ella tenim dades per a la consulta que proporciona les dades a la vista. Recordeu que ens estem connectant tots com el mateix usuari, per tant si algú ha creat un objecte (en aquest cas una vista) no es podrà utilitzar aquest nom per a crear un altre objecte. Per això és convenient que si feu una prova de crear un objecte, després esborreu aquest objecte.** 

Observeu la sintaxi CREATE OR REPLACE, que va molt bé per a crear, i si ja existeix per a substituir. Com que estem accedint tots com el mateix usuari, serà prou normal que l'objecte ja existesca per haver-lo creat un company. D'aquesta manera el substituirem. No passa res per esborrar un objecte ja existent, ja que tot açò són proves.

La manera d'utilitzar-la és com una taula normal, però ja sabem, que en realitat les dades estan en les taules.

SELECT \* 
FROM ESTADISTICA;

I fins i tot es pot jugar amb taules i vistes. En aquesta sentència traurem la província, nom de la comarca, número de pobles i altura mitjana de les comarques amb 5 o menys pobles:

SELECT provincia,COMARQUES.nom\_c,num\_p,alt\_mitjana
FROM COMARQUES , ESTADISTICA
WHERE COMARQUES.nom\_c=ESTADISTICA.nom\_c and num\_p <= 5;



Per a esborrar una vista

DROP VIEW *nom\_vista*

Per exemple, per a esborrar la vista anterior:a esborrar una vista

DROP VIEW ESTADISTICA;

[« Anterior](exercicis2.md) | [Següent »](exercicis3.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
