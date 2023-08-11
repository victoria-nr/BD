Bases de Dades

- [Tema 6: SQL - Consulta bàsica (part I)](index.md)
- [Objectius i Coneixements previs](objectius_i_coneixements_previs.md)
- [1. Introducció](1_introducci.md)
- [2. DDL i DML](2_ddl_i_dml.md)
- [3. Client DBeaver: instal·lació i confiuració](3_client_dbeaver_installaci_i_confiuraci.md)
- [4. Client DBeaver: utilització](4_client_dbeaver_utilitzaci.md)
- [5. Dades dels exemples i els exercicis](5_dades_dels_exemples_i_els_exercicis.md)
- [6. Operadors](6_operadors.md)
- [7. Funcions](7_funcions.md) 
  - [7.1 Formats de les dates](71_formats_de_les_dates.md)
  - [7.2 Formats dels números](72_formats_dels_nmeros.md)
- [8. La consulta SELECT](8_la_consulta_select.md)
- [9. Consulta bàsica](9_consulta_bsica.md) 
  - [Exercicis](exercicis.md)
- [10. Àlies en les columnes](10_lies_en_les_columnes.md) 
  - [Exercicis](exercicis0.md)
- [11. La clàusula WHERE](11_la_clusula_where.md) 
  - [Exercicis](exercicis1.md)
- [12. Funcions d'agregat](12_funcions_dagregat.md) 
  - [Exercicis](exercicis2.md)
- [13. La clàusula GROUP BY](13_la_clusula_group_by.md) 
  - [Exercicis](exercicis3.md)
- [14. La clàusula HAVING](14_la_clusula_having.md) 
  - [Exercicis](exercicis4.md)
- [15. La clàusula ORDER BY](15_la_clusula_order_by.md) 
  - [Exercicis](exercicis5.md)
- [16. El predicat DISTINCT](16_el_predicat_distinct.md) 
  - [Exercicis](exercicis6.md)
- [17. La clàusula LIMIT .. OFFSET](17_la_clusula_limit__offset.md) 
  - [Exercicis](exercicis7.md)
- [18. Consulta de creació de taules](18_consulta_de_creaci_de_taules.md) 
  - [Exercicis](exercicis8.md)
- [19. Ordre amb què s'executa una sentència SQL](19_ordre_amb_qu_sexecuta_una_sentncia_sql.md)
- [Exercicis de tot el tema, amb els resultats](exercicis_de_tot_el_tema_amb_els_resultats.md)

[« Anterior](exercicis3.md) | [Següent »](exercicis4.md)
# <a name="main"></a>**14. La clàusula HAVING**


Aquesta clàusula acompanya normalment a la de **GROUP BY**, i servirà pera poder triar alguns grups que acomplesquen una determinada condició.

Pot anar sense el GROUP BY, però aleshores el seu funcionament és com el WHERE, i per tant no val la pena. És a dir, en la pràctica sempre que trobem un HAVING hi haurà també el GROUP BY i servirà per seleccionar alguns grups, els que acomplesquen la condició del HAVING.

També podríem dir que el HAVING és al GROUP BY, el que el WHERE és al SELECT



Sintaxi

SELECT <columnes> 
FROM <taules> 
[GROUP BY <columnes>] 
HAVING <condició>



Únicament comentarem el cas en què acompanya al GROUP BY. I com hem dit, el que fa és filtrar els grups: dels grups resultants del GROUP BY, només eixiran els que acomplesquen la condició.

Aquesta condició contindrà alguna funció d'agregat o contindrà columnes incloses en el GROUP BY. Fixeu-vos que és lògic, ja que serveix per a triar grups una vegada fets, i aleshores ja no es podrà anar a un element del grup.

Per exemple, aquesta sentència servirà per traure les comarques on hi ha més de 20 pobles, i el número que hi ha:

SELECT nom\_c, COUNT(\*) 
FROM POBLACIONS
GROUP BY nom\_c
HAVING COUNT(\*) > 20;



Exemples

1. Traure aquelles poblacions que tenen més d'un de Centres Integrats de Formació Professional. La manera de saber que és un Centre Integrat és perquè el seu nom comença per CIPFP. De moment només traurem el codi de la població, i així només ens fa falta la taula INSTITUTS. Més avant aprendrem a agafar les dades de més d'una taula, i aleshores traurem també el nom de la població

SELECT cod\_m, COUNT(\*)
FROM INSTITUTS
WHERE nom LIKE 'CIPFP%'
GROUP BY cod\_m
HAVING COUNT(\*) > 1

El que fem en aquesta sentència és, de la taula INSTITUTS seleccionar únicament els Centres Integrats (utilitzant l'operador LIKE per a que comencen per CIPFP)i i després agrupar pel codi de municipi. Una vegada fets els grups, eliminarem els grups que no acompleixen la condició de HAVING, és a dir, els que tenen 0 o 1 Centre Integrat. I d'aquestos grups seleccionats traurem el codi del municipi i el número de Centres Integrats (que sempre serà igual o major que 2).

2. Calcular el número d'habitants màxim, el mínim i el número d'habitants mitjà de les poblacions de les comarques amb més de 20 pobles.

SELECT nom\_c , COUNT(cod\_m) AS "Número de pobles" , Max(poblacio) AS Màxim , Min(poblacio) AS Mínim , Avg(poblacio) AS Mitjana
FROM POBLACIONS
GROUP BY nom\_c
HAVING COUNT(cod\_m) > 20;



3. Traure l'altura mitjana, total de població i població mitjana, d'aquelles comarques que tenen una altura mitjana superior a 800 metres.

SELECT nom\_c , AVG(altura) AS "Altura mitjana" , SUM(poblacio) AS "Total població" , Avg(poblacio) AS "Població mitjana"
FROM POBLACIONS
GROUP BY nom\_c
HAVING AVG(altura) > 800;



[« Anterior](exercicis3.md) | [Següent »](exercicis4.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
