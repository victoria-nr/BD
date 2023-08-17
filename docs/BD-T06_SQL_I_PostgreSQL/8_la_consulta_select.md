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

[« Anterior](72_formats_dels_nmeros.md) | [Següent »](9_consulta_bsica.md)
# <a name="main"></a>**8. La consulta SELECT**


Com el mateix nom indica SQL (*Structured Query Language*), la consulta o interrogació de la Base de Dades és l'ànima del SQL. I la instrucció que ens ho permet és **SELECT**.

És una instrucció molt flexible i de molta potència, que permet consultar dades d'una o més taules, filtrar per files i/o columnes, ordenar el resultat, agrupar les dades (comptant o sumant alguna columna), ... Fins i tot permet crear taules noves que serien el resultat d'una consulta d'altres taules.

Veurem a continuació la sintaxi general de la instrucció, i posteriorment cadascuna de les clàusules:

Sintaxi

SELECT [DISTINCT] <columnes> 
`  `[ INTO <clàusula> ] 
`    `FROM <clàusula> 
`  `[ WHERE <clàusula> ] 
`  `[ GROUP BY <clàusula> ] 
`  `[ HAVING <clàusula> ] 
`  `[ ORDER BY <clàusula> ] 
`  `[ LIMIT num1 OFFSET num2 ]

Com veieu, les úniques clàusules obligatòries són les **columnes** que volem que isquen com a resultat i la del **FROM** (on es diu d'on venen les dades).

**Nota**

En PostgreSQL no es distingeix entre majúscules i minúscules. Millor dit, PostgreSQL passa de majúscules a minúscules tots els noms de taula o de camp o del que siga, excepte si van entre cometes dobles, que aleshores es respecten maúscules i minúscules.Com a qüestió d'estil, jo no pose mai entre cometes els noms de taules  i camps. I per a una millor lectura, intentaré posar sempre els noms de taula en majúscules, i els noms de camp en minúscules. També posaré en majúscules les clàusules de sentències SQL (SELECT , FROM , WHERE , ...). Però recordeu que és per a una millor lectura. Podria anar tot en minúscules perfectament.

[« Anterior](72_formats_dels_nmeros.md) | [Següent »](9_consulta_bsica.md)

Llicenciat sota la [Llicència Creative Commons Reconeixement NoComercial CompartirIgual 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/)
**Created with an evaluation copy of Aspose.Words. To discover the full versions of our APIs please visit: https://products.aspose.com/words/**
