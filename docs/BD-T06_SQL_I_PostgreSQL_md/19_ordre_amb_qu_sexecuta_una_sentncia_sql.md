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

[« Anterior](exercicis8.md) | [Següent »](exercicis_de_tot_el_tema_amb_els_resultats.md)
# <a name="main"></a>**19. Ordre amb què s'executa una sentència SQL**


Com hem vist, i com veurem en la Part II d'aquest tema, la sentència **SELECT** és molt completa i molt potent. Pot fer moltes coses.

Potser ens convinga saber en quin ordre s'executen les clàusules de què es compon, perquè això ens pot prevenir de possibles errors en el moment de construir una sentència d'una certa envergadura. L'ordre d'execució és el següent:

- Primer s'agafen les dades des de la taula o les taules especificades en el **FROM**. No podrem tractar informació que no tinguem en aquest origen de dades.
- Després s'eliminen les files que no acompleixen la condició del **WHERE**, en cas que tinguem aquesta clàusula.
- Després les files resultants s'agrupen pel o pels camps especificats en el **GROUP BY**, en cas que tinguem aquesta clàusula.
- Una vegada fets els grups, s'eliminen els que no acomplesquen la condició del **HAVING**, en cas que tinguem aquesta clàusula.
- Després se selecciona la informació especificada en les columnes, que en cas d'haver alguna funció d'agregat actuarà sobre els grups que resten (si teníem clàusula GROUP BY) o sobre el total de l'origen de dades.
- Posteriorment s'ordena pels camps especificats en el **ORDER BY**, en cas que tinguem aquesta clàusula.
- Després s'aplica els predicat **DISTINCT** en cas de tenir-lo especificat.
- Per últim s'agafen tantes files com indica la clàusula **LIMIT**, desplaçades tantes com indique **OFFSET**, si és que tenim aquesta clàusula especificada..
- Si tenim clàusula **INTO** es procedirà a crear una taula nova amb el resultat anterior.

Tenir clar aquest ordre ens pot clarificar alguna cosa, i poder evitar alguns errors. L'error de la següent sentència ja s'havia explicat en la pregunta 13.

SELECT nom\_c, COUNT(\*), cod\_m
FROM POBLACIONS
GROUP BY nom\_c

ens donarà el següent error:

![](19_ordre_amb_qu_sexecuta_una_sentncia_sql.002.png)

Però si analitzem l'ordre en què s'executen és lògic: quan arribem a mostrar els camps (entre ells **cod\_m**) els grups ja s'han fet, i per a valors iguals de **nom\_c**. En aquest moment no puc traure una cosa individual de cada grup com és el codi de municipi, perquè ja s'ha agrupat. En aquest moment només es pot intentar traure el nom de la comarca (ja que té el mateix valor per a tot el grup, és el camp pel qual hem agrupat), o alguna funció d'agregat, que calcula sobre el grup. I d'això ens intenta avisar PostgreSQL.

Per a solucionar-lo podem incloure el **cod\_m** en el **GROUP BY**, i aleshores farem un grup per cada comarca i població diferent, però segurament això no ens valdrà de res en aquest exemple, perquè cada grup només contindrà un element (un municipi), encara que en altres exemples sí que pot tenir sentit. O si no era això el que preteníem, senzillament llevem el camp cod\_m de la sentència, i ens funcionarà bé.



Un altre exemple il·lustratiu (que ja el vam posar molt paregut en la pregunta 13) pot ser el següent: podríem intentar traure l'altura màxima de tots els pobles, i la població que té aquesta altura. Podríem estar temptats de fer-lo d'aquesta manera:

SELECT MAX(altura), nom
FROM POBLACIONS;

Ens donarà el mateix error que abans, ja que com tenim una funció d'agregat intentarà fer grups, i com no tenim clàusula GROUP BY tota la taula serà un grup. I podrà calcular el màxim sense problemes, però no podrà traure una cosa individual del grup, com és el nom. I en aquest cas no es pot solucionar incloent el nom en el GROUP BY, perquè aleshores farem un grup per cada població. De moment, abans de veure les subconsultes, només podem resoldre aquest exemple ordenant per l'altura de forma descendent, i fer **LIMIT 1**.

Podem observar que si tenim clàusula **GROUP BY**, a partir d'aquest moment tots els camps que posem han d'estar en el GROUP BY o en una funció d'agregat, tant en la condició del **HAVING**, com en les **columnes** com en el **ORDER BY**. En canvi no caldrà per a la clàusula **WHERE**, ja que aquesta es realitza abans que el **GROUP BY**

[« Anterior](exercicis8.md) | [Següent »](exercicis_de_tot_el_tema_amb_els_resultats.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
